# Nebula Hands ✨🖐️

A real-time, interactive 3D particle system controlled entirely by your hand gestures using your webcam. Built with **Three.js** for 3D graphics rendering and **MediaPipe** for machine learning-powered hand tracking.

---

## 🌟 Features

* **Real-Time Hand Tracking:** Detects hand movements, finger positioning, and gestures via browser webcam input.
* **Dynamic Morphing Shapes:** Seamlessly transition between multiple 3D particle formations:
  * `Sphere` (Default)
  * `Heart`
  * `Saturn` (Planet with rings)
  * `Flower` (Rose curve)
  * `Fireworks` (Explosion burst)
* **Interactive Controls:**
  * **Move Hand:** Repositions and tilts the entire particle cloud in 3D space.
  * **Pinch (Thumb + Index Tip):** Expands or contracts the particle volume in real-time.
  * **Fist:** Cycles to the next available 3D shape.
* **Optimized Performance:** Powered by Three.js `BufferGeometry` and point materials with additive blending for a glowing nebula effect.

---

## 🚀 Quick Start / Running Locally

Because this project loads ES modules via an import map and accesses the user's webcam (`navigator.mediaDevices.getUserMedia`), it **must be run through a local development server** rather than opened directly as a local `file://` URL (due to browser security restrictions).

### Prerequisites
Make sure you have [Node.js](https://nodejs.org/) installed, or use any local static file server of your choice (like Python's `http.server` or VS Code's *Live Server* extension).

### Setup & Run
1. Save your main file as `index.html`.
2. Open your terminal in the directory containing `index.html`.
3. Run a local server:
   * **Using Node (npx):**
     ```bash
     npx serve
     ```
   * **Using Python (Python 3):**
     ```bash
     python -m http.server 8000
     ```
4. Open your browser and navigate to `http://localhost:3000` (or `http://localhost:8000`).
5. Allow webcam access when prompted.

---

## 🎮 Controls & Gestures

| Gesture | Action | Description |
| :--- | :--- | :--- |
| **👆 Move Hand** | Position & Rotate | Move your hand around the frame to tilt and shift the particle cluster. |
| **👌 Pinch** | Expand / Contract | Bring your thumb and index finger close together to shrink the shape, or spread them apart to expand it. |
| **✊ Fist** | Switch Shape | Hold a fist gesture briefly to cycle through the 3D shapes (Sphere $\rightarrow$ Heart $\rightarrow$ Saturn $\rightarrow$ Flower $\rightarrow$ Fireworks). |

---

## 🛠️ Tech Stack

* **[Three.js](https://threejs.org/) (v0.160.0):** 3D WebGL rendering engine used for particle management, shaders, and camera management.
* **[MediaPipe Tasks Vision](https://developers.google.com/mediapipe) (v0.10.3):** Google's machine learning framework used for high-performance hand landmark detection.
* **HTML5 / CSS3 / JavaScript (ES Modules):** Clean, modern frontend implementation without bulky build tools.

---

## ⚙️ Configuration

You can easily tweak parameters at the top of the main script block inside `index.html`:

```javascript
const PARTICLE_COUNT = 5000;   // Number of active particles in the scene
const CAM_Z = 100;             // Camera depth distance
const FIST_THRESHOLD = 10;     // Frames required to hold a fist before switching shapes
```