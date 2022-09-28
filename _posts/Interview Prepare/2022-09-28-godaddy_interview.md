---
title: GoDaddy Interview Preparation
date: 2022-09-03 00:00:00 -500
categories: [Interviews]
tags: [] # TAG names should always be lowercase
img_path: /assets/posts/
---

## 自我介绍

Previously, I was working as a fullstack engineer and our team was working on a Postman-like, open source product called Contractual. I was mainly responsible for the backend development, like designing REST APIs, designing databases and writing unit tests with `Jest`. 

Last year, I was a frontend developer intern at Boston Software Group. My main duty was to build a website with React. So I'm familiar with the frontend tech stack, like HTML, CSS and JavaScript.

I have some hands-on experience using AWS, and I'm a AWS certified Cloud Practitioner.

Before being a developer, I had some experience in web scraping and data mining using Python.

Recently, I'm doing some Selenium and Cucumber projects, and my past experience helped me a lot. I believe I'm a good fit for this position.

## 如何定位Username/ Password

Selenium supports several locators such as ID, XPath, CSS, className and tagName. 

Personally, I prefer to use CSS selectors and XPath.

I would open chrome developer tools to inspect the elements. If it has a unique attribute like id or classname, then I can use the CSS selectors. Otherwise, I will check if I can locate its parent or siblings. 

## 定时任务

In order to run tasks at pre-determined times or intervals, there are several ways.

We can write a script, and then schedule cron jobs to execute the script periodically.

Or we can create asynchronous tasks with Celery and RabbitMQ.

Personally, I think the best approach is to use some existing tools. For example, Amazon has their cloud watch system. `Postman Monitor` can run a collection of API tests periodically and check its performance and response. 

If we have not only API tests, but also some other unit tests, we can use `Jenkins` and create some triggers. 

Such ways are easier to implement, and can generate reports automatically.

## Git Workflow

Let’s say we have a repository hosted on Github, and it has a main branch. What I will do is to fork it and create a feature branch. Inside this branch, I will make my changes. 

Once I think I have finished, I would like to merge this feature branch into the main branch. In order to do this, I will submit a PR. Other engineers would review my PR, comment on it, and approve it if they it is good.

To make the merge safer, we can add some rules to protect the branch. For example, the deployment must succeed before merging, and we need at least two approvals.

## Github Actions

Github actions is a CI/CD platform and I can give you an example of how I used it.

Every time I submit a PR, I would like to guarantee the build is successful and all tests can pass. Then when merging, I also need to build a docker image and push the image to Docker Hub.

I created a `.yml` file in the `.github/workflows` folder. The file would contain events, jobs, runners, steps and actions.

In the `.yml` file, we have the “on” section, specifying when we want to run these jobs, like when we push to the main branch or there is a PR to the main branch. We also have the “jobs” section, where we can set up the workflow. For example, we let it run on Ubuntu, with node version 12/14/16, and some commands to run. If we would like to do some unit tests, then we have `npm install` and `npm run test`. If we would like to release it, we can run `docker build`, and `docker push`.

Github Actions provide a lot of templates,based on various purposes, and they're pretty handy and helpful.

## TDD

In TDD, tests are written before we code. We keep coding to make the program pass more tests.

I can give you an example of how I used TDD. One of the key features of our app is it first asks user to define their data contract. After that, every time the user test their API, we check if the request follows the data contract. 

First, I converted the requirements into some unit tests. Let's say, in the data contract, for the POST request sent to `/users`, the request body must contain a field `username`, which is a string; and a field `hobbies`, which is an array. For example, the app should return an error message if `username`turns out to be a number in the request body. The test should return passed if it is a string. 

The first time I run the tests, they were expected to return failed for most cases, because no functionality has been added. 

Then I implemented some functions to check strings. After that, the string tests should all pass, while others still failed.

Then I implemented functions to check arrays. After that, more test cases should pass.

I did it again and again until all of them got a pass.



## Page Object

Page object is a design pattern for enhancing test maintenance and reducing code duplication. 

A page object is an object-oriented class that serves as an interface to a page. The tests use the methods of this page object class when they need to interact with the UI of that page.

If the UI changes, the tests themselves don't need to change, only the code within the page object needs to change.



## Cucumber

- BDD

  BDD is a development approach that involves the use of common language to enhance the communication between tech and non-tech teams. 

  Tests are more user-focused and based on the system’s behavior. 

  “Given-When-Then” is a proposed way of writing tests. Precondition- Action- Outcome.

- Gherkin

  Gherkin is a set of rules to make plain text structured enough so Cucumber can understand.

  When we do BDD, we use concrete examples to specify what we want the software to do.

  <img src="https://lh3.googleusercontent.com/DeWTm7ky_2XRQi6FKWrlA5ToHV-lTsSDpaFinSp9jT5Hy9WAxla7qB85vwXU4YiV6NTjPn8tDv6-OcLqQEe-5UJSBn8qvYYJQcDVyLfRS3ULEUn0xOGU5aKpBnJ5R5__rQ0amHt0DwP5bdecFGm2dCC-gRYdaZjgL-vTRvYUWd4jTu_Dk01HWk4qlQ" alt="img" style="zoom:33%;" />

- Selenium

  Selenium is the tool to design web automation tests, and cucumber helps to design framework (run and maintain) of Selenium tests.

- Scenarios

  In Cucumber, `test cases` are represented as `scenarios`. A scenario, is a concrete example illustrating how the software should behave.

  Scenarios contain `steps` which are equivalent to test steps, and use Gherkin keywords to denote them: `Given`, `When`, `Then`, `But`, `And`.

- Feature and Feature File

  Feature represents business requirement.

  Feature file acts as a test suite which consists of all scenarios.