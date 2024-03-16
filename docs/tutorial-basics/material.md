In this lesson, we will introduce four of the most commonly used materials that you will see used in Three.js.

MeshBasicMaterial
MeshNormalMaterial
MeshPhongMaterial
MeshStandardMaterial
There are other materials, but we will discuss those, plus more details, about each material as we progress.

In this lesson, we will start by focusing on several important factors about materials and why you might choose one over the others.

```jsx title="./src/App.jsx"

import { Canvas } from '@react-three/fiber'
import Polyhedron from './Polyhedron'
import \* as THREE from 'three'
import { Stats, OrbitControls } from '@react-three/drei'

export default function App() {
return (
<Canvas camera={{ position: [-1, 4, 2.5] }}>
<directionalLight position={[1, 1, 1]} />
<Polyhedron
name="meshBasicMaterial"
position={[-3, 1, 0]}
material={new THREE.MeshBasicMaterial()}
/>
<Polyhedron
name="meshNormalMaterial"
position={[-1, 1, 0]}
material={new THREE.MeshNormalMaterial()}
/>
<Polyhedron
name="meshPhongMaterial"
position={[1, 1, 0]}
material={new THREE.MeshPhongMaterial()}
/>
<Polyhedron
name="meshStandardMaterial"
position={[3, 1, 0]}
material={new THREE.MeshStandardMaterial()}
/>
<OrbitControls target-y={1} />
<axesHelper args={[5]} />
<gridHelper />
<Stats />
</Canvas>
)
}

```

```

jsx title="./src/Polyhedron.jsx"

import { useRef } from 'react'
import { useControls } from 'leva'
import \* as THREE from 'three'
import { useFrame } from '@react-three/fiber'

export default function Polyhedron(props) {
const ref = useRef()

useFrame((\_, delta) => {
ref.current.rotation.x += 0.2 _ delta
ref.current.rotation.y += 0.05 _ delta
})

useControls(props.name, {
wireframe: {
value: false,
onChange: (v) => {
ref.current.material.wireframe = v
},
},
flatShading: {
value: true,
onChange: (v) => {
ref.current.material.flatShading = v
ref.current.material.needsUpdate = true
},
},
color: {
value: 'lime',
onChange: (v) => {
ref.current.material.color = new THREE.Color(v)
},
},
})

return (
<mesh {...props} ref={ref}>
<icosahedronGeometry args={[1, 1]} />
</mesh>
)
}

```

```

```
