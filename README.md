# Performance Monitoring with Stats in Three.js

Three.js includes a helpful module for monitoring performance called `stats.module`, located in:

```
three/examples/jsm/libs/stats.module.js
```

This module can be used to track FPS (frames per second) and render performance in real-time.

---

## 🎞️ Importing Stats

You can import the module like this:

```js
import Stats from 'three/examples/jsm/libs/stats.module.js';
```

---

## 🛠️ Setting Up Stats

After importing, initialize and append the stats panel to your HTML document:

```js
const stats = Stats();
document.body.appendChild(stats.dom);
```

---

## 🔁 Using Stats in the Animation Loop

To keep the stats panel updated, call `stats.update()` inside your animation loop:

```js
function animate() {
    requestAnimationFrame(animate);

    // Your rendering and update logic here...

    stats.update();  // Updates the stats panel
}
```

---

## 📌 Notes

- The Stats panel updates independently of Three.js and can be used in other JavaScript projects as well.
- It’s useful for debugging performance issues or optimizing render times.
- Stats is bundled with the Three.js examples, so you don’t need to install it separately.

---


The `Stats` panel provides a simple but powerful way to keep an eye on your rendering performance as your scene grows in complexity.

