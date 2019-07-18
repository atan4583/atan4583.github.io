---
title: "Project-Wrangle and Analyze Twitter Data Feeds"
date: 2019-04-13 00:00:00 +0000
tags: [Data Wrangling]
categories: [Project]
excerpt: Gather data from a variety of sources and in a variety of formats, assess its quality and tidiness, then clean it. Showcase data wrangling results through analyses and visualizations.
mathjax: "true"
thumbnail: "/images/Project4-tweetDataAnalysis/dogs.jpg"
---

$$\Rightarrow$$ <a href="\images\Project4-tweetDataAnalysis\wrangle_act_report.slides.html" target="_blank"><b>Slide Show</b></a> (Hit _**Auto Play**_ button to suspend/resume slide show or _**Manual Play**_ button to advance slide page manually)

# <a href="https://en.wikipedia.org/wiki/WeRateDogs" target="_blank">WeRateDogs</a> Twitter Feed Dataset Analysis
Wrangle WeRateDogs Twitter data to create interesting and trustworthy analyses and visualizations. This project is part of the deliverables for my <a href="https://www.udacity.com/course/data-analyst-nanodegree--nd002" target="_blank">Data Analyst Nanodegree</a> with Udacity.

## DataSet
Gather data from these 3 sources:
-  WeRateDogs Twitter archive. This contains 5000+ basic tweet data about dog rating, name, and "stage".
-  tweet image predictions from <a href="https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv" target="_blank">Udacity site</a>. This file contains dog breed prediction results (from a Neural Network classifier) for every dog images from the WeRateDogs Twitter archive.
-  Twitter API tweepy. Use this API to query additional data (in JSON format) for each tweet ID in the WeRateDogs Twitter archive.

## Process
-  After gathering the data, assess them visually and programmatically for quality and tidiness issues. Detect and document at least eight (8) quality issues and two (2) tidiness issues.

-  Clean each of the issues identified, document the cleaning steps taken and output the results to a high quality and tidy master pandas DataFrame.

-  Analyze and visualize the wrangled data to produce at least three (3) insights and one (1) visualization.

-  Produce a 300-600 word written report with brief description of the wrangling efforts, frame it as an internal document. Create another 250-word-minimum written report to communicate the insights and displays the visualization(s) produced from the wrangled data. Frame it as an external document, like a blog post or magazine article.

## Tool
Jupter Notebook (Python)

## Programming libraries
panda, numpy, matplotlib, seaborn, tweepy, json, requests

## Artifact
-  wrangle_act.ipynb
-  wrangle_report.pdf, wrangle_report.html
-  act_report.pdf, act_report.html
-  twitter_archive_enhanced.csv, image_predictions.tsv, tweet_json.txt, twitter_archive_master.csv, twitter_archive.db

See <a href="https://github.com/atan4583/dand-project-portfolio" target="_blank">code here</a>.
