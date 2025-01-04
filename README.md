<h1 align="center">✨ Bubbles ✨</h1>
<h2 align="center">Spheres2 Background Animation with Three.js and Anime.js</h2>

<p align="center">
  <img src="https://user-images.githubusercontent.com/your-username/project-demo.gif" alt="Project Demo" width="600">
</p>

<p align="center">
  This project demonstrates the use of the <a href="https://github.com/threejs-components/threejs-components">Spheres2Background</a> component from the <strong>Three.js Components Library</strong> to create a dynamic and interactive 3D spheres background. It also utilizes <a href="https://animejs.com/">Anime.js</a> for advanced animation effects.
</p>

---

<h2>✨ Features</h2>
<ul>
  <li><strong>Interactive Spheres Background:</strong> A vibrant 3D background of spheres with customizable colors and sizes.</li>
  <li><strong>Pause/Play Animation:</strong> Click anywhere on the page to toggle the background animation.</li>
  <li><strong>Dynamic Color Change:</strong> Use a button to randomly change sphere colors and light properties.</li>
</ul>

---

<h2>⚡ Installation</h2>

<h3>Prerequisites</h3>
<ul>
  <li>A modern web browser with WebGL support.</li>
  <li>A local or remote web server to serve the project files.</li>
</ul>

<h3>Clone the Repository</h3>
<pre>
<code>git clone https://github.com/your-username/spheres2-background.git
cd spheres2-background
</code>
</pre>

<h3>Run the Project</h3>
<ol>
  <li>Open <code>index.html</code> in a web browser via a local or remote server.</li>
  <li>Interact with the page to see animations and effects in action.</li>
</ol>

---

<h2>🛠️ Code Overview</h2>

<p>The project uses the <code>Spheres2Background</code> component to create a background with the following parameters:</p>
<ul>
  <li><strong>count:</strong> Number of spheres.</li>
  <li><strong>colors:</strong> Initial colors of the spheres.</li>
  <li><strong>minSize</strong> &amp; <strong>maxSize:</strong> Size range for the spheres.</li>
</ul>

<p>Colors and light properties are dynamically updated using the <a href="https://animejs.com/">Anime.js</a> library when the button is clicked.</p>

<details>
<summary><strong>View Code Snippet</strong></summary>

```javascript
import Spheres2Background from 'https://cdn.jsdelivr.net/npm/threejs-components@0.0.8/build/backgrounds/spheres2.cdn.min.js'

const bg = Spheres2Background(document.getElementById('webgl-canvas'), {
  count: 200,
  colors: [0xff0000, 0x0, 0xffffff],
  minSize: 0.5,
  maxSize: 1
})

const button1 = document.getElementById('colors-btn')

document.body.addEventListener('click', (ev) => {
  if (ev.target !== button1) bg.togglePause()
})

button1.addEventListener('click', () => {
  bg.spheres.setColors([0xffffff * Math.random(), 0xffffff * Math.random(), 0xffffff * Math.random()])
  bg.spheres.light1.color.set(0xffffff * Math.random())
})
