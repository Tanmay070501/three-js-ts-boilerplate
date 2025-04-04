# Three.js + TypeScript + Vite Boilerplate

A minimal boilerplate to kickstart Three.js development using **TypeScript** and **Vite** for lightning-fast builds.

---

## 📦 Features

- ⚡️ Vite-powered build setup
- 📜 TypeScript support
- 🎮 Live reload with `npm run dev`
- 🎲 Basic 3D spinning cube scene using Three.js
- 🧼 Clean project structure

---

## 🚀 Getting Started

### 🔧 Prerequisites

Make sure [Node.js](https://nodejs.org/) is installed on your system (includes npm).

---

### 🛠️ Step-by-Step Setup

#### 1. Create a Vite project

```bash
npm create vite@latest
```

Follow the CLI prompts:

```
✔ Project name: … three-js-ts-boilerplate
✔ Select a framework: › Vanilla
✔ Select a variant: › TypeScript
```

---

#### 2. Move into the project folder

```bash
cd three-js-ts-boilerplate
```

---

#### 3. Install dependencies

```bash
npm install
npm install three --save-dev
npm install @types/three --save-dev

```

---

#### 4. Start the development server

```bash
npm run dev
```

Now open your browser and go to:

👉 [http://localhost:5173](http://localhost:5173)

You should see a running Vite + TypeScript template.

---

### 🧹 Cleanup

Delete the following default files:

```text
src/vite.svg
src/counter.ts
src/typescript.svg
```

---

## 🧾 Replace Files

Replace the content of these files with the following:

---

### `index.html`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Three.js TypeScript BP</title>
  </head>

  <body>
    <script type="module" src="/src/main.ts"></script>
  </body>
</html>
```

---

### `src/style.css`

```css
body {
  overflow: hidden;
  margin: 0px;
}
```

---

### `src/main.ts`

```ts
import './style.css'
import * as THREE from 'three'

const scene = new THREE.Scene()

const camera = new THREE.PerspectiveCamera(
  75,
  window.innerWidth / window.innerHeight,
  0.1,
  1000
)
camera.position.z = 1.5

const renderer = new THREE.WebGLRenderer()
renderer.setSize(window.innerWidth, window.innerHeight)
document.body.appendChild(renderer.domElement)

window.addEventListener('resize', () => {
  camera.aspect = window.innerWidth / window.innerHeight
  camera.updateProjectionMatrix()
  renderer.setSize(window.innerWidth, window.innerHeight)
})

const geometry = new THREE.BoxGeometry()
const material = new THREE.MeshNormalMaterial({ wireframe: true })

const cube = new THREE.Mesh(geometry, material)
scene.add(cube)

function animate() {
  requestAnimationFrame(animate)
  cube.rotation.x += 0.01
  cube.rotation.y += 0.01
  renderer.render(scene, camera)
}

animate()
```


---

## 📄 License

MIT — free to use, modify and distribute.

---

## 👋 Acknowledgements

- [Three.js](https://threejs.org/)
- [Vite](https://vitejs.dev/)
- [TypeScript](https://www.typescriptlang.org/)
