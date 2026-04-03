# Design System Strategy: Technical Precision & Editorial Brutalism

### 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Precision Grid."** 

In the high-stakes worlds of logistics and crisis management, clarity is a survival trait. This system moves away from the "soft" web of rounded buttons and friendly shadows, leaning instead into a high-end editorial aesthetic that mirrors the rigor of a technical manual or an architectural blueprint. 

We break the "template" look through **intentional asymmetry**—offsetting typography and using sharp, diagonal geometric crops on high-quality photography. The visual language is authoritative, minimalist, and uncompromisingly professional. By utilizing massive scale contrasts in typography and a strictly rectangular geometry (0px radius), we create a signature identity that feels engineered rather than merely "designed."

---

### 2. Colors
Our palette is rooted in high-contrast neutrality, punctuated by a high-visibility lime green that signals action and precision.

*   **Primary Logic:** The primary accent (`#CADB2A`) is reserved for critical paths: CTAs, active states, and "crisis" indicators. 
*   **The "No-Line" Rule:** Standard 1px solid borders are strictly prohibited for sectioning. Boundaries must be defined through background color shifts. For example, a `surface-container-low` section should sit adjacent to a `surface` background to create a structural break without visual clutter.
*   **Surface Hierarchy & Nesting:** Treat the UI as layers of fine paper. Use `surface-container-lowest` for floating cards on top of a `surface-container-low` background to create "natural" depth.
*   **The Glass & Gradient Rule:** For floating navigation or image overlays, utilize Glassmorphism (using semi-transparent `surface` colors with a `backdrop-blur` of 20px). Main CTAs should use a subtle vertical gradient from `primary` to `primary_container` to provide a "machined" metallic sheen, moving beyond flat, lifeless color blocks.

---

### 3. Typography
The system employs a dual-sans-serif approach to balance technical character with readability.

*   **Display & Headlines (Manrope):** Chosen for its geometric foundation. Use `display-lg` (3.5rem) with tight letter-spacing to create an impactful, editorial "header" feel. This conveys the authority of the conference.
*   **Body & Labels (Inter):** The industry standard for clarity. Inter provides the "utility" required for dense logistics data and schedule information.
*   **Visual Hierarchy:** Use `on_surface_variant` (grey) for sub-headers to ensure the black `on_surface` headlines remain the undisputed focal point.

---

### 4. Elevation & Depth
Depth is achieved through **Tonal Layering** rather than traditional drop shadows, maintaining the "sharp minimalist" requirement.

*   **The Layering Principle:** Place `surface_container_highest` elements within `surface` areas to create "sunken" or "raised" modules. This mimics physical architectural models.
*   **Ambient Shadows:** If a "floating" effect is required (e.g., for a critical crisis alert), use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(28, 27, 27, 0.06);`. The shadow must be tinted with the `on_surface` color to feel like natural ambient light.
*   **The "Ghost Border" Fallback:** If a boundary is required for accessibility, use a 1px border with the `outline_variant` token at **15% opacity**. Never use 100% opaque borders.
*   **Geometric Framing:** Use sharp, 45-degree diagonal cuts on containers and image masks (referencing the logo's angularity) to create a sense of forward motion and logistical "vectors."

---

### 5. Components

*   **Buttons:** 
    *   **Primary:** `primary_container` background, `on_primary_container` text. Absolute 0px radius. Padding: `spacing.4` (vertical) by `spacing.8` (horizontal).
    *   **Tertiary:** Text-only with a `primary` underline that expands on hover.
*   **Cards:** No borders or visible shadows. Use `surface_container_low` backgrounds. Integrate photography that bleeds to the edge, utilizing sharp geometric masks.
*   **Inputs:** Use `surface_variant` for the input field background with a "Ghost Border" at the bottom only. No fully enclosed boxes. This maintains an airy, editorial feel.
*   **Chips (Logistics Tags):** Rectangular blocks using `secondary_fixed_dim` with `on_secondary_fixed` text. Use these to categorize "Logistics," "Crisis," or "Strategy."
*   **Lists:** Forbid horizontal divider lines. Use `spacing.6` to `spacing.10` of vertical white space to separate list items. This forces the eye to rely on typography rather than lines.
*   **Crisis Indicators:** Small, sharp squares of `error` color (#ba1a1a) used sparingly to denote urgent schedule changes or critical alerts.

---

### 6. Do's and Don'ts

**Do:**
*   **Embrace White Space:** Use `spacing.24` (8.5rem) between major sections to let the high-quality photography breathe.
*   **Asymmetric Layouts:** Offset text columns. If an image is on the right, let the headline overlap it slightly using a `surface` background-color-block to create depth.
*   **Sharp Geometry:** Ensure all containers, buttons, and image crops have a 0px border radius.

**Don't:**
*   **Use Rounded Corners:** Any radius above 0px breaks the "Precision Grid" identity.
*   **Overuse the Lime Green:** The accent color should represent approximately 5-10% of the UI. Overuse diminishes its "alert" and "action" status.
*   **Standard Grids:** Avoid simple 3-column "card" rows. Vary the widths (e.g., a 2/3 width image next to a 1/3 width text block) to maintain an editorial, high-end feel.
*   **Use Generic Icons:** If icons are necessary, use ultra-thin (1pt) stroke icons with sharp corners. Never use "filled" or rounded icon sets.