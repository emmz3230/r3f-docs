Let's add another Three.js module, but again via a Drei import. The OrbitControls.

Update your existing Stats import statement to also
import OrbitControls.

```
import { Stats, OrbitControls } from '@react-three/drei'
```

And add the `<OrbitControls/>` tag to the end of the JSX, just before the `<Stats />` tag.

```jsx title="./src/App.jsx"

import { Canvas } from '@react-three/fiber'
import Polyhedron from './Polyhedron'
import \* as THREE from 'three'
import { Stats, OrbitControls } from '@react-three/drei'

export default function App() {
const polyhedron = [
new THREE.BoxGeometry(),
new THREE.SphereGeometry(0.785398),
new THREE.DodecahedronGeometry(0.785398),
]

return (
<Canvas camera={{ position: [0, 0, 3] }}>
<Polyhedron position={[-0.75, -0.75, 0]} polyhedron={polyhedron} />
<Polyhedron position={[0.75, -0.75, 0]} polyhedron={polyhedron} />
<Polyhedron position={[-0.75, 0.75, 0]} polyhedron={polyhedron} />
<Polyhedron position={[0.75, 0.75, 0]} polyhedron={polyhedron} />
<OrbitControls />
<Stats />
</Canvas>
)
}
```

The OrbitControls has many properties that can be modified.

See the official documentation at [THREE.OrbitControls](https://threejs.org/docs/#examples/en/controls/OrbitControls) for all properties and methods.

By default, the Drei OrbitControls has enableDamping set to true. When you let go of the mouse, it continues to rotate but slow down.

You can disable damping by using the tag,

```
<OrbitControls enableDamping={false} />
```

The OrbitControls allows panning, rotating and zooming. You can enable/disable each of these. The below JSX disables panning and rotation, but still allows zooming. All three properties are true by default.

```
<OrbitControls enablePan={false} enableRotate={false} />
```

You can limit the amount of rotation up/down left/right.

```
<OrbitControls
minAzimuthAngle={-Math.PI / 4}
maxAzimuthAngle={Math.PI / 4}
minPolarAngle={Math.PI / 6}
maxPolarAngle={Math.PI - Math.PI / 6}
/>

```
