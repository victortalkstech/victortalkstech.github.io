---
layout: post
title:  "Javascript vs Typescript: A Comprehensive Comparison"
date:   2023-06-29 17:00:00 +0100
categories: scala
---

## Introduction

In the world of web development, Javascript (JS) and Typescript (TS) are two popular languages. At their core, they share many similarities since Typescript is a superset of Javascript. This means that all valid Javascript code is also valid in Typescript. The main difference, as the name suggests, is the addition of static types in Typescript. This article will delve into a comparison between these two languages, looking at their pros and cons, use cases, and code examples.

## Javascript

Javascript is a dynamic, high-level interpreted language mainly used for enhancing web pages to provide a more interactive experience for the user. Developed in 1995 by Brendan Eich while he was an engineer at Netscape, Javascript has become one of the three main technologies of the World Wide Web, alongside HTML and CSS.

### Javascript Code Example

Let's start with a simple example in Javascript.

```javascript
function add(num1, num2) {
    return num1 + num2;
}

console.log(add(5, 10));  // Outputs: 15
```

### Javascript Use Cases

* Client-Side Development: Javascript is the main language for client-side web development. It's used to add interactivity to web pages, including handling user input, manipulating the Document Object Model (DOM), and implementing AJAX for asynchronous web requests.
* Server-Side Development: With the advent of Node.js, Javascript has made its way to the server-side. Developers can now write the frontend and backend of web applications in the same language, which can streamline development and reduce context switching.
* Mobile App Development: Frameworks such as React Native and Ionic allow developers to use Javascript for building mobile applications.
* Desktop App Development: Using technologies like Electron, Javascript can also be used to build cross-platform desktop applications.

### Javascript Pros and Cons

#### Pros

* Ubiquitous: Javascript is supported by all modern web browsers without the need for any plugins or compilations.
* Versatility: It can be used for both frontend and backend development, allowing for full-stack development with a single language.
* Community Support: Javascript has a large, active community and an extensive ecosystem of libraries and frameworks, making it easier to find help and resources.

#### Cons

* Lack of Static Typing: Without static typing, errors can often go unnoticed until runtime. This can make debugging more difficult and time-consuming.
* Inconsistencies: The Javascript language has some quirks and inconsistencies that can lead to confusion and mistakes.

## Typescript

Typescript, developed and maintained by Microsoft, is a statically typed superset of Javascript that compiles to plain Javascript. It was designed to help developers write more robust code and manage large-scale projects better.

### Typescript Code Example

Here's the previous example rewritten in Typescript with types added.

```typescript
function add(num1: number, num2: number): number {
    return num1 + num2;
}

console.log(add(5, 10));  // Outputs: 15
```

In this example, we specify that `num1` and `num2` should be of type `number`. If we try to pass arguments of any other type to the `add` function, the Typescript compiler will throw an error.

### Typescript Use Cases

Typescript is used in much the same way as Javascript, but it's particularly beneficial in larger codebases and teams.

* Large-Scale Applications: The static typing system allows for better tooling (like autocompletion and compile-time error checking), making it easier to navigate and refactor large codebases.
* Angular Development: Typescript is the primary language for Angular, a popular JavaScript framework developed by Google.
* Named Tuples: TypeScript introduced the concept of named tuples, which are like advanced arrays with extra features that ensure type safety, particularly when we need to account for a list containing a fixed number of elements with multiple known types. These named tuples provide a structured approach for defining data with named properties, enhancing code readability, and making your intentions explicit by assigning names to the properties. Tuples are especially handy when you need to represent a sequence of values such as coordinates (x, y) or RGB color values (red, green, blue).

### TypeScript Pros and Cons

#### Pros

* Static Typing: TypeScript's static type system allows for better autocompletion, tooling support, and compile-time error checking. This can help catch errors early in the development process.
* Better for Large Codebases: TypeScript is great for large projects because it makes it easier to refactor code and navigate large codebases.
* Superset of JavaScript: TypeScript includes all JavaScript features, so any valid JavaScript code is also valid TypeScript code. This makes it easier for JavaScript developers to transition to TypeScript.

#### Cons

* Requires Compilation: TypeScript code must be compiled to JavaScript before it can run in a browser. This adds an extra step to the development process.
* Learning Curve: While TypeScript is based on JavaScript, it introduces static typing and other features that require time to learn.
* More Verbose: TypeScript's type annotations can make the code more verbose.

## Conclusion

In summary, JavaScript and TypeScript are both powerful languages for web development, each with its own strengths and trade-offs. JavaScript is versatile and universally supported, making it a good choice for a wide range of projects. On the other hand, TypeScript's static typing and other features can make it a better choice for larger, more complex projects, or those that require stricter type safety. The choice between the two often comes down to the specific needs and constraints of your project.
