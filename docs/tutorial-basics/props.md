Props (a.k.a. properties) are used in React to pass in attributes to your components when you declare them in the JSX.

Our Box from the last lesson is our component that returns a JSX.Element describing a THREE.Mesh.

But we cannot modify any of its properties when we create it, so if we create 2 or more, then they will just be placed in the scene on top of each other in the same position.

Instead, we can add props that we will use to further initialize them with a position when we declare them in the JSX.

```jsx title="./src/Box.jsx"

export default function Box(props) {
return (
<mesh {...props}>
<boxGeometry />
<meshBasicMaterial color={0x00ff00} wireframe />
</mesh>
)
}
./src/App.jsx

import { Canvas } from '@react-three/fiber'
import Box from './Box'

export default function App() {
return (
<Canvas camera={{ position: [0, 0, 2] }}>
<Box position={[-0.75, 0, 0]} name="A" />
<Box position={[0.75, 0, 0]} name="B" />
</Canvas>
)
}

```

#### Note

that React will re-render any component instances whenever a change is made to its state or props.

```

```
