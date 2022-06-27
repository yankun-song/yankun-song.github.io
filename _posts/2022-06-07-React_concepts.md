---
title: React Concepts
date: 2022-06-07 12:00:00 -500
categories: [Frontend]
tags: [React] # TAG names should always be lowercase
img_path: /assets/posts/
---

1. ## What's React?

React is an open-source front-end JavaScript library that is used for building user interfaces, especially for single-page applications. It is used for handling view layer for web and mobile apps. So it's good at handling the page rendering in response to the change of data. However, it's not good at passing values among components, and that's why we need Redux to assist development. 

2. ## Major features of React?
- It uses VirtualDOM instead of RealDOM, considering that RealDOM manipulations are expensive.
- Supports server-side rendering.
Follows Unidirectional data flow or data binding.
Uses reusable/composable UI components to develop the view.


3. ## Data flow in React?

React implements one-way data flow using props. Parents can pass values to children, while children cannot pass value to parents. If we still need to change it in the child component, then we need to pass parent's method which can change the value to the child, and invoke that method in the child component.

This reduces boilerplate and is easier to understand and debug than traditional two-way data binding. Because in the two-way mode, it's usually not easy to know which child is changing the value. 