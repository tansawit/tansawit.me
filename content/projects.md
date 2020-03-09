---
title: "Projects"
date: 2019-09-20T16:51:41+07:00
draft: false
---

Some of my projects to date include:

## NoteLog [:(fab fa-github):](https://github.com/NoteLog)[:(fas fa-globe):](https://search.notelog.app)

*Work In Progress*

Technology Stack: Go, Elasticsearch/Elastic Cloud, React, Google Cloud Run, Docker

A service to store and search through all of the things I want to reference in one place. Currently implemented to search through:

- My GitHub [repositories](https://github.com/tansawit?tab=repositories&type=source) and those that I've [starred](https://github.com/tansawit?tab=stars)
- My blog posts on this site

## CubeSat Engineering Model

I assisted assembling and programming an engineering model of an Arduino-based 1U [CubeSat](https://en.wikipedia.org/wiki/CubeSat) miniature satellite to be used in natural disaster prevention and relief. The project was part of Dr Tippawan Wanwiwake's research at the Geo-Informatics and Space Technology and Development Agency ([GISTDA](https://gistda.or.th/main/en)).

Prior to that, during my internship with the agency in high school, I compiled a literature review examining the practicality and feasibility of adopting the platform for use in Thailand.

## Rap Artist Lyrics Classifier [:(fab fa-github):](https://github.com/tansawit/rap-artist-classifier) [:(fas fa-globe):](https://rap-match.herokuapp.com)

The project and [resulting paper](https://github.com/tansawit/rap-artist-classifier) examines the accuracy and effectiveness of various classification models in matching rap lyrics to the correct artists.

The accompanying Python web application, built with scikit-learn, nltk, spaCy, and the [Genius API](https://docs.genius.com/), allows users to input their own text, choose the classification model to use, and outputs the name of the artist with the closest-matching lyrics features.

The source code for the app can be found on the [GitHub repo](https://github.com/tansawit/rap-match).

This project was done as the final project for the University of Michigan's EECS486 (Introduction to Information Retrieval) class.

## JARVIS Personal Assistant Chatbot

A chatbot built on top of the LINE's [Messaging API](https://developers.line.biz/en/docs/messaging-api/overview/) and Google's [Dialogflow](https://dialogflow.com/). It integrates and scrapes data from various services and websites to provide numerous useful features.

Current feature set include:

- Current weather and condition
- Directions
- World Clock
- Movies in theaters and showtime

## Smaller Projects

- Air Quality Index and PM 2.5 [LINE Notify](https://notify-bot.line.me/en/) service, written in Go, to send me a message with the daily PM 2.5 values at my home, apartment, and office. [:(fab fa-github):](https://github.com/tansawit/aqi-daily-notify)
