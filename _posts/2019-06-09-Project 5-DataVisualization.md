---
title: "Project-Analyze Loan Listing Dataset"
date: 2019-06-09 00:00:00 +0000
tags: [Data Analysis]
categories: [Project]
excerpt: Perform data wrangling, EDA and on a subset of loan listings from Prosper, an online peer-to-peer lending business. From the subset of 6,123 listings between 1 July 2008 and 31 December 2009, examine selective attributes on borrower and loans, time series events to see their effects on loan listing distributions. Create a storyboard to showcase the findings in univariate, bivariate and multivariate visualizations.
mathjax: "true"
thumbnail: "/images/Project5-loanDataAnalysis/p2p.jpg"
---

$$\Rightarrow$$ <a href="\images\Project5-loanDataAnalysis\Prosper_Loan.slides.html" target="_blank"><b>Slide Show</b></a> (Hit `Auto Play` button to suspend/resume slide show or _**Manual Play**_ button to advance slide page manually)

# Prosper Loan Dataset Exploration
Explore loan data from Prosper with plots of one, two and more variables. Produce a short presentation to illustrate interesting properties, trends, and relationships discovered in the dataset. This project is part of the deliverables for my <a href="https://www.udacity.com/course/data-analyst-nanodegree--nd002" target="_blank">Data Analyst Nanodegree</a> with Udacity.

## Dataset
The data consists of 6,123 Prosper loan listings created between 1 July 2008 and 31 December 2009 from Prosper, an online peer-to-peer lending business. The data has 16 features
(excluding two ID type variables for borrower ID and listing key), most of which are quantitative in nature but there are a few categorical ones as well.

A data feature dictionary describing the variables is available <a href="https://www.google.com/url?q=https://docs.google.com/spreadsheet/ccc?key%3D0AllIqIyvWZdadDd5NTlqZ1pBMHlsUjdrOTZHaVBuSlE%26usp%3Dsharing&sa=D&ust=1554484977407000" target="_blank">here</a>.

The dataset for `exploration` can be downloaded <a href="https://drive.google.com/file/d/1SSRs1cna9JoYpQg0sox1d9swT01GEacR/view?usp=sharing" target="_blank">here</a>, and the clean dataset for `explanatory` purpose can be downloaded <a href="https://drive.google.com/file/d/1WSURY1r0B4xh5RVV9asR473hxbGAePM-/view?usp=sharing" target="_blank">here</a>.

## Summary of Findings
In the exploration, I focused on 6,123 listings between 1 July 2008 and 31 December 2009, and examined selective attributes on borrower and loans, time series events to see their effects on loan listing distributions.

In univariate exploration, I found:
-  distributions of listing categories, borrower professions and states reveal the majority of listings were for debt consolidation, most of the borrowers held professional jobs and residents of CA had the highest number of listings.

- distribution listing amount shows majority of loan listings were below $3000 in values, employment status distribution shows a combined 97.02% of borrowers were in full, self or part time employment statuses. Yet listings in charged off and defaulted statuses is significant at 26.14% combined.

In bivariate exploration, I observed that listing amount distribution is concentrated in lower end of loan values, well below $10,000. This is consistent with my finding in univariate exploration. I also observed that adding a second feature to previously explored features can cause distribution trends to vary, as seen in the two scenarios where `Occupation` and _**`Credit`**_ Ranking were added in turn to listing distribution in the top five borrower states. In both cases, the listing distributions vary from their corresponding distributions in univariate exploration.

In multivariate exploration, I found adding a related new feature to a bivariate distribution did result in the related features strengthening each other. For examples,
- adding a third feature _**Borrower APR**_ to the bivariate distribution of listing amount and credit ranking adds visibility to varying concentrations of listing amounts at different APR rates.

- adding a fourth feature _**Listing Category**_ to multivariate distribution of listing amount and borrower APR by credit ranking enables visibility to segmentation of borrower APR on listing amount and credit ranking by listing category.

- the three features _**Time**_, _**Principal borrowed**_ and _**Delinquent amount**_ enhance each other and yield a clear trend on principal borrowed and linquent amount between 1 July 2008 and 31 December 2009.

- the three features _**Listing amount**_, _**Credit ranking**_ and _**Period**_ enhance each other and enable comparison of listing amount and credit ranking distribution in two different time periods.

- the three feature _**Listing amount**_, _**Listing category**_ and _**Period**_ enhance each other and add visibility to listing amount and listing category distribution in two different time periods.

Through univariate, bivariate and multivariate explorations, I was able to look at features pertaining to Prosper borrowers, loan listings and time periods in the dataset to study their influences on Prosper loan distributions, and see the effect of the three historical significant events on Prosper loan listings between 1 July 2008 and 31 December 2009.

## Key Insights for Presentation
For the presentation, I focused on showing the effects of selective borrower, loan attributes and time series events on Prosper loan listing distributions.

I started with introducing visuals of listing distributions associated with borrower profession, employment status, resident state, listing category, listing status and listing amount in univariate perspective.

Next, I demonstrated how adding an additional attribute to univariate listing distributions can result in variations in listing distributions.

Lastly, I created multivariate visuals by adding APR and time series attributes to bivariate listing distributions, show casing the effects of these attributes on multivariate listing distributions.

## Tool
Jupter Notebook (Python)

## Programming library
panda, numpy, matplotlib, seaborn

## Artifact
- Communicate_Data_Findings-Prosper_Loan_Part1.ipynb, Communicate_Data_Findings-Prosper_Loan_Part1.html
- Communicate_Data_Findings-Prosper_Loan_Part2.ipynb, Communicate_Data_Findings-Prosper_Loan_Part2.html
- Communicate_Data_Findings-Prosper_Loan_Part2.slides.html (`slide show`)
- readme.md
- prosperLoanData_src.csv (for data wrangling use), prosperLoanData.csv (for exploration and explanatory use)

See <a href="https://github.com/atan4583/dand-project-portfolio" target="_blank">code here</a>.

***
## Acknowledgement
Special thanks to the _**legendary**_ Udacity Data Analyst Nanodegree mentor _**Myles Callan**_, whose knowledge competency is impressively splendid, and dedication to serve students, undeniably unparalleled. I have benefited and learned a great deal from his remarkble style of coaching.

Thank you, _**Myles**_, for the privilege to learn from you, you are simply wonderful !!!
