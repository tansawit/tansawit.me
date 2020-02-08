---
title: "Projects"
date: 2019-09-20T16:51:41+07:00
draft: false
---

Some of my projects to date include:

## CubeSat Engineering Model

I assisted assembling and programming an engineering model of an Arduino-based 1U CubeSat to potentially be used in natural disaster prevention and relief as part of Dr Tippawan Wanwiwake's research at the Geo-Informatics and Space Technology and Development Agency ([GISTDA](https://gistda.or.th/main/en)), 

Prior to that, during my internship with the agency, I compiled a literature review examining the practicality and feasibility of adopting the platform for use in Thailand.

## Rapper Lyrics Matching Model

The [project and resulting paper](https://github.com/tansawit/rap-artist-classifier) examines the effectiveness of various classification models in matching rap lyrics to the correct artists.

The accompanying Python [web application](https://rap-match.herokuapp.com/), uses scikit-learn, nltk, spaCy, and the Genius API allows users to input their own text, choose the classification model to use, and outputs the name of the artist with the closest-matching lyrics features.

The source code for the app can be found on the [GitHub repo](https://github.com/tansawit/rap-match).

This project was done as the final project for the University of Michigan's EECS486 (Introduction to Information Retrieval) class.

## Notes-Search

A web app to search through all of my notes on various topics. Built using ElasticSearch, Go, React, and Docker.

Current (work-in-progress) version is hosted at [search.tansawit.me](http://search.tansawit.me) while the source code and more information can be found on its [GitHub repo](https://github.com/tansawit/notes-search).

## JARVIS Personal Assistant Chatbot

A chatbot built on top of the LINE messaging platform's Messaging API and Google's Dialogflow. It integrates and scrapes data from various services and websites to provide numerous useful features.

Current feature set include:

- Current weather and condition
- Directions
- World Clock
- Movies in theaters and showtime

## Tools

- LINE Notify [service](https://github.com/tansawit/aqi-daily-notify), written in Go, to send me a message with the daily PM 2.5 values at my home, apartment, and office.
