---
name: ouds-design-tokens
description: Comprehensive knowledge of OUDS (Orange Unified Design System) design tokens. Use when working with color tokens, spacing, typography, elevation, borders, or any UI styling questions for Orange brand. Includes all token values for Orange, SOSH, and Wireframe themes with light/dark mode support.
---

# OUDS Design Tokens Skill

## Overview

This skill provides comprehensive knowledge of the OUDS (Orange Unified Design System) design token architecture. Use this when working with design tokens, theming, or generating component documentation.

---

## Bundled Token Files

**This skill package includes all token source files:**
```
tokens/jsonl-ai/
├── orange/               # Orange theme (65 files)
├── sosh/                 # SOSH theme (65 files)
└── wireframe/            # Wireframe theme (65 files)
```

**Token file naming pattern:**
```
tokens/jsonl-ai/[theme]/ai_[theme]_[category].json
```

**Common token files:**
| Token Type | Filename |
|------------|----------|
| Background colors (light) | `ai_orange_color_bg_light.json` |
| Surface colors (light) | `ai_orange_color_surface_light.json` |
| Border colors (light) | `ai_orange_color_border_light.json` |
| Action colors (light) | `ai_orange_color_action_light.json` |
| Content colors (light) | `ai_orange_color_content_light.json` |
| Elevation | `ai_orange_elevation.json` |
| Border radius | `ai_orange_border_radius.json` |
| Font size | `ai_orange_font_size.json` |
| Space inset | `ai_orange_space_inset.json` |
| Grid (web) | `ai_orange_grid_web.json` |

---

## File Structure

```
ouds-design-tokens.skill (this package)
├── SKILL.md              # This documentation
└── tokens/jsonl-ai/
    ├── orange/           # Orange theme (65 files)
    ├── sosh/             # SOSH theme (65 files)
    └── wireframe/        # Wireframe theme (65 files)
```

**Statistics:**
- 195 JSON token files (65 per theme)
- 3 themes: Orange, SOSH, Wireframe
- 65 unique token types per theme

---

## Token Categories

### Color Tokens (20 types)
| Token File | Description | Variants |
|------------|-------------|----------|
| `color_action_light/dark` | Interactive elements | enabled, hover, pressed, loading, read-only, disabled, focus, selected, visited, highlighted, support, negative |
| `color_always` | Fixed colors | black, white, on-black, on-white |
| `color_bg_light/dark` | Backgrounds | primary, secondary, tertiary, inverse-low, inverse-high |
| `color_surface_light/dark` | Surface colors | Various surface states |
| `color_content_light/dark` | Text/content | Various content states |
| `color_border_light/dark` | Borders | Various border states |
| `color_opacity_light/dark` | Transparent colors | Opacity-based variations |
| `color_overlay_light/dark` | Overlays | Modal/overlay states |

### Typography Tokens (5 types)
| Token File | Description | Values |
|------------|-------------|--------|
| `font_family` | Font faces | Helvetica Neue, Menlo, SF Mono, Courier New |
| `font_size` | Sizes | 150px to 1850px scale (display, heading, body, label, code) |
| `font_weight` | Weights | Regular/400, Medium/500, Bold/700 |
| `font_line-height` | Line heights | Corresponding to font sizes |
| `font_letter-spacing` | Tracking | Corresponding to font sizes |

### Spacing Tokens (7 types)
| Token File | Description | Scale |
|------------|-------------|-------|
| `space_inset` | Padding insets | none, 2xsmall, xsmall, small, medium, large, xlarge, 2xlarge, 3xlarge |
| `space_fixed` | Fixed spacing | 0px, 1px, 2px, 4px, 6px, 8px, 12px, 16px, 24px, 32px, 40px |
| `space_scaled` | Responsive spacing | Adapts to breakpoint |
| `space_scaled_mobile/tablet/desktop` | Breakpoint-specific | Platform variations |
| `space_padding-block` | Vertical padding | Block-level spacing |
| `space_padding-inline` | Horizontal padding | Inline-level spacing |
| `space_column-gap` / `space_row-gap` | Grid gaps | Gap spacing |

### Size Tokens (9 types)
| Token File | Description |
|------------|-------------|
| `size` | General sizing (min-interactive-area: 48px) |
| `size_icon_decorative` | Decorative icon sizes |
| `size_icon_with-body_*` | Icons paired with body text (by breakpoint) |
| `size_icon_with-heading_*` | Icons paired with headings (by breakpoint) |
| `size_icon_with-label` | Icons paired with labels |
| `size_max-width_*` | Maximum container widths (by breakpoint) |

### Grid Tokens (6 types)
| Token File | Description | Breakpoints |
|------------|-------------|-------------|
| `grid_web/ios/android` | Platform grids | Platform-specific |
| `grid_*` | Responsive grids | 2xs (360px), xs, sm, md, lg, xl, 2xl, 3xl (1920px) |

Grid properties: width, min-width, max-width, margin, column-gap, column-count

### Border & Effect Tokens (4 types)
| Token File | Description | Values |
|------------|-------------|--------|
| `border_radius` | Corner radius | 0px, 4px, 8px, 12px, 2000px (pill) |
| `border_width` | Border thickness | Various widths |
| `border_style` | Border styles | solid, dashed, etc. |
| `elevation` | Shadows | none, raised, default, emphasized, drag, sticky |

### Other Tokens
| Token File | Description | Values |
|------------|-------------|--------|
| `opacity` | Opacity levels | invisible (0) to opaque (100) |

---

## Three-Tier Token Hierarchy

### Tier 1: Semantic Tokens (Design-Friendly)
```
ouds.[category].[subcategory].[variant]
```
Examples:
- `ouds.color.action.enabled`
- `ouds.font.size.display.large.mobile`
- `ouds.space.inset.medium`
- `ouds.border.radius.large`

### Tier 2: Core Tokens (Functional)
```
core-ouds.[category].[subcategory].[value]
core-orange.[category].[subcategory].[value]
```
Examples:
- `core-ouds.color.functional.black`
- `core-ouds.font.size.850`
- `core-orange.color.orange.550`

### Tier 3: Raw Values
```
#000000, 40px, Bold, Helvetica Neue
```

### Reference Chain
```
Semantic Token (ouds.color.action.enabled)
    ↓
Core Token (core-ouds.color.functional.black)
    ↓
Raw Value (#000000)
```

---

## JSON Token Format

### Simple Token Structure
```json
{
  "tokens": [
    {
      "ouds.color.action.enabled": {
        "type": "color",
        "value": {
          "semantic token": "ouds.color.action.enabled",
          "core token": "core-ouds.color.functional.black",
          "raw value": {
            "value": {
              "value": "#000000"
            }
          }
        },
        "description": ""
      }
    }
  ],
  "versions": {
    "sys.orange": "2.2.0",
    "core.ouds": "1.9.0",
    "core.orange": "1.2.0"
  }
}
```

### Composite Token Structure (Typography)
```json
{
  "composite tokens": [
    {
      "type.display.large.desktop": {
        "type": "typography",
        "value": {
          "family": "Helvetica Neue",
          "weight": "Bold",
          "size": "72px",
          "line-height": "80px",
          "letter-spacing": "-1.08px"
        }
      }
    }
  ]
}
```

### Token Types
- `"color"` - Color values (hex, rgba)
- `"dimension"` - Sizes, spacing (px values)
- `"string"` - Font names, styles
- `"typography"` - Composite typography tokens

---

## Platform & Responsive Variants

### Platforms
- **web** - Web applications
- **ios** - iOS native apps
- **android** - Android native apps
- **tv** - TV applications

### Breakpoints
| Name | Width |
|------|-------|
| 2xs | 360px |
| xs | 390px |
| sm | 480px |
| md | 768px |
| lg | 1024px |
| xl | 1440px |
| 2xl | 1680px |
| 3xl | 1920px |

### Responsive Typography Example
```
ouds.font.size.display.large.mobile  → 40px
ouds.font.size.display.large.tablet  → 64px
ouds.font.size.display.large.desktop → 72px
```

---

## Themes

### Orange (Primary)
- Primary branded theme
- Full color palette with Orange brand colors
- Files: `tokens/jsonl-ai/orange/`

### SOSH (Secondary)
- Secondary theme variant
- Alternative color palette
- Files: `tokens/jsonl-ai/sosh/`

### Wireframe
- Low-fidelity wireframe theme
- Grayscale/simplified colors
- Files: `tokens/jsonl-ai/wireframe/`

---

## Version Information

Current versions:
- **sys.orange:** 2.2.0
- **core.ouds:** 1.9.0
- **core.orange:** 1.2.0

---

## Common Token Patterns

### Color States
```
ouds.color.action.enabled      # Default state
ouds.color.action.hover        # Hover state
ouds.color.action.pressed      # Active/pressed state
ouds.color.action.disabled     # Disabled state
ouds.color.action.focus        # Focus state
ouds.color.action.loading      # Loading state
ouds.color.action.selected     # Selected state
```

### Spacing Scale
```
none     → 0px
2xsmall  → 1px
xsmall   → 2px
small    → 4px
medium   → 8px
large    → 16px
xlarge   → 24px
2xlarge  → 32px
3xlarge  → 40px
```

### Border Radius Scale
```
none    → 0px
small   → 4px
medium  → 8px
large   → 12px
pill    → 2000px
```

### Elevation Levels
```
none       # No shadow
raised     # Subtle lift
default    # Standard elevation
emphasized # Strong shadow
drag       # Dragging state
sticky     # Sticky element
```

---

## File Naming Conventions

### JSON Files
```
[category]_[subcategory].jsonl
```
Examples:
- `color_action_light.jsonl`
- `font_size.jsonl`
- `space_inset.jsonl`

### Markdown Files (Documentation)
```
dsm_[theme]_[category]_[subcategory].md
```
Examples:
- `dsm_orange_color_action_light.md`
- `dsm_sosh_font_size.md`

---

## Token Values Reference (Orange Theme - Light Mode)

### Background Colors (`ouds.color.bg.*`)
| Token | Use Case | Hex |
|-------|----------|-----|
| `ouds.color.bg.primary` | Main container background | `#ffffff` |
| `ouds.color.bg.secondary` | Alternate/nested containers | `#f4f4f4` |
| `ouds.color.bg.tertiary` | Warm accent background | `#f9f5f0` |
| `ouds.color.bg.inverse-low` | Dark inverse background | `#141414` |
| `ouds.color.bg.inverse-high` | Dark inverse background | `#141414` |

### Surface Colors (`ouds.color.surface.*`)
| Token | Use Case | Hex |
|-------|----------|-----|
| `ouds.color.surface.primary` | Elevated surfaces, cards | `#ffffff` |
| `ouds.color.surface.secondary` | Subtle surface overlay | `#0000000a` |
| `ouds.color.surface.tertiary` | Warm accent surface | `#bd793c14` |
| `ouds.color.surface.brand.primary` | Brand-colored surface | `#ff7900` |
| `ouds.color.surface.inverse-low` | Dark inverse surface | `#272727` |
| `ouds.color.surface.inverse-high` | Dark inverse surface | `#272727` |

**Status Surfaces:**
| Token | Muted | Emphasized |
|-------|-------|------------|
| Positive | `#3de35a1f` | `#138126` |
| Info | `#26b2ff14` | `#0073b2` |
| Warning | `#ffd00029` | `#ffd000` |
| Negative | `#db000214` | `#db0002` |
| Accent | `#bd793c14` | `#ff7900` |

### Border Colors (`ouds.color.border.*`)
| Token | Use Case | Hex |
|-------|----------|-----|
| `ouds.color.border.minimal` | Lightest outline | `#0000000a` |
| `ouds.color.border.muted` | Soft outline | `#00000014` |
| `ouds.color.border.default` | **Standard container outline** | `#00000033` |
| `ouds.color.border.emphasized` | Strong outline | `#000000` |
| `ouds.color.border.focus` | Focus state | `#000000` |
| `ouds.color.border.focus-inset` | Focus inset | `#ffffff` |
| `ouds.color.border.brand-primary` | Brand highlight | `#f15e00` |

**Status Borders:**
| Token | Hex |
|-------|-----|
| `ouds.color.border.status.positive` | `#138126` |
| `ouds.color.border.status.info` | `#0073b2` |
| `ouds.color.border.status.warning` | `#ffd000` |
| `ouds.color.border.status.negative` | `#db0002` |
| `ouds.color.border.status.accent` | `#ff7900` |

### Elevation Tokens (Composite Shadows)
| Token | Use Case | x | y | blur | spread | color |
|-------|----------|---|---|------|--------|-------|
| `elevation.none` | No shadow | 0px | 0px | 0px | 0px | transparent |
| `elevation.raised` | Subtle lift (cards) | 0px | 1px | 2px | 0px | `#00000052` |
| `elevation.default` | Standard elevation | 0px | 2px | 3px | -1px | `#00000052` |
| `elevation.emphasized` | Modals, popovers | 0px | 8px | 8px | -2px | `#0000003d` |
| `elevation.drag` | Dragging state | 0px | 4px | 4px | -1px | `#00000052` |
| `elevation.sticky` | Sticky headers | 0px | 4px | 4px | -1px | `#0000003d` |

**CSS box-shadow equivalents:**
```css
/* elevation.raised */
box-shadow: 0px 1px 2px 0px #00000052;

/* elevation.default */
box-shadow: 0px 2px 3px -1px #00000052;

/* elevation.emphasized */
box-shadow: 0px 8px 8px -2px #0000003d;

/* elevation.drag */
box-shadow: 0px 4px 4px -1px #00000052;

/* elevation.sticky */
box-shadow: 0px 4px 4px -1px #0000003d;
```

---

## Common UI Patterns

### Standard Container
```
Background: ouds.color.bg.primary → #ffffff
Border:     ouds.color.border.default → #00000033
```

### Nested/Card Container
```
Background: ouds.color.bg.secondary → #f4f4f4
Border:     ouds.color.border.default → #00000033
```

### Elevated Surface on Secondary Background
```
Base:       ouds.color.bg.secondary → #f4f4f4
Surface:    ouds.color.surface.primary → #ffffff
Border:     ouds.color.border.default → #00000033
Shadow:     elevation.raised → 0px 1px 2px 0px #00000052
```

### Modal/Dialog
```
Overlay:    ouds.color.overlay.* (check overlay tokens)
Surface:    ouds.color.surface.primary → #ffffff
Border:     ouds.color.border.default → #00000033
Shadow:     elevation.emphasized → 0px 8px 8px -2px #0000003d
```

### Status Container (e.g., Error)
```
Background: ouds.color.surface.status.negative.muted → #db000214
Border:     ouds.color.border.status.negative → #db0002
```

---

## Usage Guidelines

1. **Always use semantic tokens** (`ouds.*`) in components, not core or raw values
2. **Light/dark variants** are separate files - use appropriate variant for theme mode
3. **Composite typography tokens** bundle all type properties for consistency
4. **Platform tokens** ensure native feel on each platform
5. **Responsive tokens** automatically scale across breakpoints

---

## Quick Reference Paths (Bundled)

| Content | Path (within this skill package) |
|---------|----------------------------------|
| Orange theme tokens | `tokens/jsonl-ai/orange/` |
| SOSH theme tokens | `tokens/jsonl-ai/sosh/` |
| Wireframe theme tokens | `tokens/jsonl-ai/wireframe/` |
| Color action (light) | `tokens/jsonl-ai/[theme]/ai_[theme]_color_action_light.json` |
| Typography sizes | `tokens/jsonl-ai/[theme]/ai_[theme]_font_size.json` |
| Spacing insets | `tokens/jsonl-ai/[theme]/ai_[theme]_space_inset.json` |
| Grid definitions | `tokens/jsonl-ai/[theme]/ai_[theme]_grid_web.json` |

**Note:** Replace `[theme]` with `orange`, `sosh`, or `wireframe`.
