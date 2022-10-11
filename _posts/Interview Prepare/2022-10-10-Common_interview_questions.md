---
title: Common Interview Questions
date: 2022-10-10 00:00:00 -500
categories: [Interviews]
tags: [] # TAG names should always be lowercase
img_path: /assets/posts/
---

## 自我介绍

After graduation from college, I was a materials science researcher. My research focus was mechanical properties simulation, and I published 1 paper and 2 patents.

During my study at Columbia University for my master's degree, I was fascinated by the power of python. After learning some data science stuff, I decided to devote myself to software development.

Most recently, I was working as a fullstack engineer and our team was working on an open source product called Contractual. I was mainly responsible for the backend development, like designing REST APIs, designing databases and writing unit tests.

Last year, I was a frontend developer intern at Boston Software Group. My main duty was to build a website with React. So I'm familiar with the frontend tech stack, like HTML, CSS and JavaScript.

In my work, I have integrated CI/CD pipeline for reduced risk and a smoother path to producation.

Recently, I'm getting more experience on AWS, and I'm a AWS certified Cloud Practitioner.

In my free time, besides taking care of my cat and turtles, I'm running a close-knit coding community. We do some data structure and algo challenges and pair programming every weekend.

To conclude, I believe my skill set, espeically my xxx and xxx knowledge will help me to be a good fit for this position.

## Git Experience

Let’s say we have a repository hosted on Github, and it has a main branch. What I will do is to fork it and create a feature branch. I will make my changes on this branch

Once I finish, I would like to merge this feature branch into the main branch. In order to do this, I will submit a PR. Other engineers would review my PR, comment on it, and approve it if they it is good.

To make the merge safer, we can add some rules to protect the branch. For example, the deployment must succeed before merging, and we need at least two approvals.

## CI/CD Experience

Github actions is a CI/CD platform and I can give you an example of how I used it.

Every time I submit a PR, I would like to guarantee the build is successful and all tests can pass. Then when merging, I also need to build a docker image and push the image to Docker Hub.

I created a `.yml` file in the `.github/workflows` folder. The file would contain events, jobs, runners, steps and actions.

In the `.yml` file, we have the `on` section, specifying when we want to run these jobs, like when we push to the main branch or there is a PR to the main branch. We also have the `jobs` section, where we can set up the workflow. For example, we let it run on Ubuntu, with node version 12/14/16, and some commands to run. If we would like to do some unit tests, then we have `npm install` and `npm run test`. If we would like to release it, we can run `docker build`, and `docker push`.

Github Actions provide a lot of templates,based on various purposes, and they're pretty handy and helpful.

## TDD

In TDD, tests are written before we code. We keep coding to make the program pass more tests.

I can give you an example of how I used TDD. One of the key features of our app is it first asks user to define their data contract. After that, every time the user test their API, we check if the request follows the data contract.

First, I converted the requirements into some unit tests. Let's say, in the data contract, for the POST request sent to `/users`, the request body must contain a field `username`, which is a string; and a field `hobbies`, which is an array. For example, the app should return an error message if `username`turns out to be a number in the request body. The test should return passed if it is a string.

The first time I run the tests, they were expected to return failed for most cases, because no functionality has been added.

Then I implemented some functions to check strings. After that, the string tests should all pass, while others still failed.

Then I implemented functions to check arrays. After that, more test cases should pass.

I did it again and again until all of them got a pass.
