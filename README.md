# Horologium

### Atelier 3D Watch Customizer

Horologium is an interactive browser-based 3D watch configurator built around **Three.js**.

Instead of presenting a traditional product page, the project creates a digital watch atelier where users can rotate a 3D timepiece, customize its materials, change the dial and strap, inspect complications, view live time, and experiment with an AR-style wrist preview.

> A frontend experiment focused on 3D product visualization, interaction design, real-time configuration, and premium visual presentation.

---

## ✦ Features

### 3D Watch Customization

Customize the watch directly in the browser:

* Case material
* Dial color
* Strap
* Automatic configuration updates
* Dynamic pricing
* Configuration reference code

Available case materials include:

```text
Steel
Brushed Steel
Yellow Gold
Rose Gold
Bronze
Platinum
Ceramic
Carbon
DLC Black
```

Available dials include:

```text
Midnight
Champagne
Salmon
Ivory
Emerald
Aubergine
Abyss
Panda
Tropical
```

Available straps include:

```text
Cordovan Brown
Alligator Black
Steel Bracelet
FKM Rubber
NATO Olive
Suede Tan
```

---

## ⌚ Interactive 3D View

The watch is rendered using Three.js with:

* Perspective camera
* Orbit controls
* Damped rotation
* Auto rotation
* Real-time zoom
* Physically based materials
* Environment lighting
* Directional lights
* Spot lighting
* Transparent sapphire-style crystal
* Subtle floor reflection

The user can drag the watch to orbit around it and scroll to zoom.

---

## 🕰️ Live Watch Movement

The hands are tied to the browser's current time.

The project updates:

* Hour hand
* Minute hand
* Second hand
* 30-minute counter
* 12-hour register
* Running seconds
* Date aperture

The seconds hand uses smooth time interpolation rather than jumping once per second.

---

## 🎨 Material System

The configurator uses Three.js physical materials to simulate different surfaces.

Material properties such as:

```text
Color
Metalness
Roughness
Clearcoat
```

are changed dynamically when the user selects a different case or dial.

Case transitions are animated rather than instantly swapped.

---

## 🔗 Strap System

The straps are procedurally constructed from Three.js geometry.

Different strap types receive different material treatments:

```text
Leather
Rubber
Fabric
Suede
Metal Bracelet
```

Some straps also receive procedural visual patterns such as:

* stitching
* alligator-style patterning
* fabric texture
* bracelet links
* buckle geometry

When the strap changes, the old strap animates away while the new strap enters the scene.

---

## 📷 AR Wrist Preview

Horologium includes an experimental camera-based preview mode.

When enabled, the browser requests webcam access and places the 3D watch over the camera feed.

Users can adjust:

```text
Scale
Position X
Position Y
Tilt
Rotation
```

A snapshot action combines the camera image and rendered watch into a PNG image.

### Important

This is an **AR-style visual preview**, not a full computer-vision wrist-tracking system. The watch positioning is manually controlled through the provided sliders.

---

## ⚙️ Configuration Panel

The right-hand configuration panel updates automatically as the watch is customized.

It displays:

```text
Case
Dial
Strap
Movement
Power Reserve
Frequency
Jewels
```

The interface also calculates a configuration total based on the selected components.

---

## 💰 Dynamic Pricing

The displayed price is calculated from:

```text
Base Price
+
Case Upgrade
+
Dial Upgrade
+
Strap Upgrade
```

The reference code also changes according to the selected configuration.

Example:

```text
HM7-AU-MI
```

The pricing system is part of the visual configurator experience and is not connected to a real commerce backend.

---

## 🔍 Complications

The watch includes interactive complication areas.

The interface provides:

```text
30-minute counter
12-hour register
Running seconds
Date aperture
```

Hovering over a subdial highlights it and displays a contextual tooltip.

---

## ✨ Interaction Details

The project contains many small interaction details intended to make the configurator feel like an actual atelier interface:

* Hover states
* Material selection feedback
* Animated configuration changes
* Floating watch movement
* Toast notifications
* Orbit compass
* Live FPS counter
* Loading sequence
* Camera mode transition
* Tooltip feedback
* Animated status indicator

These effects are intentionally layered around the central 3D experience rather than used as decoration alone.

---

## 🧱 Watch Construction

The watch is created procedurally from Three.js primitives.

The model contains components such as:

```text
Case
Bezel
Crown
Pushers
Lugs
Caseback
Dial
Chapter Ring
Hour Markers
Minute Track
Subdials
Date Aperture
Hour Hand
Minute Hand
Second Hand
Crystal
Strap
Buckle
```

Basic geometry includes:

```text
CylinderGeometry
SphereGeometry
TorusGeometry
BoxGeometry
CircleGeometry
RingGeometry
LatheGeometry
ExtrudeGeometry
```

This means the project does not depend on an imported watch model.

---

## 🧩 Architecture

At a high level:

```text
User Interaction
       │
       ▼
Configuration State
       │
       ├───────────────┐
       ▼               ▼
Three.js Model     UI Panels
       │               │
       ▼               ▼
Materials          Price / Specs
       │
       ▼
Renderer
       │
       ▼
Browser Canvas
```

The configuration state controls the visual model and the surrounding interface.

---

## 🛠 Technology

### Core

* HTML
* CSS
* JavaScript
* Three.js

### Three.js modules

The project uses:

* `OrbitControls`
* `RoomEnvironment`
* `PMREMGenerator`

### External resources

The interface currently uses:

* Tailwind CSS CDN
* Google Fonts
* Font Awesome
* Three.js CDN/import map

---

## 📱 Responsive Design

The layout adapts when the viewport becomes narrower.

On smaller screens:

* side panels stack
* the center viewport remains available
* controls remain accessible
* the interface becomes vertically organized

The project is primarily designed around a desktop/laptop 3D experience, while still providing a responsive fallback.

---

## ♿ Accessibility & Reduced Motion

The project includes a reduced-motion media query:

```css
@media (prefers-reduced-motion: reduce)
```

This reduces animation duration for users who have requested reduced motion at the system level.

Interactive controls also use semantic buttons and readable labels.

---

## 🚀 Running Locally

Clone the repository:

```bash
git clone https://github.com/hosseinb1111/Horologium.git
cd Horologium
```

Because the project is a client-side HTML application, it does not require a backend or build system.

You can serve it with any static HTTP server.

For example:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

A local HTTP server is recommended instead of opening the file directly, particularly for browser features such as webcam access.

---

## 📂 Repository Structure

The project is intentionally compact.

```text
Horologium/
└── index.html
```

The current implementation keeps the entire experience in one HTML document containing:

```text
Markup
Styles
Configuration data
Three.js scene
Watch geometry
Material system
Animation logic
AR preview
UI logic
Notifications
Particle system
```

---

## 🔬 What This Project Explores

Horologium is primarily a frontend and graphics experiment exploring:

* WebGL product visualization
* Three.js
* procedural 3D geometry
* physically based materials
* real-time UI state
* interactive configurators
* animation
* camera-based compositing
* responsive interface design
* premium product presentation

The project combines a traditional product configurator with an interactive digital atelier concept.

---

## 🎯 Design Direction

The visual language is inspired by:

* traditional watchmaking
* luxury ateliers
* dark materials
* warm metallic tones
* editorial typography
* precision instruments

The goal is not to recreate a specific watch brand's interface, but to build an original digital environment around mechanical-watch aesthetics.

---

## 👤 Author

**Hossein Seyed Bagheri**

Computer Engineering student and developer interested in web development, AI applications, interactive software, Cloudflare systems, realtime applications, and technical experiments.

---

## 🔗 Repository

**GitHub**

https://github.com/hosseinb1111/Horologium

---

## 📄 License

This project is licensed under the **MIT License**.

See the [`LICENSE`](LICENSE) file for the full license text.
