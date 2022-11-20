---
layout: post
title:  Automating myself out of a job
date:   2022-11-01 10:05:00
description: I've automated a large chunk of my contract job. Here's the journey to near full automation and my main learnings.
# tags: formatting links
# categories: sample-posts
---
This is what I've designed and built recently to automate myself out of a role:

{% include figure.html path="assets/img/2021-11-01/chnnlreport.png" class="img-fluid rounded z-depth-1" %}

The architecture diagram above shows a reporting workflow I've developed on AWS, a major step towards near automation of a feature that we have attempted to automate for 2.5 years at [chnnl](https://chnnl.app/home). At the tail end of this automation, I can proudly report some technical and business learnings from having embarked, and at times, led this massive project. I'm i'm planning to write separate posts breaking down my engineering learnings, we'll focus on my product development learnings in this post. There's a few things to be learnt from seeing a SaaS product evolve and mature over the years that I hope might get you thinking about the journey of any similar product(s) you're creating.

## Context

Roughly 2.5 years ago, when I joined the smart and ambitious team at chnnl, they were doing reporting work that the mental health advocate in me loved. They were anonymously collecting self-volunteered workplace wellbeing data from app users who were employees of various NZ-sized businesses, then summarising key insights from this data to feed back to company leadership to help improve workplace cultures.

This reporting was a key part of chnnl's service offering and I was tasked to generate it monthly for clients. It collated data from the chnnl app, applied transformations and summaries, and for a while, machine learning on the data, to generate insights. The final product was a report in PDF form, which would be taken to boardrooms, presented and discussed with executives, and was the starter to conversations around how companies could improve the wellbeing of their employees. It was crucial to produce, on demand, an accurate, insightful and visually pleasing report that championed how employees felt about their work. The report had to be flexible to accommodate changing requirements for what to include in it too -- some from customer feedback, and some from the availability of customer data as employees engaged with the chnnl app to varying extents.

## The Reporting Journey

How the report was generated over the years changed as we learned more about what customers wanted, narrowed down who chnnl is and stands for, and had various engineers come and go, each offering different skillsets and ideas on how to make the report better. As with all things in startup world, we started producing the report very manually until we felt the increasing need to automate.

V1
- querying a database, downloading the files, preprocessing them with transformation scripts, loading the preprocessed data to powerbi, then generating the PDF report

I joined at V1, when the PowerBI report mostly produced summaries of the data and there was little automation in the ETL process to generate the report. The team had ideas of what the report should contain, and a fellow intern, and the only "data" person at the time produced the report in PowerBI, a tool they were very good at. Chnnl only had a few clients, and we were producing only a few reports every month between me and the other intern, manually repeating the above process. No biggie. 

My first learning started here though: often, a tool or technology used to solve a business need, like PowerBI in this case, is used because it's the preferred choice of the people doing the job. PowerBI is extensible, but not as scalable or automatable as a 

V1

V2

V3

V4

V5

Takeaways I want to write about:
-Stick long enough in a company and you see how the product changes, why, be involved in the transition as well. You learn what a product development journey looks like and what is a successful product development move and otherwise
-Repetitive, deterministic tasks that can be broken down into very concrete steps can be automated. Even something as creative as a report can be automated. 
-My criterion for automating something: is important for the business (contributes directly to revenue) and therefore is a stable feature, one that users for the foreseeable future will want, deterministic and can therefore be codified, when devs are doing the repetitive work of generating something. 
-Make initial architecture as flexible as possible, so automation is easier down the line (give example of R being report language of choice)
-I will endeavour to be as flexible in my architecture as much as possible, and be strict about automating manual parts of the dev process. Saves time, helps reproducibility because everything is codified if there is automation. Eg: ci/cd in mlops, running docker containers locally, IaC, 