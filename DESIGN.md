# Design System Specification: Kinetic Robotics & Educational Interface

## 1. Overview & Creative North Star: "The Digital Lab"
The Creative North Star for this design system is **"The Digital Lab."** Unlike generic educational platforms that feel static or "childish," this system adopts an editorial, high-tech aesthetic that mirrors a professional robotics laboratory. 

It breaks the "template" look by utilizing **intentional asymmetry** and **kinetic layering**. We move away from the rigid, centered grid. Instead, we use large, offset display type and overlapping "glass" containers to create a sense of movement. This reflects the physical nature of robotics—parts moving, sensors reacting, and logic flowing. The interface should feel like a sophisticated heads-up display (HUD) that is both authoritative for professional developers and inspiring for students.

---

## 2. Colors & Surface Logic
The palette is built on a high-contrast foundation of `surface` (#131313) and `primary` (#82CFFF). 

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders for sectioning. Structural boundaries must be defined solely through background color shifts. For example, a `surface-container-low` section sitting on a `surface` background provides all the separation necessary.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. We use the Material surface tiers to create "nested" depth:
*   **Base:** `surface` (#131313) - The primary canvas.
*   **Primary Containers:** `surface-container` (#20201F) - For main content modules.
*   **Emphasis Layers:** `surface-container-high` (#2A2A2A) - For interactive elements or nested "logic blocks."
*   **Elevated Components:** `surface-container-highest` (#353535) - For floating menus or active state cards.

### The "Glass & Gradient" Rule
To escape the "flat" look, main CTAs and Hero backgrounds must utilize **Signature Textures**. 
*   **CTAs:** Use a linear gradient from `primary` (#82CFFF) to `primary-container` (#00AEEF) at a 135-degree angle.
*   **Floating Elements:** Use `surface-variant` (#353535) with a 60% opacity and a `20px` backdrop-blur to create a "frosted tech" feel.

---

## 3. Typography: The Editorial Engine
We pair the technical precision of **Space Grotesk** (Display/Headlines) with the functional clarity of **Inter** (Body/Labels).

*   **Display (Space Grotesk):** Use `display-lg` (3.5rem) for hero titles. Don't be afraid to use `-0.04em` letter spacing for a tighter, more "engineered" look.
*   **Headlines (Space Grotesk):** `headline-md` (1.75rem) serves as the primary anchor for modules.
*   **Body (Inter):** `body-lg` (1rem) is the workhorse. High legibility is non-negotiable for educational content.
*   **Labels (Inter):** `label-md` (0.75rem) in `secondary` (#FFB874) should be used for technical metadata (e.g., sensor readings, port numbers).

The contrast between the wide, geometric Space Grotesk and the neutral Inter creates a "Scientific Journal" vibe.

---

## 4. Elevation & Depth: Tonal Layering
We convey hierarchy through **Tonal Layering** rather than traditional structural lines.

*   **The Layering Principle:** Depth is achieved by "stacking." A `surface-container-lowest` card placed on a `surface-container-low` section creates a natural, soft lift.
*   **Ambient Shadows:** For floating modals, use a custom shadow: `0px 24px 48px rgba(0, 0, 0, 0.4)`. The shadow color must never be pure black; it should be a deep tint of the background to mimic natural light absorption.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility (e.g., input fields), use the `outline-variant` token at **15% opacity**. 100% opaque borders are strictly forbidden.

---

## 5. Components

### Cards & Modules
*   **Style:** Forbid the use of divider lines. Use `spacing-8` (2rem) of vertical white space or a shift to `surface-container-lowest` to separate content.
*   **Radius:** Follow the Roundedness Scale. Most cards should use `xl` (1.5rem) for a friendly yet modern feel.

### Buttons
*   **Primary:** Gradient of `primary` to `primary-container`. `xl` roundedness. No border.
*   **Secondary:** Ghost style. `surface-container-highest` background with `on-surface` text.
*   **Interaction:** On hover, a subtle `primary` outer glow (4px blur, 20% opacity).

### Video Player Interface
*   **Chrome:** Semi-transparent `surface-container` (80% opacity) with a `12px` backdrop blur.
*   **Controls:** Use `secondary` (#FFB874) for the progress bar to provide high-contrast "Safety Orange" visibility against the dark slate.

### Robotics Icons (Traffic Signs/Sensors)
*   **Style:** Thick strokes (2px minimum). Use `secondary` for warnings/indicators and `primary` for active state logic.
*   **Glow:** Active icons should have a subtle "neon" bloom using a drop-shadow of the icon's own color at 30% opacity.

### Input Fields
*   **State:** Background `surface-container-low`. On focus, transition to `surface-container-high` with a `primary` "Ghost Border" at 20% opacity.

---

## 6. Do’s and Don’ts

### Do
*   **Do** use asymmetrical layouts (e.g., a large headline on the left with a floating card overlapping it on the right).
*   **Do** use the Spacing Scale (specifically `12` and `16`) to create generous "breathing room" between learning modules.
*   **Do** use `secondary_container` (#E38403) for "Caution" or "Technical Note" callouts to maintain the "Safety Orange" robotics theme.

### Don’t
*   **Don’t** use 1px solid lines to separate list items. Use a `spacing-2` gap and a subtle background hover state instead.
*   **Don’t** use pure white (#FFFFFF) for text. Always use `on-surface` (#E5E2E1) to reduce eye strain during long coding sessions.
*   **Don’t** use standard "drop shadows" on cards. Rely on the surface color hierarchy to define depth.