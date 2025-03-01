---
title: React Concepts
date: 2022-06-07 12:00:00 -500
categories: [Frontend]
tags: [React] # TAG names should always be lowercase
img_path: /assets/posts/
---

## 1. What's React

React is an open-source front-end JavaScript library that is used for building user interfaces, especially for single-page applications. It is used for handling view layer for web and mobile apps. So it's good at handling the page rendering in response to the change of data. However, it's not good at passing values among components, and that's why we need Redux to assist development.

## 2. Major features of React

- JSX(JavaScript Syntax Extension)
  JSX is a combination of HTML and JavaScript. You can embed JavaScript objects inside the HTML elements.JSX makes codes easy and understandable. It is easy to learn if you know HTML and JavaScript.
- Virtual DOM
  It uses VirtualDOM instead of RealDOM, considering that RealDOM manipulations are expensive.
- One-way data flow
  Follows Uni-directional data flow or data binding.
- Components
  React is component-based and it divides the web page into multiple components. Each component is a part of the UI design which has its own logic and design, so it runs faster and can be reusable.

## 3. VirtualDOM

Usually, JavaScript Frameworks updates the whole DOM at once, which makes the web application slow.
But react uses virtual DOM which is a JS object to descirbe the real DOM.

### Reconciliation

Whenever there is a modification in the web application, the whole virtual DOM is updated first and finds the difference between real DOM and Virtual DOM.

Once it finds the difference, then DOM updates only the part that has changed recently and everything remains the same.

### Diffing Algorithm

Two assumptions:

- Two elements of different types will produce different trees.
- The developer can hint at which child elements may be stable across different renders with a `key` prop.

Compare the root element. If they're different types, then discard the old tree and build a new one. If they're the same type, React looks at the attributes of both, keeps the same underlying DOM node, and only updates the changed attributes.

The `key` prop can help compare faster. You can pass an item’s index in the array as a key. This can work well if the items are never reordered, but reorders will be slow.

### Benefits

- Better performance. The cost of creating JS objects is much less than creating a DOM. Comparing JS objects is also faster.
- Cross-platform applications. For native apps, there is no DOM. But they can read virtual DOM, and convert them into components.

### DOM

Document Object Model. It's a language independent interface. It treats HTML/XML document as a tree.

## 4. Data flow in React

React implements one-way data flow using props, from top to bottom. Parents can pass values to children, while children cannot return value to parents. If we still need to change it in the child component, then we need to pass parent's method which can change the value to the child, and invoke that method in the child component.

This keeps everything modular and fast. It's also easier to read and debug. Because in the two-way mode, it's usually not easy to know which child is changing the value.

## 5. Lifecycle methods

[Details](https://blog1.westagilelabs.com/react-lifecycle-methods-9faf9b434dbe)
![](frontend_lifecycle_of_components.png)
_Lifecycle of Components_

## 6. Server Side Rendering Vs Client Side Rendering

The main difference is that for SSR your service response to the browser is the HTML of your page that is ready to be rendered,while for CSR the browser gets a pretty empty documents which links to your javaScript.

|      | SSR                                                                                                                         | CSR                                                                                                                                                              |
| ---- | --------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Pros | - Search engines can crawl the site for better SEO<br />- The initial page load is faster<br />- Great for static sites.    | - Rich site interactions<br />- Fast website rendering after the initial load<br />- Great for web applications<br /> - Robust selection of JavaScript libraries |
| Cons | - Frequent server requests<br />- An overall slow page rendering<br />- Full page reloads<br />- Non-rich site interactions | - Low SEO if not implemented correctly<br />- Initial load might require more time<br />- In most cases, requires an external library                            |

## 7. Functional vs Class components

- Syntax. Just like in their names, a functional component is just a plain JavaScript function that returns JSX. A class component is a JavaScript class that extends `React.Component` which has a render method.
- They are called stateless function components because they just take props as an argument and return a react element. They don’t manage state and don’t have a lifecycle, while class components do.
- The major difference is the syntax. It relates to the way we declare components, pass props, handling states, manage lifecycle.
- Function components capture the props and state by default. It is not a bug, but a feature of functional components.
- Functional components require less code to write an equal component. However, that doesn’t mean that functional components more readable and convenient to use. If a developer is used to work with object-oriented programming, he finds using class components much more comfortable. Those who are used to functional programming like functional components more than class components.
