---
slug: welcome
title: Rendering 3D in React made easy with react-three-fiber
authors: [Samuel]
tags: [github]
---

![R3F-fiber](/img/r3f-fiber.png)

What if I told you… that you too can learn to code in 3D objects in React that can wow customers? Learn the basics of the react-three-fiber renderer, and soon enough, you could be able to turn a static page into an art gallery, an interactive map, or any other metaverse thing.

### Reasons for using a React renderer

3D graphics now create enriched experiences for applications users that allow businesses to reach new waves of customers through memorable visuals. They can represent nearly lifelike products like sneakers or backpacks that can be customized.

Advanced renders can take you on a virtual corporate office tour or even let you complete driving exercises in VR.

From the react-three-fiber projects I’ve seen online, I noticed they aim to make a product/service memorable or understood better. But you can also embrace your frontend skill to simply create an experimental portfolio page as a work of art.

Is it hard to do? Making a scene with Three.js
Normally, you’d be using WebGL — the browser’s API for rendering 3D — which is pretty hard. The list of definitions needed for a regular cube is crazy.

Rendering is easier with a high-level library called Three.js, which allows you to create a 3D environment using a simpler API. Input just a few lines of code and you can create a React project with a plain scene hosting the cube.

To see anything, you need to declare your cube. Pretty simple.

Still nothing? Okay, there is one more step.
![R3F-Skeleton](/img/R3F-Skeletor.jpeg)

### Now, import react-three-fiber

Mixing modern React applications with jQuery-like code is not the best idea to improve code quality. But react-three-fiber (R3F) is our savior here. The renderer is declarative like React, letting you create a self-contained component of a 3D scene without mind-clouding complexity.

Add R3F and Three.js as dependencies to your existing Create React App.

Create a functional component that returns the scene setup with light.

Your scene is almost ready. Now, add the cube, so that we move forward and explore the exciting options that R3F offers.

You’re using a mesh React component that is a wrapper for different Three.js geometries. One of them is boxGeometry which represents the cuboid (or as it says — a box). Add one of the possible Three.js materials simulating depth to see your wonderful baby.

What does the declarative way of creating 3D in React give you? The direct access to all of React’s bells and whistles! You can build custom, self-contained components, use the reactive state, and do everything that React already has in a simple and efficient way.

###How to create a scene with several cuboids
A client walks out of your closet, asking for a simple app with spinning and clickable 3D boxes. The user should be able to control the rotation speed. You need a proof of concept done for lunch (which you pay for). How would you approach the project?

Make usage of the custom Box function component to specify size, color, and speedFactor. The code below assigns a default value to some extra props that can be changed later — no worries.

Use the regular useState statements to track the hovered and active state. Add boxRef to store a reference of your mesh, as it lets you manipulate the object through useFrame callback. Please analyze the code below at your pace until you understand it.

So your scene now uses the awesomely customizable Box component. In order to give the user rotation speed control, add range input to your JSX structure and the useState, which will contain the velocity information.

A small batch of code can hold a lot of wonder! Once you master react-three-fiber, you’ll be ready to play with Three.js and its rich features. And the result?

### React-three-fiber offers awesome developer experience in one pill

The renderer has its own developer experience that goes beyond the declarative style. R3F has outstanding Typescript support that reviews your types at all times.

Performance optimization in R3F is a real game-changer, as the render loop of a three.js scene is completely separated from React’s Virtual DOM.

Besides that, react-three-fiber also has a great ecosystem of utility libraries. There is @react-three/cannon for creating physics-based content or @react-three/drei. The latter offers tons of React three-fiber functions that can save hours on creating a spectacular 3D scene enriched with stunning post-processing effects.

Remember that to produce real results with react-three-fiber, you really should know Three.js by heart.

Instead of rushing to finish react-three-fiber documentation, study the Three.js docs. That will give you that extra confidence while coding. Do that and in the end, you won’t feel like this:

![R3F-Panik](/img/R3F-Panik.jpeg)

But more like this 😄

![R3F-three](/img/three-react.png)
