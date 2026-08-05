Build a polished, production-quality, single-page web application called:

CREATOR CANVAS PRO

It is a visual cover/thumbnail composition editor designed primarily for YouTube covers, video thumbnails, feature stories, technology/editorial covers, creator branding, and social media graphics.

IMPORTANT:
Do not create a generic form-based image generator.

The application should feel like a lightweight visual composition/design tool where the user controls structured layers, typography, images, colors, gradients, and layout while seeing a live preview.

Use only:
- HTML
- CSS
- Vanilla JavaScript

No backend.
No framework required.
The entire application should work locally by opening the HTML file.

==================================================
1. CORE EXPERIENCE
==================================================

Create a two-panel application:

LEFT:
A professional control panel/sidebar containing all editing controls.

RIGHT:
A large live canvas/preview.

Every important control must update the preview immediately without requiring a refresh or submit button.

The UI should feel modern, premium, technical/editorial, and suitable for a professional creator.

Use a dark interface with subtle borders, compact controls, good spacing, and clear section headings.

Do not make the interface unnecessarily flashy.

==================================================
2. CANVAS
==================================================

The canvas should support configurable aspect ratios.

Include at least:

- 16:9
- 4:3
- 1:1
- 4:5
- 9:16
- 21:9

The preview should actually change its proportions when the user selects an aspect ratio.

The composition must remain responsive inside the selected canvas.

Do NOT crop user images unnecessarily.

Where possible, use:
object-fit: contain

for hero images when the user wants the entire image visible.

Allow the image box to adapt while maintaining the selected shape.

==================================================
3. FOUR-LAYER VISUAL SYSTEM
==================================================

The composition must use four conceptual layers.

Layer 1 — BACKGROUND IMAGE
Layer 2 — UPPER TEXT
Layer 3 — HERO IMAGE
Layer 4 — REGULAR CONTENT

Exact stacking order:

Regular Text
    ↑
Hero Image
    ↑
Upper Text
    ↑
Background Image

The user must be able to upload an optional Background Image.

The Background Image should fill the complete canvas.

Typical use cases:
- system architecture diagrams
- technical diagrams
- UI screenshots
- abstract technical artwork
- data center imagery
- circuit/system graphics
- environmental images
- textures

Background image controls:
- Upload
- Opacity
- Object positioning
- Optional blur
- Optional scale

The background should blend naturally into the composition.

==================================================
4. UPPER TEXT LAYER
==================================================

Add an optional "Upper Text" field.

This text is positioned:

ABOVE the Background Image
BEHIND the Hero Image
BEHIND the Regular Text

This allows large oversized typography to partially disappear behind the hero image.

Example:

SYSTEM
ARCHITECTURE

The Hero Image should visually cover portions of this text.

Controls:
- text
- font size
- font family
- opacity
- letter spacing
- alignment
- position
- optional gradient
- optional rotation

==================================================
5. HERO IMAGE
==================================================

Provide a dedicated Hero Image upload area.

Allow the user to upload an image from their computer.

The Hero Image must support these positions:

- Photo Left
- Photo Right
- Photo Top
- Photo Center
- Hero Bottom

"Hero Bottom" means:

TEXT
TEXT
TEXT

HERO IMAGE

"Photo Top" means:

HERO IMAGE

TEXT
TEXT

Fix the vertical spacing carefully.

Do not allow the hero image to push the text excessively downward.

==================================================
6. HERO IMAGE SHAPES
==================================================

Support multiple hero shapes.

At minimum:

- Rectangle
- Rounded Rectangle
- Circle
- Oval
- Square
- Hexagon
- Diamond
- Angled
- Capsule

The shapes must actually clip the image.

Do NOT simply draw a border around a rectangle and call it a shape.

Use CSS clip-path, border-radius, masks, or another reliable method.

The image itself must be clipped.

Circle must be a true circle.

==================================================
7. HERO IMAGE BLENDING
==================================================

Add separate controls for:

Hero Image Opacity
Hero Border Opacity
Hero Box Blend

These must be independent.

Hero Image Opacity:
Controls the opacity of the actual image.

Hero Border Opacity:
Controls only the visible border around the hero image.

Hero Box Blend:
Controls the background/container behind the hero image.

The purpose is to allow the hero image to remain clear while making its rectangular container visually disappear into the background.

Example starting values:

Hero Image: 100%
Hero Border: 10%
Hero Box Blend: 5%

==================================================
8. REGULAR TEXT SYSTEM
==================================================

Include editable fields for:

- Eyebrow
- Headline
- Subtitle
- Special Word / Phrase
- Metric / Proof Point
- Proof Point Label
- Description
- Tech Specs
- Badge / Tag
- Metadata
- Corner Label
- Brand / Channel

Every text field must update live.

==================================================
9. PROOF POINT
==================================================

Do NOT hardcode "PROOF POINT".

Create two separate editable fields:

Proof Point Label

Example:
PROOF POINT

Metric / Proof Point

Example:
50% faster · 2× throughput · Verified

The user can rename the label.

Possible labels:
- RESULT
- BENCHMARK
- KEY STAT
- PERFORMANCE
- VERIFIED
- WHY IT MATTERS

==================================================
10. SPECIAL WORD / PHRASE
==================================================

Add a separate field:

Special Word / Phrase

Example:

with Community

This should be visually independent from the main headline.

The Special Word should support different typography from the headline.

Provide font choices such as:

- Handwritten Script
- Casual Handwritten
- Marker Hand
- Signature Script
- Poster Condensed
- Editorial Serif
- Tech Mono
- Rounded Sans
- Heavy Display

The Special Word should NOT automatically inherit the accent gradient.

Give it its own:

Special Word Color

By default use a light/base color such as white or warm white.

This allows compositions such as:

ACTIONABLE ROADMAP
with Community

where "ACTIONABLE ROADMAP" uses the main theme while "with Community" looks handwritten and remains a neutral/base color.

==================================================
11. MULTIPLE ACCENT WORDS
==================================================

This is extremely important.

Do NOT provide only one Accent Word.

Create:

Accent Words — comma separated

Example:

AI, INTERNET, CHANGING, RTX 5090

If the headline is:

THE INTERNET IS CHANGING WITH AI

then:

INTERNET
CHANGING
AI

should ALL receive the same accent treatment.

Support both:
- individual words
- multi-word phrases

Example:

RTX 5090, AI, 2x faster

The matching must be case-insensitive.

Sort terms longest-first before creating the matching regex so phrases are not broken by shorter terms.

The user must be able to enter any number of comma-separated accent terms.

==================================================
12. GRADIENT THEME SYSTEM
==================================================

Do NOT make themes only single colors.

Themes should be gradient systems.

Create presets such as:

NVIDIA Green → Emerald · 135°

Cyber Blue → Electric Violet · 135°

Alert Orange → Crimson · 135°

Neon Purple → Magenta · 135°

Crimson Red → Hot Coral · 135°

Aurora Cyan → Violet · 120°

Sunset Gold → Orange → Pink · 120°

Ocean Blue → Teal · 145°

Each theme should define:

- Color 1
- Color 2
- Gradient Direction

Some themes may optionally contain 3 colors.

The selected theme should control the overall accent visual language.

==================================================
13. CUSTOM ACCENT GRADIENT
==================================================

Add:

Custom Accent Gradient

Controls:

Color 1
Color 2
Gradient Direction

Direction choices:

90° — Left → Right
120° — Diagonal
135° — Rising Diagonal
180° — Right → Left
225° — Falling Diagonal
270° — Bottom → Top

The custom gradient should be used by:

- Accent Words
- Gradient Text
- appropriate theme accent elements

==================================================
14. GRADIENT TEXT
==================================================

Allow gradient text styling.

The user should be able to enable/disable gradient text.

When enabled, the selected text should use the configured two-color gradient.

Do not automatically turn every piece of text into a gradient.

The design should remain readable.

==================================================
15. BRAND / CHANNEL
==================================================

Brand / Channel should appear in the bottom-right corner.

It must NOT overlap:

- Top-right labels
- Corner labels
- Main content

Keep enough safe spacing around it.

==================================================
16. META / CORNER LABELS
==================================================

Make these independently editable.

Example:

TECH // ORIGINAL

and

01 / 04 · FEATURE STORY

Both must have their own fields.

Do not hardcode these values.

==================================================
17. COLOR SYSTEM
==================================================

Provide:

Primary Theme
Secondary Accent
Custom Gradient

The UI should make it obvious that:

Primary Theme = overall visual language

Secondary Accent = supporting accent

Custom Gradient = two-color gradient system

==================================================
18. RESPONSIVE COMPOSITION
==================================================

The design must adapt to different canvas aspect ratios.

Do not simply resize the entire canvas.

Recalculate the composition appropriately.

For example:

16:9:
horizontal composition

9:16:
vertical composition

1:1:
balanced square composition

The user should not see text accidentally clipped when switching aspect ratios.

==================================================
19. IMAGE HANDLING
==================================================

When an image is uploaded:

- preview immediately
- do not upload to a server
- use local browser object URLs
- revoke old object URLs where appropriate
- do not crop unless the user explicitly chooses crop behavior
- preserve image visibility
- allow opacity adjustment

For hero image shapes, clip the image itself.

==================================================
20. LIVE PREVIEW
==================================================

Every input must update instantly.

Examples:

Change headline
→ preview updates immediately.

Change accent words
→ all matching words update immediately.

Change theme
→ gradient changes immediately.

Change gradient direction
→ preview changes immediately.

Upload background
→ background appears immediately.

Change background opacity
→ image fades immediately.

Change hero opacity
→ hero fades immediately.

Change hero border opacity
→ border changes immediately.

Change special font
→ special word changes immediately.

Change aspect ratio
→ canvas proportions change immediately.

==================================================
21. DESIGN QUALITY
==================================================

The final result should look like a professional design tool.

Avoid:
- generic Bootstrap-like styling
- excessive rounded cards
- oversized controls
- clutter
- unnecessary animations
- childish colors
- excessive shadows

Use:
- compact controls
- dark UI
- subtle borders
- strong typography
- clean hierarchy
- premium editorial/technical aesthetic

==================================================
22. IMPORTANT USABILITY REQUIREMENTS
==================================================

Each section should have a clear title.

Suggested sidebar sections:

01 · Content
02 · Typography
03 · Theme & Gradient
04 · Background Layer
05 · Hero Image
06 · Composition
07 · Image Blending
08 · Branding
09 · Metadata

Add short helper text where a feature may not be self-explanatory.

For example:

Accent Words — comma separated

Example:
AI, INTERNET, CHANGING, RTX 5090

And:

Hero Box Blend

"Controls how strongly the hero container blends into the background."

==================================================
23. NO BROKEN CONTROLS
==================================================

Before finishing, test every control.

Specifically verify:

- multiple accent words work
- phrases work
- accent matching is case insensitive
- theme gradients change
- custom gradient changes
- gradient angle changes
- special word font changes
- special word color changes
- background upload works
- background opacity works
- hero upload works
- hero opacity works
- hero border opacity works
- hero box blend works
- circle shape is actually circular
- other shapes actually clip the image
- Photo Top doesn't push text too far down
- Hero Bottom works
- aspect ratio actually changes the canvas
- text doesn't unexpectedly get clipped
- brand doesn't overlap corner labels

==================================================
24. FILE STRUCTURE
==================================================

For the first version, make it a single self-contained HTML file.

Include:

<style>
...
</style>

<script>
...
</script>

No external dependencies unless absolutely necessary.

The file must work by double-clicking it in a browser.

==================================================
FINAL GOAL
==================================================

The result should feel like:

A lightweight Canva/Figma-style structured composition editor specifically optimized for YouTube covers and editorial/technical creator graphics.

It should be easy for a non-designer to use, but powerful enough to create sophisticated layered compositions.

Prioritize:
1. Reliability
2. Live preview
3. Correct layer ordering
4. Typography quality
5. Image blending
6. Gradient system
7. Responsive aspect ratios
8. Clean UI

Do not remove working features when adding new ones.

When adding a new feature, preserve all existing functionality.
