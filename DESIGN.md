# Design System Strategy: The Guardian’s Lens

## 1. Overview & Creative North Star: "The Guardian’s Lens"
This design system moves away from the sterile, "utilitarian" map interface. Instead, it adopts the **Guardian’s Lens**—a creative North Star that balances authoritative reliability with approachable, atmospheric depth. 

We break the "standard template" look through **Tonal Layering** and **Intentional Asymmetry**. Rather than a rigid grid of boxes, we treat the UI as a living map where information floats on sophisticated, semi-transparent surfaces. By utilizing high-contrast editorial typography (Manrope) against a functional body (Inter), we elevate "safety data" into a premium, trustworthy experience. We prioritize breathing room over borders, and depth over flat lines.

## 2. Colors & Atmospheric Depth
The palette is rooted in a core of `primary` Deep Blue to signal institutional trust, punctuated by high-signal `secondary` and `tertiary` tones for immediate hazard recognition.

### The "No-Line" Rule
**Strict Mandate:** 1px solid borders for sectioning are prohibited. 
Boundaries must be defined solely through background color shifts. For instance, a side-panel using `surface-container-low` should sit directly against a map or a `surface` background. The eye should perceive the change in elevation through the shift in hex value, not a structural line.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of fine, matte paper.
*   **Base Layer:** `surface` (#f4faff) – The primary canvas.
*   **Secondary Content:** `surface-container-low` (#e9f6fd) – For non-essential background regions.
*   **Interactive Cards:** `surface-container-highest` (#d7e4ec) – For floating map details.
*   **Nested Elements:** Place a `surface-container-lowest` (#ffffff) card inside a `surface-container-high` (#ddeaf2) tray to create a soft, natural lift.

### The "Glass & Gradient" Rule
To avoid a "flat" default look, floating map overlays (like weather alerts or search bars) should utilize **Glassmorphism**.
*   **Formula:** `surface` at 80% opacity + `backdrop-blur: 12px`.
*   **Signature Textures:** Use a subtle linear gradient (from `primary` #00327d to `primary-container` #0047ab) for main Action Buttons to give them a "jewel-like" presence on the map.

## 3. Typography: Editorial Authority
We utilize a dual-font system to balance character with legibility.

*   **Display & Headlines (Manrope):** Large-scale headers use `display-lg` to `headline-sm`. These are your "Anchors." They provide a high-end editorial feel that communicates "This is the definitive source of truth."
*   **Title & Body (Inter/Pretendard):** For functional data (CCTV locations, Hospital names), use `title-md` and `body-md`. These are optimized for rapid scanning in high-stress situations.
*   **Visual Hierarchy:** Use `on-surface-variant` (#434653) for secondary metadata to ensure the `on-surface` (#111d23) titles pop with maximum contrast.

## 4. Elevation & Depth
Depth is a functional tool, not a decoration. It communicates what is "on top" of the map and ready for interaction.

### The Layering Principle
Avoid "Drop Shadows" as a default. Use **Tonal Stacking**. 
*   *Example:* A "Hospital Information" drawer should use `surface-container-highest`. Inside it, specific action chips should use `surface-container-lowest`. The 2-step jump in container tone creates a "recessed" or "elevated" effect without a single pixel of shadow.

### Ambient Shadows
When a floating effect is required (e.g., a "Current Location" button), use **Ambient Shadows**:
*   **Specs:** `box-shadow: 0 8px 32px rgba(17, 29, 35, 0.06);` 
*   The shadow color must be a tinted version of `on-surface` at 6% opacity, never pure black. This mimics natural light.

### The "Ghost Border" Fallback
If accessibility requirements demand a border, use a **Ghost Border**:
*   **Token:** `outline-variant` (#c3c6d5) at 20% opacity. It should feel like a suggestion of a line, not a hard stop.

## 5. Components & Interface Primitives

### Buttons
*   **Primary:** Rounded `xl` (1.5rem). Gradient background (`primary` to `primary-container`). White `on-primary` text.
*   **Secondary:** `surface-container-highest` background with `primary` text. No border.
*   **States:** Hover should increase the background brightness; active/pressed should "sink" by using `surface-dim`.

### Cards & Lists
*   **Constraint:** Zero dividers. 
*   **Separation:** Use `spacing-6` (1.5rem) of vertical white space or a subtle shift from `surface-container-low` to `surface-container-highest` to distinguish between different safety alerts.
*   **Corners:** All cards must use `rounded-lg` (1rem) for a modern, friendly feel.

### Safety Markers (Map Icons)
*   **CCTV/Shelter:** High-contrast `on-primary` icons sitting on `primary` circular backgrounds with an `xl` roundedness.
*   **Air Quality Chips:**
    *   *Good:* `tertiary` (#00400c)
    *   *Moderate:* `secondary` (#7e5700)
    *   *Bad/Very Bad:* `error` (#ba1a1a)
    *   *Styling:* These should be "Pill" shapes (`rounded-full`) with `label-md` typography.

### Input Fields
*   **Style:** `surface-container-low` background, no border. On focus, transition to `surface-container-lowest` with a "Ghost Border" of `primary` at 20% opacity.

## 6. Do’s and Don’ts

### Do
*   **Do** use `surface-container` shifts to group related safety data.
*   **Do** use `manrope` for large numerical data (e.g., "98% Air Quality") to give it a premium feel.
*   **Do** favor `spacing-8` (2rem) and `spacing-10` (2.5rem) to ensure the interface never feels "cramped" during an emergency.

### Don't
*   **Don't** use 1px solid lines to separate list items. Use white space.
*   **Don't** use pure black (#000000) for shadows or text. Use `on-surface` (#111d23).
*   **Don't** use `rounded-none`. In a safety app, sharp corners feel aggressive; use `rounded-md` as your minimum.
*   **Don't** use high-saturation yellows for non-critical info. Reserved `secondary` (Amber/Yellow) strictly for "Caution."