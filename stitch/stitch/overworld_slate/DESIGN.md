# Design System Specification: Architectural Earth

## 1. Overview & Creative North Star
The Creative North Star for this system is **"Organic Brutalism."** It is a synthesis of the block-based structural integrity found in digital construction environments and the sophisticated, muted palette of a high-end architectural firm. 

We are moving away from the "gamified" aesthetic of neon greens and floating icons. Instead, we embrace a grounded, editorial feel. The system utilizes heavy, blocky layouts and a rigid 0px radius scale to evoke strength, but softens this "brutalist" edge through a low-contrast, earthy color palette and generous whitespace. We break the monotony of the grid through intentional asymmetry—using "weighted" containers that feel like stacked stone or timber.

## 2. Colors & Surface Logic
The palette is rooted in the "Dark Mode" spectrum but avoids pure blacks. It favors deep, desaturated forest greens and mineral grays to reduce ocular fatigue.

### Color Roles
*   **Primary (`#abd0a7`):** A soft, lichen green used for high-priority actions and brand accents.
*   **Secondary (`#d9c2b2`):** A warm, parchment-wood tone used to balance the cool greens.
*   **Surface (`#121412`):** Our foundation—a deep, obsidian-green gray.
*   **Tertiary (`#c7c6c6`):** A stone-gray for utilitarian elements and supporting metadata.

### The "No-Line" Rule
While the style is "blocky," we prohibit 1px solid borders for standard sectioning. Boundaries must be defined by **Background Color Shifts**. For example:
*   A main content area on `surface` should be distinguished from a sidebar by shifting the sidebar to `surface-container-low`.
*   Avoid "hairline" dividers; use the change in tonal value to tell the user where one "block" ends and the next begins.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical slabs. 
1.  **Base Layer:** `surface-container-lowest` (#0d0f0d)
2.  **Standard Sectioning:** `surface` (#121412)
3.  **Raised Cards/Modules:** `surface-container` (#1e201e)
4.  **Interaction States:** `surface-bright` (#383a37)

### Signature Textures
To add "soul," use subtle linear gradients on primary CTAs. Transition from `primary` (#abd0a7) to `primary-container` (#2c4c2c) at a 135-degree angle. This mimics the way light hits a textured block without relying on dated bevels or glow effects.

## 3. Typography
The type system balances digital heritage with modern readability.

*   **Display & Headlines (Space Grotesk):** This clean, geometric sans-serif provides a "pro" architectural feel. Use `display-lg` (3.5rem) for hero statements with tight letter-spacing.
*   **Body & Titles (Work Sans):** Chosen for its exceptional legibility at small sizes. Use `body-md` (0.875rem) for the bulk of the experience.
*   **Micro-Branding (Press Start 2P):** Use *only* for the logo, level indicators, or specific "Easter egg" labels. It must never be used for more than three words in a row.
*   **Technical Data (VT323 / Monospace):** Use for code snippets, coordinates, or secondary metadata to maintain the digital-construction theme.

## 4. Elevation & Depth
In this system, "Elevation" is a measure of light absorption, not physical height.

*   **The Layering Principle:** Stack `surface-container-low` on top of `surface`. Because we have a **0px roundedness scale**, the blocks must align perfectly. The "depth" comes from the contrast between the deep greens and the stone grays.
*   **Ambient Shadows:** We avoid traditional drop shadows. If an element must "float" (like a modal), use a wide, diffused shadow: `box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4)`. The shadow color should be a darkened version of the surface color, not a neutral black.
*   **The "Ghost Border":** For essential accessibility on inputs, use the `outline-variant` (#434840) at 20% opacity. This creates a "suggestion" of a block edge without cluttering the brutalist aesthetic.

## 5. Components

### Buttons
*   **Primary:** Solid `primary` background with `on-primary` text. Square edges (0px).
*   **Secondary:** Solid `secondary_container` background.
*   **Tertiary:** Ghost style. No background, but a 2px `outline` border to emphasize the "block" shape.
*   **Interaction:** On hover, shift the background color one tier higher (e.g., from `primary` to `primary_fixed`).

### Cards & Layout Modules
Cards should never have borders. Separate them from the background using the `surface-container-high` token. Use `display-sm` for card titles to create an editorial, "poster-like" layout.

### Input Fields
*   **Structure:** Rectangular blocks with a `surface-container-highest` background.
*   **Focus State:** A 2px solid `primary` border. No glow.
*   **Labels:** Use `label-md` in `on-surface-variant` (muted gray) positioned strictly above the block.

### Navigation
Vertical navigation is preferred to reinforce the "structured" look. Use `surface-container-low` for the nav rail, creating a subtle vertical column that anchors the left side of the screen.

### Lists
Prohibit the use of horizontal divider lines. Use `8px` or `12px` of vertical whitespace (from the spacing scale) and a slight background change on hover to indicate individual list items.

## 6. Do’s and Don'ts

### Do:
*   **Do** embrace asymmetry. Place a large `display` heading on the left and a smaller `body` block on the right to create visual tension.
*   **Do** use 0px border-radius for everything. The system relies on "The Power of the Square."
*   **Do** use `secondary` (wood/tan) colors to highlight "warm" or "human" elements like user profiles or success messages.

### Don't:
*   **Don't** use any rounded corners (0px is the hard rule).
*   **Don't** use neon "Redstone" reds or "Diamond" cyans. Stick to the Earthy Palette.
*   **Don't** use 1px dividers. If the layout feels cluttered, increase the whitespace between blocks rather than adding a line.
*   **Don't** use `Press Start 2P` for any text longer than a short label; it destroys readability.