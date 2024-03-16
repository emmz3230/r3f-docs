---
sidebar_position: 1
---

# React-Three-Fiber

Build your scene declaratively with re-usable, self-contained components that react to state, are readily interactive and can participate in React's ecosystem.

```
npm install three @types/three @react-three/fiber
```

### Does it have limitations?

None. Everything that works in Threejs will work here without exception.

### Is it slower than plain Threejs?

No. There is no overhead. Components render outside of React. It outperforms Threejs in scale due to Reacts scheduling abilities.

### Can it keep up with frequent feature updates to Threejs?

Yes. It merely expresses Threejs in JSX, <mesh /> dynamically turns into new THREE.Mesh(). If a new Threejs version adds, removes or changes features, it will be available to you instantly without depending on updates to this library.

### What does it look like?

```
import { createRoot } from 'react-dom/client'
import React, { useRef, useState } from 'react'
import { Canvas, useFrame } from '@react-three/fiber'

function Box(props) {
  // This reference will give us direct access to the mesh
  const meshRef = useRef()
  // Set up state for the hovered and active state
  const [hovered, setHover] = useState(false)
  const [active, setActive] = useState(false)
  // Subscribe this component to the render-loop, rotate the mesh every frame
  useFrame((state, delta) => (meshRef.current.rotation.x += delta))
  // Return view, these are regular three.js elements expressed in JSX
  return (
    <mesh
      {...props}
      ref={meshRef}
      scale={active ? 1.5 : 1}
      onClick={(event) => setActive(!active)}
      onPointerOver={(event) => setHover(true)}
      onPointerOut={(event) => setHover(false)}>
      <boxGeometry args={[1, 1, 1]} />
      <meshStandardMaterial color={hovered ? 'hotpink' : 'orange'} />
    </mesh>
  )
}

createRoot(document.getElementById('root')).render(
  <Canvas>
    <ambientLight intensity={Math.PI / 2} />
    <spotLight position={[10, 10, 10]} angle={0.15} penumbra={1} decay={0} intensity={Math.PI} />
    <pointLight position={[-10, -10, -10]} decay={0} intensity={Math.PI} />
    <Box position={[-1.2, 0, 0]} />
    <Box position={[1.2, 0, 0]} />
  </Canvas>,
)
```

### First steps

You need to be versed in both React and Threejs before rushing into this. If you are unsure about React [React](https://react.dev/learn) consult the official React docs, especially the section about hooks [section about hooks](https://react.dev/reference/react). . As for Threejs, make sure you at least glance over the following links:

Make sure you have a [basic grasp of Threejs](https://threejs.org/docs/index.html#manual/en/introduction/Creating-a-scene) .
Keep that site open.
