---
title: "Deploy an AI Sentiment Prediction App to AWS"
date: 2020-02-21 00:00:00 +0000
tags: [AWS Cloud]
categories: [Post]
excerpt: Transforms the original infrastructure of an AI sentiment prediction app (trained on the RNN model) to an AWS cloud deployable infrastructure.
mathjax: "true"
thumbnail: "/images/Project7-aiAppOnAWS/Rnn.png"
---

$$\Rightarrow$$ <a href="http://ai-frontend.s3-website-us-west-2.amazonaws.com/" target="_blank"><b>Project Website</b></a>

# Project Information
This project transforms the original infrastructure of an AI sentiment prediction app (trained on the RNN model) to an AWS cloud leveraging various AWS cloud stack concepts covered in Phase I of Udacity | Bertelsmann Technical Scholoarship Cloud Track Challenge, i.e. S3, Lambda, Elastic Load Balancer, Auto Scaling Group, Cloudformation and IAM; as well as advanced concepts like Serverless Framework, CI/CD, Docker, API Gateway, ECS, DockerHub, DynamoDB and Microservices.

![png](/images/Project7-aiAppOnAWS/cicdworkflow.png)

## Project Team
There team members from Phase I of the Cloud Track Challenge:
-  <a href="https://github.com/Adriks976" target="_blank">Adrik S (France)</a>
-  <a href="https://github.com/atan4583" target="_blank">Audrey ST (USA)</a>
-  <a href="https://github.com/christopherrauh" target="_blank">Christopher R (Germany)</a>

## How to use AI Sentiment Prediction App
### Scenario I
![png](/images/Project7-aiAppOnAWS/UC1a.png)
   1. User enters a text in the web UI and click Submit button to get a sentiment prediction result
   2. The RNN model returns a label (e.g. guilt) representing the predicted sentiment, which user can approve or revise

![png](/images/Project7-aiAppOnAWS/UC1b.png)
   3. User clicks `Approve` button to accept the prediction result. The result is recorded to the DynamoDB

### Scenario II
![png](/images/Project7-aiAppOnAWS/UC2a.png)
   1. The RNN model prediction result returned does not quite match the user’s expectation. The user can click one of the seven available labels to override the returned result

![png](/images/Project7-aiAppOnAWS/UC2b.png)
   2. User clicks ‘joy’ label to override the returned result ‘sadness’. The revised result is recorded to the DynamoDB

### Scenario III
![png](/images/Project7-aiAppOnAWS/UC3a.png)
   1. All previously approved and revised prediction results are stored in the DynamoDB. The data can be exported to a csv file from the Web UI as a new dataset for retraining the RNN Sentiment Prediction model

![png](/images/Project7-aiAppOnAWS/UC3b.png)
   2. User accesses the csv file download endpoint to download prediction results stored in the DynamoDB. This csv file can then be used as a new dataset for retraining the RNN Sentiment Prediction model

## Original Infrastructure (Logical View)
![png](/images/Project7-aiAppOnAWS/architecture-orig.png)
The original architecture of the AI app consists of:
- a Flask app backend hosting a RNN sentiment prediction model
- a website with a Vue Web UI powered by `Springboot Framework`
- a datastore built on MySQL DB
It is styled in Microservices fashion. This makes the infrastructure and its underlying components easily transformable to AWS cloud deployable infrastructure.

## Cloud Infrastructure (Logical View)
![png](/images/Project7-aiAppOnAWS/architecture-cloud.png)
The transformation resulted in a streamlined infrastructure as below:
- the Flask backend now runs in a docker container and utilizes AWS ECS
- the website is now hosted on S3 bucket powered by AWS Lambda functions
- the MySQL datastore is now replaced by a light weight noSQL DynamoDB
The new AWS cloud infrastructure comes with these benefits:
- costly specialist support effort in Springboot, MySQL, Infrastructure resource deployment & provisioning no longer needed
- built-in auto failover and user demand driven infrastructure scaling features
- predictable operation performance with minimum effort and improved overall user experience

## Cloud Infrastructure Deployment Workflow
![png](/images/Project7-aiAppOnAWS/depoywf.png)
- DevOps team merges feature branches to the master branch and pushes to one of the three remote masters
- Code build - three build paths:
   1. If the push is onto `ai-frontend` repo, CI/CD Action _*Upload Website*_ automatically runs to upload updated static files (index.html, app.js) to AWS S3 website `udacity-ai-frontend`
   2. If the push is onto `ai-backend` repo, CI/CD Action _*Deploy to Amazon ECS*_ automatically runs to build a new Flask container to push to the DockerHub, then deploys a new ECS task definition to start container operation on AWS cloud
   3. If the push is onto `ai-automation` repo, CI/CD Action _*Serverless deployment*_ automatically runs a serverless.yml configuration file to deploy Lambda functions, their triggering events and required infrastructure resources (DynamoDB, API Gateway and S3) to AWS and rebuild the website

## Cloud Infrastruture Operation Workflow
![png](/images/Project7-aiAppOnAWS/opswf.png)
- RNN Sentiment Prediction App Operation
   a. User submits a sentiment prediction request thru website UI and receives a result
      - User approves the prediction result, the approved result is written to the DynamoDB
      - User revises the prediction result, the revised result is written to the DynamoDB
   b. User downloads prediction results stored in the DynamoDB as a CSV file for use as a new dataset for retraining of the RNN model
   c. Depending on website traffic, AWS ECS and Auto Scaling group orchestrate to scale up to 3 Flask container instances to optimize workload distribution and app response time

## Tool
NodeJS, Python, Flask, AWS(S3, Lambda, ELB, ASG, Cloudformation, IAM, API Gateway, ECS, DynamoDB, Severless Framework), Docker, GitHub Action

## Code Artifact
-  <a href="https://github.com/bertelsmann-cloud-challenge-collaborate/ai-frontend" target="_blank">ai-frontend repo</a>
-  <a href="https://github.com/bertelsmann-cloud-challenge-collaborate/ai-automation" target="_blank">ai-automation repo</a>
-  <a href="https://github.com/bertelsmann-cloud-challenge-collaborate/ai-backend" target="_blank">ai-backend repo</a>
