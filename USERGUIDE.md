# VERSION 1 Animation Editor — User Guide

## Getting Started

1. Open `version1_editor.html` in your browser (Safari, Chrome, or Firefox)
2. The animation plays live in the preview panel on the right
3. Adjust any controls in the left sidebar
4. Click **Update Preview** to apply your changes
5. When happy, use **Record Video** or **Download HTML** to export

## Editor Layout

- **Left sidebar**: all controls, grouped into collapsible sections — click a section header to expand/collapse
- **Right panel**: live animation preview
- **Bottom bar**: Update Preview, Download HTML, Record Video, Reset Defaults

---

## Sections

### Saved Layouts

Save and load your configurations. Layouts are stored in your browser's local storage — they persist across sessions but are browser-specific.

- **Save**: type a name and click Save
- **Load**: select a layout from the dropdown and click Load
- **Delete**: select a layout and click Delete (you'll be asked to confirm)

Note: uploaded images (logos, background photos) are NOT saved in presets due to storage limits. You'll need to re-upload images after loading a preset.

---

### Global

| Control | What it does |
|---------|-------------|
| **Loop Duration (ms)** | How long one loop of the animation lasts. 16000 = 16 seconds. Set this before recording. |
| **BPM** | Beats per minute — controls the speed of the kick-synced pulse, spectrum analyser, and waveform. Match this to your track. |
| **Background Colour** | The canvas background colour. Default is black (#000000). Change to white if using a dark logo, or any colour you like. |
| **Background Image** | Upload a photo (e.g. a shot of you DJing) to use as the background. The image is cover-fitted to fill the 1080x1920 canvas. Click **Clear** to remove it. |

---

### Logos

Each logo is an image that appears on the canvas with its own position, size, fade timing, and optional parallax entrance/exit.

By default there is one logo (Logo 1) which uses `logo.png`. You can:

- **Upload a different image** per logo (png, jpg, svg) — click "Upload image" in the logo panel
- **Add more logos** — click "+ Add Logo" to layer multiple images
- **Remove logos** — click the X button on any logo panel (Logo 1 cannot be removed as it's used by the pulsing effect and background logos)

| Control | What it does |
|---------|-------------|
| **Image** | Upload a custom image or use the default logo.png |
| **Y Position** | Vertical position (0.1 = near top, 0.9 = near bottom) |
| **Size** | Width as a fraction of canvas width (0.82 = 82% of canvas width) |
| **Fade In / Fade Out (ms)** | How long the logo takes to appear/disappear |
| **Parallax entrance** | When enabled, the logo slides in from a starting position and slides back out at the end for a seamless loop |
| **Parallax Start Y** | Where the logo starts before sliding in (-0.3 = above the canvas) |
| **Parallax Duration (ms)** | How long the parallax slide takes |

---

### Pulsing Logo

A beat-synced ghost copy that pulses outward on each kick. Creates an energetic club feel. By default it uses Logo 1's image, but you can upload a different image specifically for the pulse effect.

| Control | What it does |
|---------|-------------|
| **Pulse Image** | Upload a custom image for the pulse effect, or leave as default to use Logo 1's image. Click **Clear** to revert to Logo 1. |
| **Enabled** | Turn the pulse effect on/off |
| **Y Position** | Where the pulse ghost appears (independent of the main logo position) |
| **Start Time (ms)** | When in the loop the pulse effect begins (e.g. 10000 = starts at 10 seconds) |
| **Opacity** | Maximum brightness of the pulse ghost (0.85 = 85%) |
| **Max Scale** | How large the pulse expands (2.0 = doubles in size at peak) |

The pulse fades out naturally with the beat phase — it's bright on the kick and fades between beats.

---

### Text Boxes

All text elements are text boxes. By default there are two:

1. **Text Box 1** — DJ names (border OFF by default)
2. **Text Box 2** — Event info with a red border (border ON by default)

You can add as many text boxes as you want. Each has independent controls.

| Control | What it does |
|---------|-------------|
| **Text** | The text content. Use `\n` for line breaks (e.g. `LINE ONE\nLINE TWO`) |
| **Font** | Choose from built-in fonts (Bungee, Arial Black, Bebas Neue, Impact, etc.) or upload a custom font file (.ttf, .otf, .woff, .woff2) |
| **Y Position** | Vertical position on canvas (0.1 = top, 0.98 = bottom) |
| **Font Size (px)** | Size in pixels. The canvas is 1920px tall, so use sizes like 80-150 for clearly visible text. Max is 300. |
| **Fade In Time (ms)** | When in the loop this text starts appearing |
| **Text Colour** | The colour of the text (default white) |
| **Border** | Toggle the rounded border on/off |
| **Border Width (px)** | Thickness of the border line (only shown when border is ON) |
| **Border Colour** | Colour of the border (only shown when border is ON) |
| **Corner Radius (px)** | Roundness of border corners (only shown when border is ON) |

Tips:
- Font sizes are in canvas pixels (1080x1920). Size 64 looks small — try 100+ for headings.
- All text boxes automatically fade in and fade out symmetrically for a seamless loop.
- Text is always horizontally centred on the canvas.

---

### Spectrum EQ

A segmented spectrum analyser (like a graphic EQ) that reacts to simulated audio.

| Control | What it does |
|---------|-------------|
| **Enabled** | Turn the spectrum analyser on/off |
| **Height (px)** | Total height of the bars in canvas pixels |
| **Bottom Offset (px)** | Distance from the bottom of the canvas |
| **Bar Count** | Number of frequency bars (8-64) |

The bars are coloured in three zones:
- **Green** (bottom 75%) — low/mid frequencies
- **Amber** (next 18.75%) — upper-mid frequencies
- **Red** (top 6.25%) — high/peak frequencies

White peak indicators sit at the top of each bar.

---

### Waveform

A cyan waveform line that reacts to the simulated audio spectrum. Drawn as the topmost layer.

| Control | What it does |
|---------|-------------|
| **Enabled** | Turn the waveform on/off |
| **Y Center** | Vertical centre position of the waveform |
| **Height (px)** | Vertical range the waveform can swing |
| **Line Width (px)** | Thickness of the waveform line |

The waveform has a cyan glow and a subtle fill beneath it.

---

### Background Logos

Scrolling logo layers that move across the canvas at various sizes, speeds, opacities, and directions. Creates depth and movement behind the main content.

By default there are 8 layers. You can add, remove, or edit each one.

| Control | What it does |
|---------|-------------|
| **Logo Image** | Upload a different image for this layer, or use the default logo.png |
| **Scale** | Size of the scrolling logo relative to canvas width (1.0 = full width, 3.0 = 3x canvas width) |
| **Y/X Position** | Cross-axis position. For horizontal/diagonal directions this is vertical position (0.0 = top, 1.0 = bottom). For vertical directions (12 or 6) this becomes horizontal position (0.0 = left, 1.0 = right). |
| **Speed** | Scroll speed (higher = faster) |
| **Direction** | Clock-face picker with 12 directional paths. 12 = up, 3 = right, 6 = down, 9 = left. Diagonal positions (1, 2, 4, 5, 7, 8, 10, 11) move at the corresponding angle. Click a dot on the clock face to select. |
| **Opacity** | Transparency of this layer (0.05 = barely visible, 0.50 = half opacity) |

Each layer automatically fades in/out at loop boundaries. If parallax is enabled on Logo 1, background logos also shift vertically during the parallax entrance/exit (except for vertical-direction layers).

---

### Effects

Visual effects overlaid on the animation. All are on by default. Each can be toggled independently.

| Effect | What it does | Visibility |
|--------|-------------|------------|
| **Glitch** | RGB split, horizontal slice displacement, and noise rectangles. Bursts at the start and end of the loop, with occasional random glitches in the middle. | **High** — clearly visible |
| **Scanlines** | Thin horizontal black lines every 4px across the entire canvas at ~5% opacity. Simulates a CRT monitor. | **Very subtle** — most visible on light backgrounds |
| **Grid** | Red vertical and horizontal lines every 60px at ~4% opacity. Gently sways side to side. | **Very subtle** — look for faint red lines |
| **Light Sweeps** | A white gradient bar that sweeps horizontally across the logo area. Occurs at 3 specific moments during the loop (10-20%, 45-55%, 70-78%). | **Subtle** — watch the logo area for a brief white shimmer |
| **Corner Accents** | Small red L-shaped marks in each corner of the canvas at 30% opacity. | **Subtle** — look at the corners |
| **Vignette** | Darkens the edges and corners using a radial gradient. Strengthens near loop boundaries to help fade to black. | **Always present** — most noticeable when you toggle it off (edges become brighter) |

---

## Exporting

### Download HTML

Click **Download HTML** to save a standalone HTML file with your current settings baked in. This file can be opened in any browser without the editor — perfect for sharing or archiving.

Uploaded images (logos, background photos) are embedded in the downloaded file as data URLs.

### Record Video

1. Set **Loop Duration** in Global to your desired length
2. Set **Loops** count (next to the Record button) for how many cycles to capture
3. Click **Record Video**
4. A recording overlay appears with a progress bar
5. When complete, the video file downloads automatically

**Format**: Safari produces MP4 (ready for Instagram). Chrome/Firefox produce WebM — convert to MP4 using [CloudConvert](https://cloudconvert.com) or [HandBrake](https://handbrake.fr).

The video file appears in your Downloads folder as `version1_animation.mp4` or `version1_animation.webm`.

---

## Tips

- **Always click "Update Preview"** after making changes — controls don't update live
- **Seamless looping**: all elements automatically fade in at the start and fade out at the end of each loop. The parallax entrance reverses at the end. This means the first and last frames are identical (black), so the loop is seamless.
- **Font choice**: Bungee is the VERSION 1 brand font. Bebas Neue renders ALL CAPS only. Arial Black is a good fallback for mixed case.
- **Large text**: the canvas is 1080x1920 pixels. Font size 64 looks small — use 100-150 for headings.
- **Background combos**: try a dark photo with a transparent/white logo, or a solid colour with effects like grid and scanlines for a retro feel.
- **Performance**: if the preview is slow, try turning off some effects (glitch is the most CPU-intensive).

## File Structure

| File | Purpose |
|------|---------|
| `version1_editor.html` | The visual editor — open this |
| `version1_animation_v5.html` | The animation engine (loaded in the editor's preview) |
| `logo.png` | Default VERSION 1 logo |
| `logo_transparent.png` | Logo with transparent background |
| `font/Bungee-Regular.ttf` | Bungee font (VERSION 1 brand font) |
| `archive/` | Previous animation versions (v1-v4) |
