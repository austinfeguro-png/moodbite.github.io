```markdown
# Design System Specification

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Tactile Serenity."** 

We are moving away from the rigid, clinical structures of traditional SaaS and toward a high-end editorial experience that feels like a digital sanctuary. This system prioritizes psychological comfort through intentional asymmetry, breathing room, and organic shapes. By breaking the "template" look with overlapping elements and a shift from structural lines to tonal depth, we create an environment that feels curated, premium, and inherently wellness-focused.

## 2. Color & Atmospheric Depth
This palette is grounded in nature, using Earth-tones to lower the user's cognitive load.

### The Foundation
- **Primary Olive/Moss (`#535845`):** Used for primary actions and grounding elements.
- **Secondary Sage (`#596244`):** Used for supportive accents and navigational hierarchy.
- **Background Warm Cream (`#fafaf5`):** The "canvas." Never pure white.
- **Accent Soft Orange (`#8d3f00` / `tertiary` tokens):** Reserved exclusively for mood-based iconography to ensure emotional resonance.

### The "No-Line" Rule
To maintain a premium, organic feel, **explicitly prohibit the use of 1px solid borders** for sectioning. Boundaries must be defined solely through background color shifts. Use `surface-container-low` for large sections sitting on a `surface` background to create soft, imperceptible transitions.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of fine, heavy-weight paper.
- **Base Layer:** `surface`
- **Sectioning Layer:** `surface-container-low`
- **Component Layer:** `surface-container-lowest` (this creates a "lifted" card effect without needing a shadow).

### The "Glass & Gradient" Rule
Standard flat colors can feel sterile. Use subtle gradients (e.g., `primary` to `primary_container`) for hero buttons or backgrounds to provide visual "soul." For floating overlays, apply a **Glassmorphism effect**: Use semi-transparent surface colors with a `20px` to `40px` backdrop-blur to allow the organic background textures to bleed through.

## 3. Typography
We utilize **Plus Jakarta Sans** for its modern, friendly, and slightly rounded character, which mirrors the pill-shaped elements of the UI.

| Level | Size | Weight | Role |
| :--- | :--- | :--- | :--- |
| **Display-LG** | 3.5rem | 600 | Editorial moments and hero headers. |
| **Headline-MD** | 1.75rem | 500 | Section titles; high-contrast against body. |
| **Title-SM** | 1rem | 600 | Component-level headers and card titles. |
| **Body-LG** | 1rem | 400 | Primary reading text; high line-height for air. |
| **Label-MD** | 0.75rem | 500 | Metadata and small utilitarian text. |

**Editorial Contrast:** Pair large `Display-LG` titles with significant whitespace and `body-md` text to create a high-fashion, premium layout.

## 4. Elevation & Depth
Hierarchy is achieved through **Tonal Layering** rather than structural lines.

### The Layering Principle
Depth is created by stacking tiers. For example, a `surface-container-lowest` card placed on a `surface-container-low` section creates a natural, soft lift.

### Ambient Shadows
Shadows must be "ambient," mimicking natural light.
- **Value:** `0px 12px 32px`
- **Color:** Use a 6% opacity version of `on-surface` (never pure black).
- **Feel:** Shadows should be felt, not seen. They are for "floating" elements only (e.g., FABs or active cards).

### The "Ghost Border" Fallback
If a border is required for accessibility (e.g., input fields), use a **Ghost Border**: the `outline-variant` token at **20% opacity**. Never use 100% opaque borders.

## 5. Components

### Buttons
- **Shape:** Fully pill-shaped (`rounded-full` / `9999px`).
- **Primary:** `primary` fill with `on-primary` text. Add a subtle vertical gradient for depth.
- **Secondary:** `secondary-container` fill.
- **Tertiary:** No fill, `primary` text.

### Chips (Mood & Filter)
- **Selection Chips:** Use `secondary-fixed-dim` for the unselected state. When selected, transition to `primary` with a soft ambient shadow.
- **Shape:** Softly rounded (`1rem` / `DEFAULT`).

### Input Fields
- **Styling:** Use `surface-container-highest` as the background fill. No bottom line. Use the "Ghost Border" (20% `outline-variant`) only on focus.
- **Labels:** Position inside the container for a compact, integrated look.

### Cards & Lists
- **The Divider Ban:** Strictly forbid 1px dividers between list items. Use **vertical white space** (16px–24px) or a `surface-variant` background on alternate items to separate content.
- **Floating Cards:** Use `rounded-lg` (2rem) for all card containers to reinforce the organic, soft vibe.

### Additional Signature Components
- **Mood Sliders:** Thick, organic tracks with a large, pill-shaped handle. 
- **The Sensory Header:** A top navigation bar that uses Glassmorphism (blur) rather than a solid fill to keep the interface feeling light and airy.

## 6. Do's and Don'ts

### Do
- **Do** use intentional asymmetry. Place images off-center or allow them to bleed off the edge of the screen.
- **Do** use large amounts of "negative space" to prevent the user from feeling overwhelmed.
- **Do** use organic, hand-drawn-style illustrations to complement the olive and sage tones.
- **Do** ensure all interaction states (hover, active) use tonal shifts (e.g., moving from `surface-container-low` to `surface-container-high`).

### Don't
- **Don't** use 1px solid dividers or borders. It breaks the "sanctuary" feel.
- **Don't** use pure black (`#000000`) for text. Use `on-surface` (`#1a1c19`) for a softer, more natural contrast.
- **Don't** use the accent orange for anything other than mood-specific icons. It is a high-energy color and must be used sparingly to maintain the "Calm" vibe.
- **Don't** use sharp corners. Every element should feel safe and soft to the touch.

---
**Note to Designers:** Your goal is not to fill every pixel, but to curate the space between elements. Think like a gallery curator, not a data architect.```