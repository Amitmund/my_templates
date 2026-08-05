You are an expert Principal Frontend Engineer and Design Systems Architect. Your task is to generate a single-file, production-ready HTML/CSS/JS application called "Creator Canvas Pro" — a universal visual studio for creating content cover assets (YouTube thumbnails, podcast art, course covers, etc.).

Generate the complete, self-contained HTML file without using external dependencies or frameworks. Implement the exact layout, features, styling, and interactive behaviors detailed below:

---

### 1. LAYOUT & UI ARCHITECTURE
Create a 3-column application layout (`.app`):
- Left Sidebar (330px): Form controls for design intent, aspect ratio, custom gradient, visual treatment, color palette, composition layout, hero image, typography/message inputs, and optional module chips.
- Stage (Flex Center / Dark Canvas): Houses the aspect-ratio constrained canvas frame (`.frame`), top toolbar with aspect ratio indicator, and dark radial-gradient background.
- Right Inspector (310px): Contains the "Layers & Position" control panel followed by the "Live Design Readout" summary stats.

---

### 2. VISUAL STYLING & DESIGN SYSTEM
- Theme Variables: Dark UI theme (`#07090d` background, `#10141b` panels, `#29313d` borders) with CSS custom properties for `--accent` and `--accent2`.
- Custom Gradient Engine: Support a 2-color custom gradient with selectable angle directions (`90deg`, `120deg`, `135deg`, `180deg`, `225deg`, `270deg`). Accent words within the headline and custom gradient text should automatically utilize this gradient.
- Visual Treatments: Include options for "Tech Editorial", "Minimal Studio", "Breaking Alert", "Luxury Product", and "Bold Creator". Each treatment updates subtle background grid lines, network particle overlays, glow intensities, border styles, and headline letter-spacing.
- Color Swatches: Provide preset buttons (Cyber Cyan, NVIDIA Green, Cyber Blue, Alert Orange, Neon Purple, Crimson Red, Electric Gold, Cyber Lime, Hot Pink, Mono White) + raw color pickers.

---

### 3. CANVAS COMPOSITION & MOCKUP ENGINE
- Aspect Ratios: Support 16:9, 4:3, 3:2, 1:1, 4:5, 9:16, 2:3 via CSS `aspect-ratio` on the `.frame`.
- Dynamic Layout Modes: Support 5 photo layouts (`photo-left`, `photo-right`, `photo-top`, `photo-bottom`, `photo-center`).
- Hero Image Shapes & Fits:
  - Shapes via `clip-path` or `border-radius`: Angled, Rounded, Circle, Hexagon, Diamond, Arch, Cut Corner, Square.
  - Fits: Contain, Cover, Original.
- Layer Architecture inside the Cover (`.cover`):
  1. `backgroundLayer` (Full-canvas background image with blend overlay).
  2. `upperTextLayer` (Large background watermark text behind the hero/content).
  3. Ambient overlays (`gridbg`, `glow`, `net` particle graph, `safeGuide` safe-area dashed box).
  4. `canvasMeta` (Top right label) & `canvasCorner` (Bottom left label).
  5. `composition` (`copy` container holding Eyebrow/Tag, Headline, Special Phrase, Subhead, Metric, Micro, Chips; and `visual` holding Badge + Hero `photoBox`).
  6. `bottomBrand` (Bottom right brand tag).

---

### 4. ADVANCED TYPOGRAPHY & MESSAGE CONTROLS
- Headline Accent Highlighting: Automatically parse comma-separated "Accent Words". Any matching word inside the headline dynamically wraps in `<span class="accentWord">` (or `.gradientText`).
- Special Phrase Module: Dedicated text entry rendered separately from the main headline with selectable web-safe handwriting/serif/sans fonts and custom color controls.
- Independent Upper Text (Background Layer 02):
  - Compact bounding box fitting strictly around text (`width: max-content`, centered via transform).
  - Configurable font-weight dropdown (900, 800, 700, 500).
  - Letter outline/stroke toggle (`-webkit-text-stroke`).
  - **SEPARATE Custom Gradient System**: Independent toggle, custom Color 1, Color 2, and Gradient Direction dropdown that works strictly on the Upper Text without altering the main accent gradient.

---

### 5. LAYERS & POSITION SYSTEM (Interactive Canvas Engine)
Implement a robust 2D transform and interactive layer system in vanilla JavaScript:
- Layer Registry: Track 15 separate, un-nested layers:
  1. Background Image
  2. Upper Text
  3. Hero Visual
  4. Tag / Eyebrow
  5. Headline
  6. Special Phrase
  7. Subhead
  8. Metric
  9. Micro Description
  10. Chips / Tags
  11. Badge
  12. Bottom Brand
  13. Top Meta
  14. Corner Text
  15. Network Graphic
- Layer Transform Matrix: Every layer maintains independent state values for `x`, `y`, `zIndex`, `opacity`, `scale` (10% to 500%), and `angle` (0° to 360°).
- CSS Render Engine: Apply transforms via `translate(x, y) rotate(angle) scale(scale)` alongside `z-index` and `opacity`.

- On-Canvas Interactivity & UI Feedback:
  - Active Selection: Clicking any canvas layer or dragging its handle outlines the element with a dashed accent border (`.layer-active`). Clicking outside deselects it.
  - Direct Dragging: Click-and-drag any element on the canvas to move it in real-time.
  - Corner Resize Handles: Attaches 4 circular corner handles (`.se`, `.nw`, `.ne`, `.sw`) on the active selection bounding box. Dragging any handle scales the layer while strictly preserving its original aspect ratio.
  - Top Rotation Handle: Attaches a dedicated top circular handle (`.rotate-handle` styled in pink/accent with a stem line) centered above the active layer. Dragging this handle dynamically rotates the element between 0° and 360° based on its center angle.

- Right Inspector Panel Controls ("Layers & Position"):
  - Render an itemized control row for all 15 layers.
  - Each row includes: Layer Title, Fallback Drag Handle (`.drag-handle-btn` for easy dragging of full-canvas or overlapping elements), numeric Z-Index input, Opacity range slider (0–1), Scale (%) numeric input, and Angle (°) numeric input.
  - All inputs bidirectionally synchronize with canvas interactions in real-time.

---

### 6. EVENT HANDLING & AUTO-RELOAD
- Automatically generate network particle nodes and SVG/CSS connection lines on load.
- Ensure all inputs (text, colors, file uploads, toggles, layout selectors) dynamically update the canvas and readout stats without re-initializing layer positions or causing screen flashes.
- Ensure image file uploads (`FileReader`) maintain local object URLs without external requests.

Deliver the entire application in a single HTML code block with embedded CSS and JavaScript.
