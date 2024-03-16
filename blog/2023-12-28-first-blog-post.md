---
slug: first-blog-post
title: How to Build Interactive Graphics with React Three Fiber
authors:
  name: Samuel Emmanuel
  title: Technical writer and Front-End Engineer
  url: https://github.com/emmz3230
  image_url: https://github.com/emmz3230.png
tags: [github]
---

![R3F-img](/img/r3f-img.png)

React Three Fiber (R3F) is a powerful tool that brings the world of 3D into React. It's a React renderer for ThreeJS on the web and React Native. It allows developers to declaratively create custom elements, manage them in the React way, and take advantage of React's ecosystem.

React Three Fiber is not a wrapper for ThreeJS, but a reconciler (similar to ReactDOM and React Native). It bridges the gap between the declarative React world and the imperative ThreeJS world, allowing you to write ThreeJS code in a React-ish way.

TypeScript, on the other hand, is a statically typed superset of JavaScript that compiles to plain JavaScript. It adds optional types, classes, and modules to JavaScript, enhancing the development experience by catching errors early and providing excellent tooling.

React Three Fiber and TypeScript together make a powerful combination. The static typing of TypeScript allows you to automatically infer types, making your React Three Fiber code more robust and easier to refactor.

```
import { Canvas } from '@react-three/fiber'

function App() {
  return (
    <Canvas>
      <mesh>
        <boxBufferGeometry args={[1, 1, 1]} />
        <meshStandardMaterial color={'orange'} />
      </mesh>
    </Canvas>
  )
}

export default App;
```

### Loading a 3D Model in React Three Fiber

Loading a 3D model in React Three Fiber is straightforward. You can use the useLoader hook provided by React Three Fiber to load your 3D models. This hook accepts a loader instance (GLTFLoader in this case) and a URL to the model.

```
import { useLoader } from '@react-three/fiber'
import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader'

function Model({ url }) {
  const gltf = useLoader(GLTFLoader, url)
  return <primitive object={gltf.scene} />
}
```

In the above code, useLoader is a hook that lets you use loaders in a React way. It returns the loaded asset, which, in this case, is a GLTF model. The primitive component is a special React Three Fiber component that allows you to include raw ThreeJS objects in your React tree.

### Using ThreeJS with TypeScript: A Comprehensive Guide

ThreeJS is a popular library for creating 3D graphics on the web. It provides a low-level, highly flexible API for creating complex 3D scenes. However, it's not designed to work with React or TypeScript out of the box.

Fortunately, with the help of React Three Fiber, you can use ThreeJS in a React and TypeScript environment. React Three Fiber provides a set of hooks and components that allow you to use ThreeJS in a React way. It also provides TypeScript definitions for all its exports, making it easy to use ThreeJS with TypeScript.

```
import { Canvas, useFrame } from '@react-three/fiber'

function Box() {
  const ref = useRef()
  useFrame(() => (ref.current.rotation.x += 0.01))
  return (
    <mesh ref={ref}>
      <boxBufferGeometry args={[1, 1, 1]} />
      <meshStandardMaterial color={'orange'} />
    </mesh>
  )
}

function App() {
  return (
    <Canvas>
      <Box />
    </Canvas>
  )
}

export default App;
```

In the above code, useFrame is a hook provided by React Three Fiber that allows you to run animations. It accepts a callback that is called before every frame. The ref is used to get a reference to the ThreeJS object (the mesh in this case).

### Integrating ThreeJS with React: A Step-by-Step Approach

Integrating ThreeJS with React can be tricky due to the differences in their paradigms. ThreeJS is imperative and mutable, while React is declarative and prefers immutability. However, with the help of React Three Fiber, you can bridge this gap and use ThreeJS in a React way.

Here is a step-by-step guide on how to integrate ThreeJS with React using React Three Fiber:

- Install React Three Fiber: You can install React Three Fiber using npm or yarn.

```
npm install @react-three/fiber
```

- Create a Canvas: The Canvas component provided by React Three Fiber is where your ThreeJS scene will live. It creates a WebGL renderer, a camera, and a scene for you.

```
import { Canvas } from '@react-three/fiber'

function App() {
return <Canvas></Canvas>
}
export default App;
```

Add Objects to the Scene: You can add objects to your ThreeJS scene using React components. React Three Fiber provides components for all ThreeJS objects.

```
import { Canvas } from '@react-three/fiber'

function App() {
return (
<Canvas>
<mesh>
<boxBufferGeometry args={[1, 1, 1]} />
<meshStandardMaterial color={'orange'} />
</mesh>
</Canvas>
)
}
export default App;
```

In the above code, mesh, boxBufferGeometry, and meshStandardMaterial are all components provided by React Three Fiber that correspond to their ThreeJS counterparts.

### The Difference Between React Three Fiber and ThreeJS

ThreeJS is a powerful library for creating 3D graphics on the web. It provides a low-level, highly flexible API for creating complex 3D scenes. However, it's not designed to work with React or TypeScript out of the box.

React Three Fiber, on the other hand, is a React renderer for ThreeJS. It's not a wrapper for ThreeJS but a reconciler (similar to ReactDOM and React Native). It bridges the gap between the declarative React world and the imperative ThreeJS world, allowing you to write ThreeJS code in a React-ish way.

The main difference between React Three Fiber and ThreeJS is how they are used. With ThreeJS, you create and manage your 3D objects imperatively. With React Three Fiber, you can declaratively create and manage your 3D objects using React components and hooks.

React Three Fiber also provides additional features not available in ThreeJS, such as integration with React's ecosystem, automatic memory management, and support for React's concurrent mode.

### Using React Three Fiber in React Native: A Practical Approach

React Three Fiber is not limited to the web. You can also use it in React Native to create 3D graphics in your mobile apps. The process of using React Three Fiber in React Native is similar to using it on the web.

First, you need to install @react-three/fiber and expo-gl:

```
npm install @react-three/fiber expo-gl
```

Then, you can use the Canvas component provided by React Three Fiber to create a WebGL context and render your ThreeJS scene:

```
import { Canvas } from '@react-three/fiber'

function App() {
return (
<Canvas>
<mesh>
<boxBufferGeometry args={[1, 1, 1]} />
<meshStandardMaterial color={'orange'} />
</mesh>
</Canvas>
)
}

export default App;
```

In the above code, Canvas creates a WebGL context using expo-gl, and mesh, boxBufferGeometry, and meshStandardMaterial are React components corresponding to their ThreeJS counterparts.

### Getting Started with React Three Fiber: A Beginner's Guide

Getting started with React Three Fiber (R3F) is quite straightforward. Here's a step-by-step guide:

- Installation: Install React Three Fiber using npm or yarn.

```
  npm install @react-three/fiber
```

- Create a Canvas: The Canvas component is where your ThreeJS scene will live. It creates a WebGL renderer, a camera, and a scene for you.

```
import { Canvas } from '@react-three/fiber'

function App() {
return <Canvas></Canvas>
}

export default App;
```

Add Objects to the Scene: You can add objects to your ThreeJS scene using React components. R3F provides components for all ThreeJS objects.

```
import { Canvas } from '@react-three/fiber'

function App() {
return (
<Canvas>
<mesh>
<boxBufferGeometry args={[1, 1, 1]} />
<meshStandardMaterial color={'orange'} />
</mesh>
</Canvas>
)
}

export default App;
```

Animate Your Objects: You can animate your objects using the useFrame hook provided by R3F.

```
import { Canvas, useFrame } from '@react-three/fiber'
import { useRef } from 'react'

function Box() {
  const ref = useRef()
  useFrame(() => (ref.current.rotation.x += 0.01))
  return (
    <mesh ref={ref}>
      <boxBufferGeometry args={[1, 1, 1]} />
      <meshStandardMaterial color={'orange'} />
    </mesh>
  )
}

function App() {
  return (
    <Canvas>
      <Box />
    </Canvas>
  )
}

export default App;
```

In the above code, useFrame is a hook that lets you run animations. It accepts a callback that is called before every frame. The ref is used to get a reference to the ThreeJS object (the mesh in this case).

### The Benefits of Using TypeScript in React

TypeScript is a statically typed superset of JavaScript that compiles to plain JavaScript. It adds optional types, classes, and modules to JavaScript, enhancing the development experience by catching errors early and providing excellent tooling.

Using TypeScript in React has several benefits:

1. Type Safety: TypeScript catches errors at compile-time, which means fewer runtime errors. This is especially beneficial in large codebases.
2. Better Developer Experience: TypeScript provides excellent autocompletion, making it easier to use APIs and libraries.
3. Easier Refactoring: With TypeScript, you can confidently refactor your code, knowing that any errors will be caught at compile-time.
4. Better Documentation: TypeScript types serve as documentation, making it easier for other developers to understand your code.

Here's an example of a React component written in TypeScript:

```
import { FC, useState } from 'react'

interface ButtonProps {
  initialText: string
}

const Button: FC<ButtonProps> = ({ initialText }) => {
  const [text, setText] = useState(initialText)

  return <button onClick={() => setText('Clicked!')}>{text}</button>
}
export default Button
```

In the above code, ButtonProps is a TypeScript interface that defines the props for the Button component. FC (Function Component) is a TypeScript type provided by React.

### Using ThreeJS Code in React: A Detailed Explanation

ThreeJS is a powerful library for creating 3D graphics on the web. However, it's not designed to work with React out of the box. Fortunately, with the help of React Three Fiber, you can use ThreeJS in a React way.

Here's an example of how to use ThreeJS code in React using React Three Fiber:

```
import { Canvas, useFrame } from '@react-three/fiber'
import { useRef } from 'react'

function Box() {
const ref = useRef()
useFrame(() => (ref.current.rotation.x += 0.01))
return (
<mesh ref={ref}>
<boxBufferGeometry args={[1, 1, 1]} />
<meshStandardMaterial color={'orange'} />
</mesh>
)
}

function App() {
return (
<Canvas>
<Box />
</Canvas>
)
}

export default App;
```

In the above code, useFrame is a hook provided by React Three Fiber that allows you to run animations. It accepts a callback that is called before every frame. The ref is used to get a reference to the ThreeJS object (the mesh in this case).

### The Advantages of Using ThreeJS in React

ThreeJS is a powerful library for creating 3D graphics on the web. However, using it with React can be tricky due to the differences in their paradigms. ThreeJS is imperative and mutable, while React is declarative and prefers immutability.

React Three Fiber bridges this gap and provides several advantages:

1. Declarative Syntax: With React Three Fiber, you can write ThreeJS code in a React-ish way. This makes your code more readable and easier to reason about.
2. Integration with React's Ecosystem: React Three Fiber allows you to use React's ecosystem. You can use React's state and props, context, hooks, and even libraries like Redux and React Router.
3. Performance: React Three Fiber optimizes your ThreeJS scene by minimizing the number of operations and only updating what's necessary. This can lead to better performance compared to vanilla ThreeJS.
4. Automatic Memory Management: React Three Fiber automatically cleans up resources (geometries, materials, textures, etc.) when components unmount, preventing memory leaks.

### The Process of Loading a 3D Model in React Three Fiber

Loading a 3D model in React Three Fiber is straightforward. You can use the useLoader hook provided by React Three Fiber to load your 3D models. This hook accepts a loader instance (GLTFLoader in this case) and a URL to the model.

```
import { useLoader } from '@react-three/fiber'
import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader'

function Model({ url }) {
const gltf = useLoader(GLTFLoader, url)
return <primitive object={gltf.scene} />
}
```

In the above code, useLoader is a hook that lets you use loaders in a React way. It returns the loaded asset, which in this case is a GLTF model. The primitive component is a special React Three Fiber component that allows you to include raw ThreeJS objects in your React tree.

### Understanding What React Fiber Does: A Deep Dive

React Fiber is a reimplementation of React's core algorithm, the engine that powers React behind the scenes. It was introduced in React 16 and significantly improved rendering performance, especially for large and complex applications.

The main goal of React Fiber was to enable incremental rendering - the ability to split rendering work into chunks and spread it out over multiple frames. This allows React to keep the user interface responsive even when there's a lot of work to do.

React Fiber also introduced a few other features, such as the ability to return multiple elements from a component's render method, better error handling, and support for React's concurrent mode.

React Three Fiber, on the other hand, is a React renderer for ThreeJS that uses React Fiber's architecture. It allows you to write ThreeJS code in a React-ish way and takes advantage of React Fiber's features to optimize your ThreeJS scene.

```
import { Canvas, useFrame } from '@react-three/fiber'
import { useRef } from 'react'

function Box() {
const ref = useRef()
useFrame(() => (ref.current.rotation.x += 0.01))
return (
<mesh ref={ref}>
<boxBufferGeometry args={[1, 1, 1]} />
<meshStandardMaterial color={'orange'} />
</mesh>
)
}

function App() {
return (
<Canvas>
<Box />
</Canvas>
)
}

export default App;

```

In the above code, useFrame is a hook provided by React Three Fiber that allows you to run animations. It accepts a callback that is called before every frame. The ref is used to get a reference to the ThreeJS object (the mesh in this case).

### Can we use TypeScript in React?

Yes, TypeScript can be used with React to build robust and scalable applications. TypeScript is a statically typed superset of JavaScript that adds optional types to the language. It provides benefits like early error checking, better autocompletion, and improved navigation, refactoring, and understanding of the code.

React and TypeScript work well together. TypeScript has built-in support for JSX and React's component model, and React has TypeScript definitions available in the DefinitelyTyped project.

Here's an example of a React component written in TypeScript:

```
import { FC, useState } from 'react'

interface ButtonProps {
initialText: string
}

const Button: FC<ButtonProps> = ({ initialText }) => {
const [text, setText] = useState(initialText)

return <button onClick={() => setText('Clicked!')}>{text}</button>
}

export default Button
```

In the above code, ButtonProps is a TypeScript interface that defines the props for the Button component. FC (Function Component) is a TypeScript type provided by React.
