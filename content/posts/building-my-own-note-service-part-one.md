---
author: "Sawit Trisirisatayawong"
author_link: "https://tansawit.me"
title: "Building My Own Information Storage and Retrieval Service: Idea and Designing the Service"
date: 2020-03-03T15:10:55+07:00
draft: true
description: "One service to rule them all. Because looking in multiple places takes too much energy..."

description_as_summary: true
show_in_homepage: true
featured_image: /images/building-my-own-note-storage-part-one/note.jpg
---

There's two feelings I hate most when it comes to knowledge and information: 

1. Knowing you've seen/heard of/read something but not being able to remember the details and
2. Not knowing where you saved something important. 

In an effort to solve those two issues, I have previously built a few tools for myself, but none scratch that itch well enough yet:

[**notes.tansawit.me**](https://notes.tansawit.me) 

My first attempt at a solution. Implementation-wise it's just a Hugo static site built using Alex Shpak's [hugo-book theme](https://github.com/alex-shpak/hugo-book).

The website and theme by nature is pretty decent at categorising information. All notes are Markdown files structured into folders by section, topic, sub-topic etc. This is great when it comes to seeing all the things I know on a single topic. However, I've found myself spending more time sorting the notes into an increasingly more nested folder structure than actually writing them. Along with that, while there is search, the default only searches off the document titles.

[**search.tansawit.me**](http://search.tansawit.me)

This iteration is the complete opposite of the previous attempt in that it was built completely from scratch using a combination of ElasticSearch, Golang API backend, and React frontend. By using ElasticSearch and personally configuring exactly the information to index along with specifying the query parameters, I managed to somewhat solve the previous issue of search granularity. But, at least to the extent that I've taken it, there still remain some issues and potential improvements

- Notes are all stored as plaintext. This means links within notes are not possible.
- No easy way to share the retrieved notes by individual links
- The implementation was focused on primarily focused on solving the issue of the previous attempt. Thus the ease of adding new data sources was not considered.

**publicly available solutions**

Some of the pre-made solutions also got pretty close, but doesn't still lacks in some areas. To that point, [Alfred](https://www.alfredapp.com/) probably got the closest to being what I want, especially when combined with its [workflows](https://www.alfredapp.com/workflows/) feature. I will most likely end up building my own workflow on top of it, making it one of the clients for the service. But as it stands, I still require multiple workflows to achieve the functionality I need.

My ideal solution would have the following features:

- Aggregate data from all the sources I care about (more on this later) 
- Full-text search across all text components
- Easy retrieval for sharing/local downloads for notes

For all of this, I hope to be able to search through all of the aggregated items in a single place (a la Google Search/URL bar, Alfred, Mac Spotlight)

## The Design

I plan on building services to pull data from various sources and store them in Elasticsearch indices. Each of them will run on [cron schedules](https://en.wikipedia.org/wiki/Cron) to keep the information updated without me having to explicitly check. 

Then, from the client side, any search queries coming in will be passed through a backend API service, responsible for any query manipulation/transformation, before being subsequently passed on to the Elasticsearch module for full-text/fuzzy searching. The query results will then again be transformed as needed by the backend service, before being forwarded to the client. 

The diagram below illustrates the general flow of data and queries:

![Data/Query Pipeline](/images/building-my-own-note-storage-part-one/data-feed.png)

### Sources

For the first iteration, I'll be pulling information from the following two places:

#### Blog Posts

For quick references and sending links to others.

**Implementation**

For this I used a combination of the [colly](https://github.com/gocolly/colly) scraper and [goquery](https://github.com/PuerkitoBio/goquery) libraries. I started by using colly's `Collector` to collect all the posts listed on my website's [posts page](https://tansawit.me/posts). Then for each of those posts I use goquery's `Find` function to find and extract the information I want into a custom Post struct. As of the time of writing, these info are:

- Title
- Date
- Categories
- Tags
- Text Content
- URL of Post

#### GitHub

I wanted something similar to Lachlan Donald's [alfred-github-jump workflow](https://github.com/lox/alfred-github-jump), where I can search for both my own repositories as well as those that I've starred

**Implementation**

My implementation is simply based off Lachlan's [repos.go](https://github.com/lox/alfred-github-jump/blob/master/repos.go) functions for retrieving the repos from the two places.

### Database

#### Elasticsearch

While there are interesting alternatives to Elastic to supply the full-text search capability such as [Algolia](https://www.algolia.com/), which even claimed to be the [superior option](https://blog.algolia.com/full-text-search-in-your-database-algolia-versus-elasticsearch/), there are certain issues that I have with it:

- The need to display the Algolia logo when using a free tier. With some of the mediums I plan on using this service through, that might just not be possible. Plus, I prefer to keep the UI as clean as possible.
- Customization/Configuration constraint. Elastic, despite, or perhaps due to, its complex Domain Specific Language, allow for more fine-grained control over how I want my search service to work. It also allow for better future extensibility of the two.

Having used ElasticSearch in previous projects, I'm also more comfortable with how the technology works and how to achieve the search system I want from it. Lastly, I'm personally interested in learning more about the Elastic Stack, so this will be a good chance to gain more experience with it. So I'll stick with it for now and will see how it goes in the long run.


## Conclusion and Next Steps

