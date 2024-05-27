# React

## What is React? What is the role of React in software development?

React is an open-source library used for building user interfaces. It simplifies the creation of Single-Page Applications (SPAs) by using reusable components.

## What are the key features of React?

- **Virtual DOM**: React utilizes a virtual representation of the DOM, allowing efficient updates by minimizing direct manipulation of the actual DOM, resulting in improved performance.

- **Component-Based Architecture**: React structures user interfaces as modular, reusable components, promoting a more maintainable and scalable approach to building applications.

- **Reusability & Composition**: React enables the creation of reusable components that can be composed together, fostering a modular and efficient development process.

- **JSX (JavaScript XML)**: JSX is a syntax extension for JavaScript used in React, allowing developers to write HTML-like code within JavaScript, enhancing readability and maintainability.

- **Declarative Syntax**: React has a declarative programming style (JSX), where developers focus on "what" the UI should look like and React handles the "how" behind the scenes.

- **Community & Ecosystem**: React benefits from a vibrant and extensive community, contributing to a rich ecosystem of libraries, tools, and resources, fostering collaborative development and innovation.

- **React Hooks**: Hooks are functions that enable functional components to manage state and lifecycle features, providing a more concise and expressive way to handle component logic.

## What is the DOM? What is the difference between HTML and DOM?

DOM stands for Document Object Model. It's a tree-like structure that represents the elements and structure of a web page. HTML is the language used to create the structure and content of your webpage, while the DOM is a programming interface that allows you to interact with and manipulate that structure using languages like JavaScript. HTML is the static blueprint, and DOM is the dynamic, interactive version browsers use to render and update web pages based on user interactions or scripting.

## What is Virtual DOM? Difference between DOM and Virtual DOM?

- **DOM**: Represents the structure and content of a website in the form of a tree. It allows scripts and webpages to manipulate, modify, and identify the components of a website. DOM can be slow for modern websites, which require frequent updates and dynamic content rendering.

- **Virtual DOM**: A copy of the DOM that doesn't display the page of a website in a browser. When there are changes in a web page, updates are first made to the Virtual DOM, which then compares itself to the real DOM to identify specific updates needed, minimizing the number of changes that must be made in the actual DOM. This optimization improves overall web page speed.

## What are React Components? What are the main uses of them?

React components are reusable and self-contained pieces of code that represent different parts of a webpage. They help organize and manage the user interface. Think of them as Lego pieces that can be combined to construct a webpage. Each component has its functionality and can be easily combined with other components to create an interactive user interface. For example, you can have a "Button" component for handling user clicks, a "Header" component for displaying the title of your page, and a "Form" component for collecting user input.

## What is SPA (Single-Page Application)?

A Single-Page Application (SPA) is a type of web application that loads and interacts with content on a single web page without needing to reload the entire page for each action. SPAs use modern web technologies like JavaScript to dynamically update the content on the same page, providing a smoother and faster user experience. SPAs often use frameworks like React, Angular, or Vue.js to manage the dynamic content and enhance user interactivity.

## What are the five advantages of React?

1. Simple to build Single Page Applications by reusing components.

2. React is cross-platform and open-source, making it free to use.

3. Lightweight and swift, thanks to the Virtual DOM.

4. Large community and ecosystem.

5. Easy to test.

## What are the Disadvantages of React?

- React introduces new concepts like JSX, component-based architecture, and virtual DOM, which can be challenging for junior developers to grasp.

- Managing state and props within React components may be confusing for junior developers, especially when dealing with complex applications.

## What is the role of JSX in React?

In React, JSX (JavaScript XML) allows developers to write HTML-like code within JavaScript. Instead of using plain JavaScript to create elements, JSX lets you write HTML-like code. JSX gets transformed into regular JavaScript by a transpilation process before it's rendered in the browser, helping React understand and efficiently update the user interface based on the underlying JavaScript logic.

## What is the difference between Declarative & Imperative syntax?

- **Imperative Syntax**: Gives step-by-step instructions, micromanaging every detail.

  - Example: Instructing a robot to make a sandwich by specifying each action.

- **Declarative Syntax**: Focuses on the result you want to achieve, letting the system figure out how to do it.
  - Example: Instructing a robot to make a sandwich without specifying each action.

Declarative syntax is more focused on what you want to achieve, letting the computer figure out how to do it.

## What is the difference between Component and PureComponent? Give an example where it might break an application.

- **Component**: Renders any time its render function is called, regardless of whether its state or props changed.

- **PureComponent**: Renders only if the state or props differ, using a shallow comparison between the previous state and the new state. Complex objects might still trigger a render due to a possible change in the memory reference.

> Example:
>
> If a child component extending from Component receives a huge array of objects and renders a long list of data, it will re-render any time the parent updates, even if the data is the same, causing performance issues.
>
> Extending from PureComponent might seem to fix the problem, but if the array memory reference changes, the PureComponent will still re-render.

## Why combining Context with ShouldComponentUpdate might be dangerous?

A component whose `ShouldComponentUpdate` function prevents updates also prevents anything below it in the DOM tree from updating, even if another component should update because it’s consuming data from Context. This is no longer a problem in the newer `createContext` API.

## Describe 3 ways to pass information from a component to its parent

1. A child can send data to its parent using a callback function.

2. Using Context.

3. Using a state manager such as Redux.

## Describe 2 ways to prevent components from re-rendering

1. Using `React.memo` or `shouldComponentUpdate` to prevent any component from re-rendering if its props have not changed, by doing a shallow comparison between the previous props and state and the new ones. This is not always effective if the props are functions, objects, or arrays.

2. Making good use of props by passing primitive types when possible and memoized objects, arrays, and functions using `React.useMemo` or `React.useCallback`.

## What is React.Fragment?

`Fragment` is a tool to wrap children components in an element without adding an extra element to the DOM tree.

## What are the differences between Promises, callbacks, and Async/Await functions?

- **Callbacks**: Use the error-first pattern where the callback’s first argument is always the error object.

- **Promises**: Objects that provide methods to handle the different states of an asynchronous function. Handle errors using the `.catch()` method.

- **Async/Await**: Syntactic sugar built on top of promises that help write async code in a sync way, using `try/catch` blocks to handle exceptions.

## How many arguments does setState take and why is it async?

`setState` accepts two parameters:

1. The new state or a callback to update the new state.

2. A callback function that is triggered when the state update is completed.

It is asynchronous because state updates are queued into the JS event loop to allow for synchronous operations to be completed before the state is updated.

## List a few ways to style components

- **Inline styling**: Pass a CSS property object to a component style attribute.

- **CSS Modules**: Define classes in a module and export them into your component, passing those classes to the component’s `className` attribute.

- **CSS-in-JS libraries**: Such as `styled-components`, allowing you to style components directly and more dynamically.

- **CSS frameworks**: Such as Tailwind or Bootstrap, providing predefined styles and classes that can be used across your application.

## How can I render an HTML string?

You can render an HTML string by setting the `innerHTML` attribute of an element to the string. To get the element, you either query it using JavaScript or set the prop `dangerouslySetInnerHTML={{ __html: <html_string> }}`

[Go back](https://github.com/guillermo-segura/tech-interview-questions)
