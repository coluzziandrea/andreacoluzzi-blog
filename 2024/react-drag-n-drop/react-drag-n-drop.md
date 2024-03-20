---
title: Drag and Drop feature in React
subtitle: How to Implement Drag and Drop feature without using any library
slug: react-drag-n-drop
tags: react, javascript, frontend, css, html5
domain: https://coluzziandrea.hashnode.dev/
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1710956698520/fxKilWoCT.png?auto=format
canonical: https://coluzziandrea.hashnode.dev/react/react-drag-n-drop
seoTitle: Drag and Drop feature in React
seoDescription: How to Implement Drag and Drop feature without using any library
seriesSlug: react
enableToc: true
saveAsDraft: false
---

# Drag and Drop feature in React

> How to Implement Drag n' Drop feature without using any library.

## Introduction

In this blog post, I will show you how to implement a simple Drag and Drop feature in a React application without using any library.

### Why Drag and Drop?

The Drag and Drop feature is a common interaction pattern that allows users to move elements around the page. It is a great way to make your application more interactive and user-friendly.

## Getting Started

To implement the Drag and Drop feature, we will use the [HTML5 Drag and Drop API](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API). This API provides a set of events and methods that allow you to create a custom Drag and Drop behavior.

### Step 1: Create a new React application

First, let's create a new React application using Create React App.

```bash
npx create-react-app drag-n-drop --template typescript
```

And let's navigate to the newly created project.

```bash
cd drag-n-drop
```

Now we can start the development server.

```bash
npm start
```

This will start the development server and open the application in your default web browser.

Now that we have our React application set up, let's move on to the next step. But before, let's open our project in our favorite code editor. I personally use Visual Studio Code, but you can use any code editor you prefer.

```bash
code .
```

### Step 2: Create a Draggable component

Next, let's create a new component called `Draggable` that will represent the draggable element.

We'll create it in the `src` folder.

```tsx
import React from 'react'

const Draggable: React.FC = () => {
  return (
    <div
      className="draggable"
      draggable
      onDragStart={(e) => {
        e.dataTransfer.setData('text/plain', 'Hello, World!')
      }}
    >
      Drag me!
    </div>
  )
}

export default Draggable
```

In this component, we use the `draggable` attribute to make the element draggable. This [attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/draggable) will tell the browser that the element can be dragged.

We're also reacting to the `onDragStart` [event](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/dragstart_event).
This event is fired by the Drag n Drop API when the user starts dragging the element and can be used to set some properties of the drag operation.

For example, we use the `setData` [method](https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/setData) of the `dataTransfer` object (that is coming directly from the event itself) to set the data that will be transferred when the element is dragged.

This works by setting the data type and the data itself. In this case, we set the data type to `text/plain` and the data to `Hello, World!`.

to set the data that will be transferred when the element is dragged.

Also, we're setting the class name of the element to `draggable` to style it later.

### Step 3: Create a Droppable component

Next, let's create a new component called `Droppable` that will represent the droppable area.

We'll create it in the `src` folder.

```tsx
import React from 'react'

const Droppable: React.FC = () => {
  return (
    <div
      className="droppable"
      onDragOver={(e) => {
        e.preventDefault()
      }}
      onDrop={(e) => {
        e.preventDefault()
        const data = e.dataTransfer.getData('text/plain')
        console.log(data)
      }}
    >
      Drop here!
    </div>
  )
}

export default Droppable
```

In this component, we're reacting to the `onDragOver` [event](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/dragover_event).

This event is fired by the Drag n Drop API when the user drags an element over a valid drop target and can be used to specify what happens when the element is dragged over the target.

In this case, we're calling the `preventDefault` [method](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault) of the event to prevent the default behavior of the browser, which is **to not allow dropping**.

> This is very important, because by default, the browser does not allow dropping elements on other elements. So we need to call `preventDefault` in the onDragOver handler to allow the onDrop handler to be fired.

We're also reacting to the `onDrop` [event](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/drop_event).

This event is fired by the Drag n Drop API when the user drops an element on a valid drop target and can be used to specify what happens when the element is dropped.

In this case, we're still calling the `preventDefault` and then we're using the `getData` [method](https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/getData) of the `dataTransfer` object to get the data that was set when the element was dragged.

Also, we're setting the class name of the element to `droppable` to style it later.

### Step 4: Use the Draggable and Droppable components

Now that we have our `Draggable` and `Droppable` components, let's use them in the `App` component.

We'll open the `App.tsx` file and replace its content with the following code.

```tsx
import React from 'react'
import './App.css'

import Draggable from './Draggable'
import Droppable from './Droppable'

const App: React.FC = () => {
  return (
    <div className="container">
      <Draggable />
      <Droppable />
    </div>
  )
}

export default App
```

In this component, we're using the `Draggable` and `Droppable` components that we created earlier. We're also setting the class name of the container to `container` to style it later.

### Step 5: Style the Draggable and Droppable components

Now that we have our components set up, let's style them.

We'll open the `App.css` file and replace its content with the following code.

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 2rem;
  height: 100vh;
}

.draggable {
  padding: 16px;
  background-color: #f0f0f0;
  cursor: move;
}

.droppable {
  padding: 16px;
  background-color: #f0f0f0;
  cursor: pointer;
}
```

In this file, we're styling the `container`, `draggable`, and `droppable` elements.

### Step 6: Test the Drag and Drop feature

Now that we have our components set up and styled, let's test the Drag and Drop feature.

We can do this by dragging the `Draggable` element and dropping it on the `Droppable` element.

When we do this, we should see the data that was set when the element was dragged logged to the console.

If everything is working correctly, you should see `Hello, World!` logged to the console, like the following:

![Demo](https://cdn.jsdelivr.net/gh/coluzziandrea/andreacoluzzi-blog/2024/react-drag-n-drop/assets/demo_1.gif)

The Drag and Drop feature is now working correctly! 🎉
The two components are indeed communicating with each other, and the data is being transferred from the draggable element to the droppable element. Starting from this simple example, you can build more complex interactions and behaviors.

## Conclusion

In this blog post, we learned how to implement a simple Drag and Drop feature in a React application without using any library. We used the HTML5 Drag and Drop API to create a custom Drag and Drop behavior and we created a `Draggable` component and a `Droppable` component to represent the draggable element and the droppable area.

I hope you found this blog post helpful and that you learned something new. If you have any questions or feedback, feel free to reach out to me on [Twitter](https://twitter.com/andreacoluzzi94). I'm always happy to help!

You can see the final code on [my GitHub profile](https://github.com/coluzziandrea/react-drag-n-drop)
