Let's now add some shadows, and see how different materials react.

Things to remember at minimum,

Add shadows to Canvas

```
<Canvas shadows />
```

Set your light to cast shadows

```
<directionalLight castShadow />
```

Select which meshes will cast shadows

```
<mesh castShadow />
```

Select which meshes will receive shadows

```
<mesh receiveShadow />
```

```jsx title="./src/app.jsx"


import Polyhedron from './Polyhedron'
import \* as THREE from 'three'
import { Canvas } from '@react-three/fiber'
import { Stats, OrbitControls } from '@react-three/drei'
import { useControls } from 'leva'
import Floor from './Floor'

function Lights() {
const ambientCtl = useControls('Ambient Light', {
visible: false,
intensity: {
value: 1.0,
min: 0,
max: 1.0,
step: 0.1,
},
})

const directionalCtl = useControls('Directional Light', {
visible: true,
position: {
x: 3.3,
y: 1.0,
z: 4.4,
},
castShadow: true,
})

const pointCtl = useControls('Point Light', {
visible: false,
position: {
x: 2,
y: 0,
z: 0,
},
castShadow: true,
})

const spotCtl = useControls('Spot Light', {
visible: false,
position: {
x: 3,
y: 2.5,
z: 1,
},
castShadow: true,
})

return (
<>
<ambientLight
        visible={ambientCtl.visible}
        intensity={ambientCtl.intensity}
      />
<directionalLight
visible={directionalCtl.visible}
position={[
directionalCtl.position.x,
directionalCtl.position.y,
directionalCtl.position.z,
]}
castShadow={directionalCtl.castShadow}
/>
<pointLight
visible={pointCtl.visible}
position={[
pointCtl.position.x,
pointCtl.position.y,
pointCtl.position.z,
]}
castShadow={pointCtl.castShadow}
/>
<spotLight
visible={spotCtl.visible}
position={[spotCtl.position.x, spotCtl.position.y, spotCtl.position.z]}
castShadow={spotCtl.castShadow}
/>
</>
)
}
export default function App() {
return (
<Canvas camera={{ position: [4, 4, 1.5] }} shadows>
<Lights />
<Polyhedron
name="meshBasicMaterial"
position={[-3, 1, 0]}
material={new THREE.MeshBasicMaterial({ color: 'yellow' })}
/>
<Polyhedron
name="meshNormalMaterial"
position={[-1, 1, 0]}
material={new THREE.MeshNormalMaterial({ flatShading: true })}
/>
<Polyhedron
name="meshPhongMaterial"
position={[1, 1, 0]}
material={
new THREE.MeshPhongMaterial({ color: 'lime', flatShading: true })
}
/>
<Polyhedron
name="meshStandardMaterial"
position={[3, 1, 0]}
material={
new THREE.MeshStandardMaterial({
color: 0xff0033,
flatShading: true,
})
}
/>
<Floor />
<OrbitControls target={[2, 2, 0]} />
<axesHelper args={[5]} />
<Stats />
</Canvas>
)
}
```

```jsx title="./src/Polyhedron.jsx"

import { useRef } from 'react'
import { useFrame } from '@react-three/fiber'

export default function Polyhedron(props) {
const ref = useRef()

useFrame((\_, delta) => {
ref.current.rotation.x += 0.2 _ delta
ref.current.rotation.y += 0.05 _ delta
})

return (
<mesh {...props} ref={ref} castShadow receiveShadow>
<icosahedronGeometry args={[1, 1]} />
</mesh>
)
}
```

```jsx title="./src/Floor.jsx"

Create another file named Floor.jsx in the ./src/ folder.

export default function Floor() {
return (
<mesh rotation-x={-Math.PI / 2} receiveShadow>
<circleGeometry args={[10]} />
<meshStandardMaterial />
</mesh>
)
}
```
