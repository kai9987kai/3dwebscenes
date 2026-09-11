# 🌐 3D Web Scenes

A collection of interactive, real-time **3D scenes that run directly in the web browser** using **Three.js, WebGL, HTML, CSS and JavaScript**.

This repository is an experimental playground for building increasingly detailed browser-based 3D environments without requiring a traditional game engine or complex build pipeline.

The scenes combine procedural geometry, procedural textures, lighting, shadows, animation, environmental effects, post-processing and interactive camera systems inside standalone HTML applications.

## ✨ Overview

`3dwebscenes` explores how far modern browser graphics can be pushed using relatively lightweight web technology.

Current scenes include:

| Scene | Description |
|---|---|
| 🏰 `Citadel.html` | A large interactive sci-fi/gothic fortress with procedural architecture, atmospheric weather, emissive lighting, battle damage and post-processing |
| 🦒 `giraffe_enclosure_realistic.html` | A detailed outdoor giraffe enclosure with procedural terrain, vegetation, structures and a procedurally constructed giraffe |

The scenes are designed to work without Node.js, npm, bundlers or a traditional compilation process.

---

# 🏰 Citadel // Fortress 360

`Citadel.html` is an interactive reconstruction of a large fortified architectural environment.

It combines gothic red-brick architecture with metallic structural elements, illuminated infrastructure, defensive systems and a dark sci-fi atmosphere.

## Citadel features

- Fully navigable 3D environment
- Procedurally generated fortress geometry
- Procedural brick and material textures
- Physically based materials
- Red-brick architecture
- Metallic structural ribs
- Emissive architectural elements
- Surveillance and defensive structures
- Exterior reconstruction viewable from all sides
- Real-time directional lighting
- Soft shadows
- Atmospheric fog
- Night mode
- Dynamic rain
- Damage and scorch decals
- Adjustable emissive intensity
- Adjustable bloom
- Adjustable renderer exposure
- Automatic camera orbit
- Reference-image comparison system
- Multiple predefined camera positions
- Screenshot capture
- Fullscreen mode
- Rendering quality presets
- Shadow toggle
- Live FPS counter
- Triangle counter
- Draw-call counter
- Responsive control interface

## Camera presets

The Citadel provides several predefined viewpoints:

- Front
- Rear
- Left
- Right
- Top
- Hero

You can also freely orbit around the structure.

### Camera controls

**Left mouse drag**

Rotate/orbit around the scene.

**Mouse wheel**

Zoom in and out.

**Right mouse drag**

Pan the camera.

---

# 🦒 Realistic Giraffe Enclosure

`giraffe_enclosure_realistic.html` is an interactive outdoor animal enclosure rendered completely in the browser.

The scene combines a procedural landscape, enclosure architecture, environmental details and a custom-built giraffe model.

## Giraffe features

The giraffe includes detailed procedural anatomy such as:

- Tapered limbs
- Leg joint structure
- Articulated neck
- Head and muzzle geometry
- Eyes
- Ears
- Ossicones
- Mane
- Tail
- Hooves
- Detailed body proportions
- Procedurally generated coat patterning

The scene additionally contains:

- Procedural terrain
- Multi-octave terrain noise
- Terrain displacement
- Procedural ground textures
- Wooden structures
- Fencing
- Shelter architecture
- Environmental props
- Directional sunlight
- Hemisphere lighting
- Atmospheric fog
- Large procedural sky
- Soft real-time shadows
- Camera focus presets
- Automatic camera tour
- Walk mode
- Quality settings
- Shadow controls
- FPS monitoring
- Triangle statistics
- Draw-call statistics
- Object-count monitoring

---

# 🧰 Technology

The project is primarily built using:

- **HTML5**
- **CSS3**
- **JavaScript ES Modules**
- **Three.js**
- **WebGL**
- **GLSL shaders**
- **Canvas-generated procedural textures**
- **Three.js OrbitControls**
- **Three.js post-processing**

The Citadel also makes use of:

- `EffectComposer`
- `RenderPass`
- `UnrealBloomPass`
- `OutputPass`
- ACES filmic tone mapping
- sRGB colour management
- PCF soft shadow mapping

Most assets are generated dynamically in JavaScript rather than relying on a large collection of external model or texture files.

---

# ⚙️ No Build System Required

There is currently:

- No npm installation
- No webpack
- No Vite
- No package compilation
- No application server
- No database

Three.js and its supporting modules are loaded directly from CDNs using browser import maps.

This makes each scene largely self-contained.

---

# 🚀 Getting Started

## 1. Clone the repository

```bash
git clone https://github.com/kai9987kai/3dwebscenes.git
```

Enter the project directory:

```bash
cd 3dwebscenes
```

---

# 🌐 Run a Local Web Server

Because the scenes use JavaScript ES modules and browser import maps, running them through an HTTP server is recommended instead of opening the HTML files directly with a `file://` URL.

If Python is installed:

```bash
python -m http.server 8000
```

On some systems you may need:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000/
```

---

# 🏰 Open the Citadel

Navigate to:

```text
http://localhost:8000/Citadel.html
```

---

# 🦒 Open the Giraffe Enclosure

Navigate to:

```text
http://localhost:8000/giraffe_enclosure_realistic.html
```

---

# 📁 Repository Structure

```text
3dwebscenes/
│
├── .github/
│
├── Citadel.html
├── giraffe_enclosure_realistic.html
│
├── CODE_OF_CONDUCT.md
├── SECURITY.md
├── LICENSE
└── README.md
```

The main scenes are deliberately kept as standalone HTML applications.

Each HTML file can contain its own:

```text
HTML interface
    │
    ├── CSS interface styling
    │
    ├── Three.js imports
    │
    ├── WebGL renderer
    │
    ├── Scene
    │
    ├── Camera
    │
    ├── Lighting
    │
    ├── Materials
    │
    ├── Procedural textures
    │
    ├── Procedural geometry
    │
    ├── Environment
    │
    ├── Animation
    │
    ├── Camera controls
    │
    └── Performance monitoring
    │
    ▼
Interactive WebGL Scene
```

---

# 🎨 Procedural Graphics

A major focus of this repository is generating visual assets directly at runtime.

Instead of requiring every texture to exist as an external image, JavaScript and HTML Canvas can generate textures dynamically.

Examples include:

- Brick surfaces
- Ground textures
- Wood grain
- Animal coat patterns
- Noise overlays
- Surface variation
- Material imperfections
- Damage details

This keeps experiments portable while allowing a large amount of visual variation.

---

# 🌍 Procedural Environments

The project also experiments with generating environments mathematically.

For example, the giraffe enclosure uses layered noise functions to construct irregular terrain.

Conceptually:

```text
Noise
  ↓
Multiple frequencies
  ↓
Fractal noise / FBM
  ↓
Terrain height
  ↓
Vertex displacement
  ↓
Recalculate normals
  ↓
3D landscape
```

This allows relatively large landscapes to be created without importing external terrain models.

---

# 💡 Rendering

The scenes use real-time physically inspired rendering techniques provided by Three.js.

Depending on the scene, this includes:

- Perspective projection
- WebGL hardware acceleration
- Antialiasing
- PBR-style materials
- Directional lights
- Hemisphere lights
- Soft shadows
- Atmospheric fog
- Emissive materials
- Bloom
- Tone mapping
- Procedural shaders
- Dynamic particle effects

The Citadel uses **ACES Filmic Tone Mapping** to provide more cinematic highlight handling.

---

# ✨ Post-Processing

The Citadel uses a Three.js post-processing pipeline approximately structured as:

```text
Three.js Scene
      │
      ▼
 RenderPass
      │
      ▼
UnrealBloomPass
      │
      ▼
 OutputPass
      │
      ▼
    Canvas
```

Bloom is used particularly heavily for illuminated and emissive architectural elements.

---

# 📊 Performance Monitoring

Both scenes contain real-time rendering statistics.

Depending on the application, the HUD can display:

```text
FPS
Triangles
Draw Calls
Objects
Rendering Mode
```

These statistics make it easier to experiment with browser rendering performance while increasing scene complexity.

---

# ⚡ Quality Modes

Scenes provide configurable graphics settings so they can run across different GPU capabilities.

Possible quality levels include:

### Performance / Medium

Prioritises frame rate.

Suitable for:

- Integrated graphics
- Older laptops
- Lower-power devices

### Balanced / High

Provides a compromise between visual fidelity and rendering cost.

This is generally the recommended setting.

### Ultra

Prioritises rendering quality.

Suitable for more capable desktop GPUs.

---

# 🖥️ Browser Requirements

A modern browser with WebGL and JavaScript ES module support is recommended.

Suitable browsers include recent versions of:

- Google Chrome
- Microsoft Edge
- Mozilla Firefox
- Safari

For the best results, hardware acceleration should be enabled.

---

# 🎮 GPU Requirements

The project does not require a dedicated graphics card, but scene complexity can vary significantly.

Performance depends on factors including:

- GPU
- Browser
- Screen resolution
- Device pixel ratio
- Shadow resolution
- Geometry complexity
- Post-processing
- Number of visible objects
- Number of draw calls

If performance is poor, reduce the scene's quality setting or disable expensive effects such as shadows.

---

# 🧪 Experimental Project

This repository is also intended as a space for experimenting with browser-based graphics techniques.

Areas of interest include:

- Procedural modelling
- Procedural architecture
- Procedural animals
- Browser-based game environments
- Digital twins
- Interactive architectural visualisation
- Web-based simulation
- WebGL optimisation
- Shader development
- Procedural landscapes
- Runtime texture synthesis
- Real-time lighting
- Post-processing
- Environmental effects
- Interactive camera systems
- Large standalone HTML applications

---

# ➕ Adding Another Scene

A new scene can be added as another standalone HTML file:

```text
3dwebscenes/
├── Citadel.html
├── giraffe_enclosure_realistic.html
├── new_scene.html
└── ...
```

A basic Three.js scene can follow this architecture:

```text
Create renderer
      ↓
Create scene
      ↓
Create camera
      ↓
Create controls
      ↓
Generate/load environment
      ↓
Create materials
      ↓
Create geometry
      ↓
Configure lighting
      ↓
Configure effects
      ↓
Start animation loop
      ↓
Render continuously
```

---

# 🛠️ Development

When modifying a scene, run the local server:

```bash
python -m http.server 8000
```

Then refresh the browser after saving changes.

Browser developer tools are particularly useful for monitoring:

- JavaScript exceptions
- WebGL errors
- Network requests
- CDN imports
- GPU performance
- Frame rate
- Memory usage

---

# 🔮 Possible Future Development

Potential future improvements include:

- More interactive 3D scenes
- Shared scene launcher
- Central `index.html`
- Scene thumbnails
- First-person navigation
- Collision detection
- Physics
- WebGPU rendering
- Instanced rendering
- Level-of-detail systems
- GLTF/GLB model support
- Improved procedural vegetation
- Dynamic weather
- Day/night cycles
- Spatial audio
- Animated characters
- More advanced shaders
- Screen-space effects
- Improved mobile controls
- Progressive scene loading
- Asset caching
- Scene export tools
- Performance benchmarking
- VR/WebXR support

---

# 🤝 Contributing

Contributions, experiments and improvements are welcome.

A typical workflow is:

```bash
git clone https://github.com/kai9987kai/3dwebscenes.git
cd 3dwebscenes
git checkout -b feature/my-new-scene
```

Make your changes, then commit them:

```bash
git add .
git commit -m "Add new 3D scene"
```

Push your branch:

```bash
git push origin feature/my-new-scene
```

Then open a pull request on GitHub.

Please also read the repository's `CODE_OF_CONDUCT.md` before contributing.

---

# 🔐 Security

If you discover a security issue, please follow the instructions in:

```text
SECURITY.md
```

Please avoid publicly disclosing vulnerabilities before they can be reviewed.

---

# 📜 Licence

This project is licensed under the **Apache License 2.0**.

See:

```text
LICENSE
```

for the complete licence terms.

---

# 👤 Author

**Kai Piper**

GitHub:

https://github.com/kai9987kai

Repository:

https://github.com/kai9987kai/3dwebscenes

---

# ⭐ Support the Project

If you find the project interesting, consider giving the repository a ⭐ on GitHub.

The project is intended to continue growing into a larger collection of interactive browser-based 3D environments, procedural experiments and real-time WebGL scenes.

---

**Built with HTML, JavaScript, Three.js and WebGL.**