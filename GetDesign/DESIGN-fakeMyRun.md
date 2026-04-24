# Design System Inspired by FakeMyRun

## 1. Visual Theme & Atmosphere

FakeMyRun is the visual equivalent of a runner's clean morning trail — open air, minimal distraction, and one clear path forward. The interface splits its personality between two distinct registers: the **landing pages** read like a carefully typeset outdoor magazine with editorial serif headings and generous breathing room, while the **/app** page snaps into a full-bleed cartographic workspace where a map dominates the viewport and floating panels offer surgical control over route parameters. This tonal duality isn't a contradiction — it's a deliberate separation of storytelling ("here's why this exists") from doing ("now draw your route").

The palette exercises remarkable restraint. A near-monochrome foundation of warm whites and soft greys serves as the canvas, with a single Burnt Orange (`#ea580c`) cutting through the neutrality like a trail marker on a forest path. This orange isn't decorative — it appears exclusively on primary CTAs, active navigation states, and critical UI touchpoints. When everything else is quiet, one color carries maximum weight. There's no gradient spectacle, no glassmorphism drama, no dark-mode-first aesthetic — just clean surfaces, precise typography, and a map that does the talking.

The Geist font family from Vercel anchors the typographic identity with a technical neutrality that feels native to the developer ecosystem. Combined with the frosted-glass navigation bar (`backdrop-blur`), generous section spacing, and flat-bordered cards, the design language communicates: *built by a developer who cares about craft, for runners who care about data.*

**Key Characteristics:**
- Near-monochrome palette with a single orange accent for all primary actions
- Two-register design: editorial landing pages vs utilitarian app workspace
- Geist Sans as the primary typeface — modern, technical, developer-native
- Full-bleed map integration dominating the app workspace
- Frosted-glass navigation bar with subtle blur effect
- Flat cards with borders (not shadows) for informational containers
- Warm amber highlight cards for key information callouts
- Generous whitespace and breathing room on marketing pages
- Vertical timeline pattern for "How It Works" flow

## 2. Color Palette & Roles

### Primary

- **Burnt Orange** (`#ea580c`): The singular accent — primary CTA backgrounds, active navigation states, interactive highlights, brand mark color. The entire visual identity revolves around this one color
- **Orange Hover** (`#c2410c`): Darkened orange for hover/pressed button states
- **Orange Light** (`#fed7aa`): Subtle orange tint for secondary hover backgrounds
- **Amber-600** (`#d97706`): Warm amber used for donation-related elements (☕ links)
- **Amber-500** (`#f59e0b`): Mobile-specific donate button fill

### Surface & Background

- **Pure White** (`#ffffff`): Primary page canvas — landing, how-it-works, app panels
- **Off-White** (`#fafafa`): Subtle surface differentiation for alternate sections, sidebar backgrounds
- **Warm Amber** (`#fef3c7`): Highlight card backgrounds, tip containers, info callouts — connects to the orange accent without competing
- **Light Amber** (`#fff7ed`): Softer amber for larger feature section backgrounds
- **Orange-50** (`#fff7ed`): Step icon backgrounds in how-it-works timeline

### Neutrals & Text

- **Near Black** (`#09090b`): Primary heading text — almost black with a faint warm undertone
- **Charcoal** (`#18181b`): Body text, strong labels
- **Dark Grey** (`#3f3f46`): Secondary text, descriptions, inactive navigation links
- **Medium Grey** (`#71717a`): Tertiary text, metadata, timestamps, muted labels
- **Light Grey** (`#a1a1aa`): Placeholder text, disabled states
- **Border Grey** (`#e4e4e7`): Standard card borders, dividers, input borders
- **Subtle Grey** (`#f4f4f5`): Input backgrounds, hover states, alternating surfaces
- **Navbar Border** (`#f3f4f6`): Very light grey for navigation bottom border

### Semantic

- **Destructive Red** (`#ef4444`): Clear/delete actions, error states, validation failures
- **Success Green** (`#22c55e`): Confirmation states, positive feedback
- **Route Blue** (`#3b82f6`): Map route overlay, location markers, geographic elements

### Special

- **Frosted Glass**: `rgba(255, 255, 255, 0.8)` with `backdrop-filter: blur(12px)` — navigation bar background creating depth without visual weight
- **Colored Shadow**: `shadow-amber-200` — warm glow shadow on active donate buttons
- **Scrollbar**: `#cbd5e1` thumb (4px width) with `#94a3b8` hover — minimal custom scrollbar for scrollable panels

## 3. Typography Rules

### Font Family

**Primary:** Geist Sans (Vercel's typeface)
- Variable font with full weight range
- Fallbacks: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif
- Anti-aliased rendering for crisp text on all screens

**Monospace:** Geist Mono
- Used for: data previews, technical labels, code snippets, numeric displays
- Fallbacks: ui-monospace, SFMono-Regular, Menlo, monospace

### Hierarchy

| Role | Size | Weight | Line Height | Letter Spacing | Notes |
|------|------|--------|-------------|----------------|-------|
| Display Hero | 60px | 800 (Extra Bold) | 1.1 | -0.02em | Landing page hero headline, maximum visual impact |
| Display Section | 36px | 800 (Extra Bold) | 1.1 | -0.02em | Section titles on landing pages |
| Heading 1 | 30px | 700 (Bold) | 1.2 | -0.01em | Page titles, major section headings |
| Heading 2 | 24px | 700 (Bold) | 1.3 | -0.01em | Subsection headings, card titles |
| Heading 3 | 18px | 700 (Bold) | 1.5 | — | Feature labels, step headings |
| Body Large | 18px | 400 (Regular) | 1.75 | — | Hero subtitles, lead paragraphs |
| Body | 16px | 400 (Regular) | 1.625 | — | Standard body text, descriptions |
| Body Medium | 14px | 500 (Medium) | 1.43 | — | Navigation links, form labels, button text |
| Caption | 14px | 400 (Regular) | 1.43 | — | Metadata, helper text |
| Small | 12px | 500 (Medium) | 1.33 | — | Tags, badges, fine print |
| Tiny | 11px | 400 (Regular) | 1.27 | — | Map annotations, slider tick values |

### Principles

Geist brings a technical neutrality that signals "built by someone who knows what they're doing." Extra Bold 800 on display headings creates typographic gravity that anchors the editorial landing pages, while Regular 400 on body text keeps reading effortless. The system avoids italics entirely — weight contrast (400 vs 700 vs 800) is the primary differentiation tool. Tight negative letter-spacing (-0.02em) on headings creates a confident, magazine-like density. Tabular numerals are used for pace/distance/time displays where vertical alignment matters.

## 4. Component Stylings

### Buttons

**Primary (Orange Fill)**
- Background: Burnt Orange (`#ea580c`)
- Text: White (`#ffffff`), 14px, weight 500
- Border: none
- Border radius: 8px
- Padding: 8px 16px (standard), 10px 20px (large)
- Shadow: subtle `0 1px 3px rgba(0,0,0,0.1)`
- Hover: background darkens to `#c2410c`, shadow intensifies
- Active: subtle scale(0.98) transform
- Transition: all 150ms ease
- Cursor: pointer

**Secondary (Ghost)**
- Background: transparent
- Text: Dark Grey (`#3f3f46`), 14px, weight 500
- Border: 1px solid transparent
- Border radius: 8px
- Padding: 8px 16px
- Hover: background fills with Subtle Grey (`#f4f4f5`), border appears (`#e4e4e7`)
- Transition: all 150ms ease

**Destructive (Red)**
- Background: Destructive Red (`#ef4444`)
- Text: White (`#ffffff`)
- Border: none
- Border radius: 8px
- Hover: darkens to `#dc2626`
- Used for: "Clear route", "Delete" actions

**Donate (Amber)**
- Background: Amber-500 (`#f59e0b`)
- Text: White (`#ffffff`)
- Border: none
- Border radius: 8px
- Shadow: `shadow-amber-200` (warm glow effect)
- Hover: scale(1.02) with intensified shadow
- Used for: donation CTAs only

**Icon Button**
- Background: transparent
- Size: 36px × 36px (square)
- Border radius: 8px
- Icon: 16-20px, Medium Grey (`#71717a`)
- Hover: background `#f4f4f5`, icon darkens to `#3f3f46`

### Cards & Containers

**Standard Card**
- Background: White (`#ffffff`)
- Border: 1px solid Border Grey (`#e4e4e7`)
- Border radius: 16px (large rounded)
- Padding: 24px
- Shadow: none — flat design, borders do the work
- Hover: no change (informational cards are not interactive)

**Highlight Card (Amber)**
- Background: Warm Amber (`#fef3c7`)
- Border: 1px solid `#fde68a`
- Border radius: 16px
- Padding: 24px
- Used for: key information callouts, tips, featured content

**Feature Card**
- Background: White (`#ffffff`)
- Border: 1px solid Border Grey (`#e4e4e7`)
- Border radius: 16px
- Padding: 24px
- Icon container: 40px circle, `#fff7ed` background, orange icon
- Hover: subtle shadow appears

**App Control Panel**
- Background: White (`#ffffff`)
- Border: 1px solid Border Grey (`#e4e4e7`)
- Border radius: 16px
- Padding: 16px
- Shadow: `0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -1px rgba(0,0,0,0.06)`
- Position: floating over map, absolutely positioned
- Max-height: viewport minus nav, scrollable with custom scrollbar

### Inputs & Forms

**Text Input**
- Background: White (`#ffffff`)
- Text: Charcoal (`#18181b`), 14px
- Border: 1px solid Border Grey (`#e4e4e7`)
- Border radius: 8px
- Padding: 8px 12px
- Focus: border shifts to Burnt Orange (`#ea580c`), ring glow `0 0 0 2px rgba(234,88,12,0.2)`
- Placeholder: Light Grey (`#a1a1aa`)
- Transition: border-color 150ms, box-shadow 150ms

**Search Input**
- Same as Text Input but with:
- Left icon: Search (18px, Medium Grey), padding-left 40px
- Full width within panel
- Border radius: 10px

**Slider/Range**
- Track: Border Grey (`#e4e4e7`), 4px height, rounded
- Filled track: Burnt Orange (`#ea580c`)
- Thumb: White circle (18px), 2px orange border, subtle shadow
- Used for: pace, distance, elevation parameters

**Checkbox**
- Size: 16px × 16px
- Border: 2px solid Border Grey
- Border radius: 4px
- Checked: Burnt Orange (`#ea580c`) fill, white checkmark
- Label spacing: 8px gap

**Activity Type Selector**
- Row of icon-labeled options
- Inactive: bordered card style, grey icon
- Active: orange border, orange icon, subtle amber background
- Border radius: 8px per option

### Navigation

**Sticky Header**
- Background: White at 80% opacity with 12px blur effect (frosted glass)
- Border bottom: 1px solid very light grey (`#f3f4f6`)
- Shadow: subtle small shadow for minimal elevation
- Position: sticky, top 0, z-index 50
- Height: 64px
- Max content width: 1400px, centered

**Logo**
- Runner emoji (🏃) + text "FakeMyRun"
- "My" portion highlighted in Burnt Orange (`#ea580c`)
- Font: Bold, 20px, Near Black (`#09090b`)
- Hover: opacity reduces to 80%

**Nav Links**
- Color: Dark Grey (`#3f3f46`), 14px, weight 500
- Active state: Burnt Orange background, white text, subtle shadow
- Hover (inactive): grey background fill, text darkens
- Border radius: 8px per link
- Gap: 4px between links

**Donate Link (Nav)**
- Color: Amber-600, 14px, weight 500
- Coffee emoji prefix (☕)
- Hover: light amber background fill

**Mobile Navigation**
- Only shows "App" button (orange) and coffee emoji button (amber)
- Full nav links hidden, minimal mobile footprint

### Footer

- Background: White (`#ffffff`) or Off-White (`#fafafa`)
- Border top: 1px solid Border Grey (`#e4e4e7`)
- Padding: 48px vertical, 24px horizontal
- Text: Medium Grey (`#71717a`), 14px
- Links: Dark Grey, hover shifts to orange
- Layout: centered, single column

## 5. Spacing & Layout

### Grid System

- **Max content width:** 1400px (nav container), 1200px (content sections)
- **Horizontal padding:** 16px mobile, 32px tablet, 32px desktop
- **Layout approach:** Content-width driven with generous auto-margins, not strict column grid
- **App layout:** Full viewport width — map takes 100% with floating panels overlaid

### Section Spacing

| Context | Value | Notes |
|---------|-------|-------|
| Section-to-section | 96px | Between major landing page blocks |
| Section inner padding | 64px top/bottom | Within sections |
| Heading to content | 24px | After section headings |
| Paragraph to paragraph | 16px | Between body paragraphs |
| Card to card | 24px | In grid or stack layouts |
| Input to input | 16px | Between form fields |
| Button group gap | 12px | Between side-by-side buttons |
| Nav item gap | 4px | Between navigation links |

### Component Internal Spacing

| Component | Padding | Notes |
|-----------|---------|-------|
| Standard Card | 24px all sides | Uniform padding |
| App Control Panel | 16px | Tighter for utility context |
| Primary Button | 8px 16px | Standard |
| Large Button | 10px 20px | Hero/section CTAs |
| Text Input | 8px 12px | Compact |
| Nav Bar (inner) | 0 16px (mobile), 0 32px (desktop) | Height: 64px |
| Timeline Step | 24px left of connecting line | Step content offset |

### Breakpoints

| Name | Width | Key Behavior |
|------|-------|-------------|
| Mobile | < 640px | Single column, collapsed nav (only App + ☕), full-width cards |
| Tablet | 640px–1024px | 2-column feature grids, expanded nav |
| Desktop | > 1024px | Full layout, floating panels on map, all nav links visible |

## 6. Motion & Transitions

### Transition Defaults

- **Micro-interactions:** 150ms ease (hover, focus, active)
- **Layout changes:** 300ms ease (panel open/close, section reveal)
- **Properties:** `all` for buttons, `color` for text links, `border-color + box-shadow` for inputs

### Hover Effects

| Element | Effect | Duration |
|---------|--------|----------|
| Primary Button | Background darkens + shadow intensifies | 150ms |
| Secondary Button | Background fills with subtle grey | 150ms |
| Donate Button | Scale up (1.02) + warm shadow glow | 150ms |
| Nav Links | Background fill appears, text darkens | 150ms |
| Icon Buttons | Background appears + icon color darkens | 150ms |
| Footer Links | Color shifts to orange | 150ms |
| Standard Cards | No hover effect (intentionally static) | — |

### Active/Press Effects

- Buttons: `transform: scale(0.98)` — subtle shrink on press
- Duration: 100ms, easing: ease-out

### Page-Level Motion

- No staggered entrance animations — content is immediately present
- Smooth scroll for anchor links (e.g., `#buy-me-coffee`)
- Map tiles load progressively
- Sticky nav remains visible with frosted-glass effect on scroll
- No parallax, no scroll-triggered animations — the design trusts its content

## 7. Patterns & Best Practices

### Map-First App Pattern

The `/app` page follows a "map as canvas" pattern where the interactive map takes 100% of the viewport, and UI controls float above it as positioned panels:
- Map: full viewport, positioned behind everything
- Control panels: floating, top-left or right, scrollable
- Search: top of panel with integrated icon
- Settings: collapsible sections within panel
- Actions (download, clear): fixed at panel bottom
- This pattern is shared by Mapbox Studio, Google Maps, and Figma — the workspace IS the content

### Editorial Landing Pattern

The landing page uses a magazine-style layout:
- Hero: oversized heading (60px) + descriptive subtitle + single primary CTA
- Features: icon-labeled cards in 2-3 column grid with amber background section
- Social proof / donation: warm-toned section with QR and supporter list
- Footer: minimal, centered, single column

### Vertical Timeline (How It Works)

Steps are displayed in a vertical timeline with numbered indicators:
- Each step: orange circle number badge + heading + description paragraph
- Connecting line: 2px solid Border Grey between steps
- Steps may contain screenshots, tip boxes, or inline demos
- Pill-shaped badges describe sub-processes
- Typically 3–5 steps

### Single Accent Color Strategy

The entire visual identity uses **one accent color** (Burnt Orange). This means:
- Every colored element carries maximum visual weight
- Users always know where to look for the next action
- No cognitive load from competing color signals
- Orange = "do this now," grey = "information," amber = "take note"

### Frosted Glass Navigation

The navigation uses semi-transparent white + backdrop blur:
- Maintains content visibility while scrolling
- Separates nav from content without a hard visual break
- Feels modern without being trendy
- The blur effect is the only "special effect" in the entire design

## 8. Do's and Don'ts

### Do's ✅

- **Do** use Burnt Orange exclusively for primary actions — never for decoration
- **Do** maintain generous section spacing (96px between sections) on landing pages
- **Do** use Geist Sans everywhere — it is the visual identity's DNA
- **Do** use flat bordered cards (not shadow-elevated) for informational containers
- **Do** keep the map full-bleed in the app — never constrain it in a bordered card
- **Do** use warm amber tones for highlight/tip containers — they connect to the orange
- **Do** use the frosted-glass nav pattern with `backdrop-blur`
- **Do** use 150ms for micro-interactions — fast enough to feel responsive, slow enough to notice
- **Do** use large border-radius (16px) on cards and containers — this is a signature shape
- **Do** keep mobile nav minimal — show only the most critical action buttons

### Don'ts ❌

- **Don't** introduce a second accent color — the single-orange system is the identity
- **Don't** add shadows to landing page cards — use borders instead (shadows are reserved for floating panels)
- **Don't** add staggered entrance animations — content should appear immediately
- **Don't** use gradients on buttons or backgrounds — the palette is flat and intentional
- **Don't** use Geist Mono for body text — it's reserved for data/code contexts
- **Don't** add decorative illustrations — the map IS the visual element
- **Don't** use small border radius (4px) on cards — the design vocabulary is 8px-16px
- **Don't** make informational cards hoverable — they're not interactive
- **Don't** constrain the app map inside a container — it needs full viewport
- **Don't** use pill-shaped buttons — the 8px rounded rectangle is the established shape

## 9. Technology Stack

| Layer | Technology | Notes |
|-------|-----------|-------|
| Framework | Next.js (App Router) | React Server Components for landing, Client Components for app |
| Styling | Tailwind CSS v4 | OKLCH color tokens in CSS variables |
| UI Library | shadcn/ui | Prebuilt component primitives |
| Animations | tw-animate-css | Micro-animation utilities |
| Typography | Geist Sans + Geist Mono | Variable fonts via `next/font` |
| Maps | Mapbox GL JS | Full-bleed interactive mapping |
| Icons | Lucide React | Consistent line-icon style |
| State | Zustand | Client-side state management |
| Deployment | Vercel | Edge-optimized hosting |

## 10. CSS Variables Reference

```css
:root {
  /* Brand */
  --color-primary: #ea580c;
  --color-primary-hover: #c2410c;
  --color-primary-light: #fed7aa;

  /* Surface */
  --color-background: #ffffff;
  --color-surface: #fafafa;
  --color-highlight: #fef3c7;
  --color-highlight-border: #fde68a;

  /* Text */
  --color-text-primary: #09090b;
  --color-text-secondary: #3f3f46;
  --color-text-tertiary: #71717a;
  --color-text-muted: #a1a1aa;

  /* Borders */
  --color-border: #e4e4e7;
  --color-border-focus: #ea580c;

  /* Semantic */
  --color-destructive: #ef4444;
  --color-success: #22c55e;
  --color-info: #3b82f6;

  /* Radius */
  --radius-sm: 6px;
  --radius-md: 8px;
  --radius-lg: 10px;
  --radius-xl: 16px;

  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
  --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
  --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1);

  /* Typography */
  --font-sans: 'Geist Sans', system-ui, sans-serif;
  --font-mono: 'Geist Mono', ui-monospace, monospace;

  /* Motion */
  --transition-fast: 150ms ease;
  --transition-normal: 300ms ease;

  /* Layout */
  --max-width: 1200px;
  --max-width-wide: 1400px;
  --nav-height: 64px;
  --section-gap: 96px;
}
```
