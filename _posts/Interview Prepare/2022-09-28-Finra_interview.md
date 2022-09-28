---
title: FINRA Interview Preparation
date: 2022-09-03 00:00:00 -500
categories: [Interviews]
tags: [] # TAG names should always be lowercase
img_path: /assets/posts/
---

# Selenium Questions

## 1. Challenges with Selenium

- No support for non-web automation
- Timeout or Sync issues
- Test execution slowness in IE
- Limited reporting

## 2. New Selenium 4 features

- webdriver
- Selenium IDE support for Chrome
- Selenium grid
- Taking screenshots at the element level, section level and page level
- Support of relative locators

## 3. WebDriver.findElement() vs WebElement.findElement()

- driver is finding the element from the entire page
- webelement is searching in itself and its children

## 4. Page object model vs Page factory

Both are Selenium design pattern.

POM is a repository where we store all the webElements. If UI changes, we update WebElements to Page class in POM.

PF is similar to POM, the difference is the way we define locators.

## 5. Locators supported

- ID
- CSS Selector: tags and attributes
- XPath: Search in the DOM, reliable but slow
- Name: same as ID, but it is not unique
- Classname
- TagName
- LinkText
- Partial LinkText

## 6. StaleElementReferenceException

You grab webElements in a page, and then go to another page, then all these elements would be **stale** (outdated). Even you come back again to this page, they cannot be used.

## 7. Difference between XPath and CSS Selector

- XPaths is slower
- XPath supports text, while CSS Selector cannot
- XPath can move in both forward and backward, while CSS Selector can only move forward



# API Testing

## 1. Challenges under API testing

- API documentation

  data contracts

- Access to DB

  when API is from third party, their database details are not shared.

- Authorization overhead

  authorization and authentication involved

## 2. Difference between PUT and POST methods

- POST: Creating new objects on the server
- PUT: Update the object in server with new value

## 3. Authentication techniques used in APIs

- Session/ Cookie based authentication

- Basic authentication

  username + password

- Digest authentication

  A hash of the credentials is sent over the wire.

- OAuth

## 4. What is REST API

Representational State Transfer. It is a set of functions helping developers in performing requests and receive responses. Interactions are made through HTTP Protocol.

## 5. What needs to verify in API testing

- the accuracy of the data
- HTTP status code
- error codes
- response time
- non-functional testing such as performance testing and security testing