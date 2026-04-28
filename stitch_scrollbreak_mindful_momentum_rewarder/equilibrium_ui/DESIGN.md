# Design System Specification: The Focused Flow

## 1. Overview & Creative North Star
**Creative North Star: "The Digital Sanctuary"**

This design system is engineered to counteract the high-dopamine, high-noise environment of social media. We are not building just another utility; we are building a sanctuary. The aesthetic rejects the "flat and frantic" nature of modern apps in favor of **Depth-First Design**. 

To move beyond the template look, we utilize **Intentional Asymmetry** and **Tonal Immersion**. By prioritizing Dark Mode as the primary experience, we signal to the user’s brain that it is time to decompress and focus. We break the rigid grid by allowing hero elements to overlap containers, creating an editorial feel that suggests the app is "breathing" rather than just rendering data.

---

## 2. Colors: Tonal Depth & The "No-Line" Rule
The palette centers on deep, obsidian-teals that ground the user, punctuated by "Bioluminescent Accents" (Amber and Coral) that symbolize growth and reward.

### The "No-Line" Rule
**Borders are a cognitive tax.** In this system, 1px solid borders for sectioning are strictly prohibited. We define boundaries through:
1.  **Background Shifts:** Use `surface-container-low` for the base and `surface-container-high` for interactive elements.
2.  **Tonal Transitions:** Defining space through subtle value changes rather than structural lines.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. We use a "Nesting" logic:
*   **Base Level:** `surface` (#0c1514) – The infinite void.
*   **Section Level:** `surface-container-low` (#141d1c) – To define large content areas.
*   **Interactive Level:** `surface-container-highest` (#2d3735) – For cards and actionable items.

### The Glass & Gradient Rule
To achieve a "premium" feel, use **Glassmorphism** for floating headers or navigation bars. Use `surface_bright` at 60% opacity with a `20px` backdrop-blur. 
*   **Signature Textures:** Apply a subtle linear gradient (Top-Left to Bottom-Right) using `primary` (#98d1c8) to `primary_container` (#002c27) for high-impact CTAs. This creates a tactile, jewel-like quality.

---

## 3. Typography: The Editorial Voice
We utilize **Manrope** for its balance of geometric precision and organic warmth.

*   **Display (lg/md/sm):** Reserved for "Flow States" or milestone achievements. Use tight letter-spacing (-0.02em) to give it an authoritative, editorial punch.
*   **Headline & Title:** The "Director’s Voice." These guide the user through the sanctuary. Use `headline-md` for screen titles to establish a clear hierarchy.
*   **Body (lg/md/sm):** The "Companion Voice." Used for instructions and content. High line-height (1.5x) is mandatory to ensure the "Calm Focus" aesthetic is maintained.
*   **Labels:** Specifically for gamified metrics (e.g., "Focus Time: 45m"). These should be set in `label-md` using `primary` or `secondary` colors to distinguish data from narrative.

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows are often "muddy." We use **Ambient Light Simulation** to create lift.

*   **The Layering Principle:** Instead of a shadow, place a `surface-container-lowest` card on top of a `surface-container` background to create a "sunken" or "carved" effect.
*   **Ambient Shadows:** For floating action buttons or rewards, use a diffused shadow: `box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4)`. The shadow must never be pure grey; it should feel like it is absorbing the deep teal of the background.
*   **The "Ghost Border" Fallback:** If a container lacks contrast (e.g., on certain image backgrounds), use the `outline-variant` (#414846) at **15% opacity**. It should be felt, not seen.
*   **Glassmorphism:** Use `surface_variant` with 40% opacity and a heavy blur for overlays. This keeps the user connected to the "Focus" context behind the modal.

---

## 5. Components: Tactile Modernism

### Buttons (The "Pulse" of Action)
*   **Primary:** Rounded `full`. Gradient fill (`primary` to `primary_fixed_dim`). No border. High-contrast `on_primary` text.
*   **Secondary:** Rounded `xl`. `surface-container-highest` fill. Use for "Add Task" or "Breather" actions.
*   **Tertiary:** Text only in `primary`. No container. Used for "Cancel" or "Skip."

### Cards & Lists (The "Anti-Grid")
*   **Rule:** **Zero Dividers.** Separate list items using `12px` of vertical whitespace.
*   **Interaction:** On tap, a card should subtly scale down (0.98x) and transition to `surface_bright`, mimicking a physical press into a soft material.

### Chips (Gamified Tags)
*   **Selection Chips:** Use `secondary_container` with `on_secondary_container` text. These should feel like "earned tokens" rather than just filters.

### Input Fields
*   **Focus State:** Instead of a bold border, the background should shift from `surface-container-low` to `surface-container-highest`, and the `label` should transition to the `primary` teal color.

### Progress Visuals (Gamification)
*   Use `secondary` (Amber) for active progress and `tertiary` (Coral) for "Streak Breaks" or "Urgency." Progress bars should have a `rounded-full` cap and a subtle inner-glow.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use asymmetrical margins (e.g., a wider left margin for headlines) to create an editorial, premium feel.
*   **Do** use `rounded-xl` (1.5rem) for main containers to emphasize softness and safety.
*   **Do** lean into the Dark Mode. Light Mode should feel like a "Paper" version—matte and soft, never stark white.

### Don’t:
*   **Don’t** use pure black (#000000). Always use the `background` (#0c1514) to maintain the "Deep Forest" depth.
*   **Don’t** use standard 1px dividers. If you feel the need for a line, increase your whitespace instead.
*   **Don’t** use high-velocity animations. All transitions should be "snappy yet eased" (e.g., `cubic-bezier(0.4, 0, 0.2, 1)`) to reflect a calm environment.
*   **Don’t** crowd the screen. If a user has to think about where to click, the "Calm Focus" has failed.