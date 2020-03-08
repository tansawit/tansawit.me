---
author: "Sawit Trisirisatayawong"
author_link: "https://tansawit.me"
title: "NoteLog: Building A Personal Information Storage and Retrieval Service - Idea and Design"
date: 2020-03-03T15:10:55+07:00
draft: true
description: "A single search tool to rule them all"
categories:
- projects
- elastic
tags:
- go
- elasticsearch
description_as_summary: true
show_in_homepage: true
featured_image: /images/building-my-own-note-storage-part-one/note.jpg
images: 
- /images/building-my-own-note-storage-part-one/note.jpg
---

## Introduction and the Problem

I've found myself relying on an increasing number of services to store the information I want to reference later (article with [Pocket](https://app.getpocket.com/), repositories with [GitHub](https://github.com/), notes with [Bear](https://bear.app/) or [my wiki](https://notes.tansawit.me)). While this is normally fine, it means that whenever I want to look up something, I need to spend time actually thinking about *where* to search before actually thinking about *what* to search for. That time, I believe, can be minimized.

What's more, many of these services I use also searches on a somewhat 'surface-level' (only searching for title of websites and not the actual content). To me, this greatly limits the future discoverability of the item. Finally, there is no way of searching through all these services at the same time, using the same query. This makes cross-referencing quite a bit more difficult. For example, if I want to search for the info I've saved from a topic expert (let's say across their blogs, repos, and tweets), I would have to do 3 separate searches and somehow merge them myself, either manually or mentally. What I roughly envision is a service that allows me to search for their name, along with a topic keyword, and getting all the relevant information, across multiple sources, in a single results field.

## Previous Attempts and Current Solution

In order to solve this issue, I have tried various tools and apps that are available. Out of all of them, [Alfred](https://www.alfredapp.com/) probably got the closest to being what I want, especially by utilizing its [workflows](https://www.alfredapp.com/workflows/) feature. But searching multiple places still requires multiple calls to different workflows. Again, this makes cross-referencing a manual and time-consuming effort.

## Proposed Solution

Now onto the solution I plan to build. The service I've planned consists of three main parts:

- Data aggregator/loader
- Search service/API
- Frontent clients

Let's expand more on each of these:

### Data Aggregator

This will be a cron service running tasks that routinely pulls and update data from various places. In the initial proof-of-concept stage, I will be using data from two sources:

- GitHub: using the [GitHub API](https://developer.github.com/v3/)
- My Blog: through web scraping using a combination of [colly](https://github.com/gocolly/colly) and [goquery](https://github.com/PuerkitoBio/goquery)

These information will then be fed into my [Elastic Cloud](https://www.elastic.co/cloud/) instance to be indexed by [Elasticsearch](https://www.elastic.co/).

### Search Service and API

This module will act as the intermediary between whatever contexts the service will be used (web, apps, Alfred workflows, etc.) and the Elasticsearch indices. It will be responsible for transforming the query as necessary, performing the search, and retrieving the results from Elastic.

Although I could have simply used [Elastic's own API](https://www.elastic.co/guide/en/elasticsearch/reference/current/rest-apis.html), which will probably make building my frontend [easier](https://github.com/appbaseio/reactivesearch), I decided to build my own for two reasons:

- Granular Control: By having my own API in the middle, I can control specifically how data is being routed, the how the input/output is formatted, and so on. I also can specify the format the API routes myself, hopefully making it easier to integrate with the frontend applications.
- Abstraction and maintainability: As the service itself will hopefully be used from various mediums and contexts, having to handle request manipulation and transformation at the frontend will get messy fast. Instead, by abstracting away all that work behind my API, it will make building a new clients much easier, not to mention helping with the ease of implementing future fixes, changes, and features across all services.

### Frontend Clients

Now comes the part that I'm still the most unclear on.
