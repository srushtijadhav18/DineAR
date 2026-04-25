# DineAR 🍽️

**Browser-based WebAR menu system** that overlays interactive 3D food models on physical menu cards — no app download required. Point your phone camera at a menu card and the dish appears in 3D, to scale, right on the table.

🔗 **[Live Demo](https://srushtijadhav18.github.io/DineAR/)**

---

## 📸 Demo

![DineAR Demo](demo.gif)

---

## How It Works

Each physical menu card acts as an image marker. When the camera detects a card, MindAR.js triggers the corresponding 3D GLB model to render anchored to that card in real space. A dish info card (name, price, calories, prep time) appears simultaneously at the bottom of the screen.

Users can rotate the model with a single finger and pinch-to-zoom to inspect it from any angle.

---

## Tech Stack

| Layer | Technology |
|---|---|
| AR Tracking | MindAR.js (image marker) |
| 3D Rendering | A-Frame + Three.js |
| 3D Models | GLB format (Sketchfab) |
| Gesture Control | Custom touch event handlers |
| Deployment | GitHub Pages |

---

## Key Technical Details

- **Auto-normalize component** — custom A-Frame component that reads each GLB's Three.js bounding box at runtime and computes the exact scale factor to render it at a consistent real-world size, regardless of the unit system the model was exported in (mm/cm/m)
- **Gesture handler** — single-finger drag for Y-axis rotation, two-finger pinch for zoom, clamped relative to normalized scale
- **5 image targets** compiled into a single `.mind` file, each mapped to a unique dish with metadata

---

## Project Structure

```
DineAR/
├── index.html        # Main AR app
├── targets.mind      # Compiled image target file
├── pizza.glb
├── momos.glb
├── thali.glb
├── paneer.glb
└── cake.glb
```

---

## Run Locally

```bash
# Needs HTTPS or localhost for camera access
npx serve .
# then open http://localhost:3000
```
