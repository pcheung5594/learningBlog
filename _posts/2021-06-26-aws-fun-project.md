---
layout:       post
title:        "AWS Fun Project"
date:         2021-06-26 9:00:00
author:       "PC"
header-img:   "img/photo-with-title.png"
header-mask:  0.3
hidden: true
catalog:      true
tags:
    - AWS
---

### Amazon Free Tier Project

I really like the idea of the Amazon Free Tier. It allows us to have a chance of getting something started for free. Even though the price of cloud servers nowadays is cheap, it is quite some budget for building something from scratch, and usually takes longer than you may think. Therefore, I would like to take this advantage of the free tier to explore and build something with the resources. I will share some of the pros and cons of the services that I am exploring and why do I ending up choosing one, but not the other.

In this blog, I will try to go through a few different higher level thought process of how I wanted to structure my project and services level comparison of the AWS service of why they are chosen.

### Serverless vs Cloud Server

In the higher-level consideration of my project, I struggle to pick between serverless and owning a cloud server. AWS has a superior Lambda function that runs a serverless function managed by AWS, we only need to apply the code and setup a scheduler, and wola it is done, it runs maybe daily, weekly or monthly just like setting up a cron job in an EC2. Here are some of the things that I considered for my scraper. 

In my project, I will be scrapping some stock data, and it will be separated between historical data and current data. 

![AWS comparison](../../../../img/AWS_explore_001.PNG)

### AWS Setup for my project

I think as a fun project, writing a scraper is probably one of the best and easy project to start with. It leads to a lot of follow up action that could be taking in the next step, such as data analytics, visualization and data processing, etc. Other than building something one-off, it may lead to more continuous fun. I am trying to set up a low-cost database with a pipeline for hoping to create something before I do get a high price charge, as most of the cloud servers are not that cheap. So, this is some of the information that I have gathered for myself to do some comparison on for the services on AWS.

### EC2 vs ECS vs Lambda

/*--TODO--*/

#### What is an EC2?

EC2 in short is a **virtual machine** of in OS level, like Linux or Windows, usually use in a **terminal** like server having all controls starting from the OS to Container all the way to the Applications. It is a very similar experience when you are using your personal computer.

#### What is a ECS?

![ECS](../../../../img/aws_ecs_1.png)

ECS is a **docker image** manager that helps run the docker container on the **serverless** environment of the AWS, including the container (docker image), service (load balancer and security management), and cluster (VPC and subnet) level management. Therefore, you can have the image be a lot more lightweight and can be hands-free from the OS or machine with lesser chance of downtime.

#### What is Lambda?

Lambda is simply code and scheduler. Worry nothing about container or cluster. It costs by **run time** and **network**.

### RDS vs Aurora

/*--TODO--*/

### Glue vs Data Pipeline

/*--TODO--*/

![Data Pipeline](../../../../img/aws_datapipline_1.png)

### AWS Credential

/*--TODO--*/

https://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/setup-credentials.html 