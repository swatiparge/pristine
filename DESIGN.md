# Design System Document

## 1. Overview & Creative North Star

### Creative North Star: "The Industrial Architect"
This design system moves away from the generic "utility company" template and embraces an editorial, architectural aesthetic. It reflects the precision of high-end electrical engineering through a sophisticated interplay of raw industrial power and refined digital elegance.

To break the "standard" look, the system utilizes **Intentional Asymmetry**. Rather than perfectly centered grids, we use weighted layouts where imagery (like the high-tension wire sunset) offsets bold, oversized typography. The interface is not a flat canvas but a series of **Layered Surfaces** that mimic the complexity of electrical schematics, using tonal shifts and "ghost" elements to guide the eye without relying on rigid, outdated borders.

---

## 2. Colors

The palette is rooted in the high-contrast relationship between deep industrial navies and the high-visibility "Volt Gold" of the logo.

### Palette Strategy
*   **Primary (#735C00 / #F6D264):** The "Volt Gold." Use the deeper `primary` for text-on-light or icons, and the vibrant `primary_container` for high-impact surfaces.
*   **Neutral Dark (#171D2F / #1A1C1C):** The foundation of the brand. This represents the "Black" of industrial hardware. Use `on_secondary_fixed` for footer backgrounds and deep headers.
*   **Surface Neutrals (#F9F9F9 to #E2E2E2):** A range of cool-grays and whites used to create architectural depth.

### The "No-Line" Rule
**Explicit Instruction:** Prohibit the use of 1px solid hex-code borders to define sections. Layout boundaries must be established exclusively through background color shifts. For example, a `surface_container_low` card must sit on a `surface` background to define its edges. Physical lines feel "cheap"; tonal transitions feel "custom."

### Surface Hierarchy & Nesting
Treat the UI as a physical stack.
*   **Level 0 (Base):** `surface` (#F9F9F9)
*   **Level 1 (Sections):** `surface_container_low` (#F3F3F3)
*   **Level 2 (Cards/Modules):** `surface_container_lowest` (#FFFFFF)

### Signature Textures
*   **The Power Gradient:** For primary CTAs or Hero overlays, utilize a subtle linear gradient from `primary` (#735C00) to `primary_container` (#F6D264) at a 135-degree angle.
*   **Glassmorphism:** For navigation bars or floating tooltips over imagery, use `surface` with 80% opacity and a `backdrop-blur` of 12px. This creates an "Industrial Frost" effect.

---

## 3. Typography

The typography strategy leverages the cleanliness of **Montserrat** and **Plus Jakarta Sans** to convey technical precision.

*   **Display (Plus Jakarta Sans):** Oversized, tight tracking, and bold. Used for "Hero" statements. It represents the "Pristine" nature of the solutions.
*   **Headline & Title (Plus Jakarta Sans / Inter):** Used for section headers. These should be authoritative and clear.
*   **Body (Inter):** High readability, generous line height (1.6+). Inter provides a modern, functional contrast to the more decorative display faces.
*   **Labels (Work Sans):** Monospaced-adjacent feel for technical data, specs, or "Sector" tags. This reinforces the industrial engineering vibe.

---

## 4. Elevation & Depth

We reject traditional drop shadows in favor of **Tonal Layering** and **Ambient Light**.

*   **The Layering Principle:** Depth is achieved by placing lighter surfaces on darker backgrounds. A White (#FFFFFF) card on a Light Gray (#F3F3F3) background provides all the "lift" required for a premium feel.
*   **Ambient Shadows:** If a floating state is required (e.g., a "Contact" FAB), use a shadow with a 32px blur, 0px offset, and 6% opacity of the `on_surface` color. It should feel like a soft glow, not a dark stain.
*   **The "Ghost Border":** If a separation is strictly needed for accessibility in input fields, use `outline_variant` at **15% opacity**. It should be barely perceptible—a "whisper" of a line.
*   **Industrial Transparency:** Use semi-transparent layers of `secondary_container` over images to allow the "Sunset Industrial" hero image to bleed through into the UI, ensuring the brand and the interface are inseparable.

---

## 5. Components

### Buttons
*   **Primary:** Volt Gold gradient background, `on_primary_fixed` text (Deep Navy). Hard 4px corners (`md` roundedness). No border.
*   **Secondary:** Ghost style. No background, `outline_variant` at 20% opacity. 
*   **Interaction:** On hover, primary buttons should shift +2px vertically with an ambient shadow to simulate a physical "switch" being flipped.

### Cards
*   **Constraint:** No borders. No dividers.
*   **Structure:** Use `surface_container_lowest` (#FFFFFF). Use the Spacing Scale (specifically `8` or `10`) for internal padding to give content massive "breathing room."
*   **Industrial Accents:** A single 4px vertical bar of `primary` gold on the left side of a card can be used to denote an "Active" or "Featured" service.

### Input Fields
*   **Style:** Filled style using `surface_container_high`. 
*   **Focus State:** The bottom edge gains a 2px `primary` gold underline. Avoid the "box" focus look; prefer the "underline" look to mimic technical drawing boards.

### Sector Chips
*   Small, all-caps labels using `label-sm`. Background `secondary_fixed_dim` with 30% opacity. These should look like metal tags or industrial labels.

---

## 6. Do's and Don'ts

### Do
*   **Do** use large amounts of white space (Spacing `16` and `20`) between major sections to let the industrial photography breathe.
*   **Do** use high-contrast type scales. A 3.5rem Display-lg next to a 0.875rem Body-md creates an editorial, high-end feel.
*   **Do** crop industrial photography at sharp, interesting angles to reinforce the "Engineering" theme.

### Don't
*   **Don't** use 1px solid black or gray borders. They clutter the technical aesthetic.
*   **Don't** use standard "Web Blue" for links. Use the Volt Gold (`primary`) or a deep Navy.
*   **Don't** use rounded corners above `0.5rem (lg)`. High-end industrial design is defined by structure and precision; overly bubbly corners look "consumer-grade" and soft.
*   **Don't** use generic iconography. Use thin-stroke, technical icons that look like blueprint symbols.