# Design System: Enock Plumbing Solutions

## 1. Typeface Pairing
- **Display / Headings**: `Archivo` (weights 600, 700, 800) with `-0.01em` tracking and tight line-height (`1.12` to `1.15`). Chosen for its sturdy, industrial grotesque geometry that reads clearly on trade flyers, mobile job-site screens, and printed A4 quotations.
- **Body / Controls / Tabular Data**: `Source Sans 3` (weights 400, 500, 600, 700) with `tabular-nums` on quantities and currency amounts. Chosen for open counters and unambiguous numeral legibility on low-brightness phone screens outdoors.

## 2. Palette and Named Semantic Tokens
Sourced from physical plumbing materials (deep water supply pipework, copper fittings, and trade ledger paper):
- `--ink` (`#14202b`): Primary text and high-contrast foreground.
- `--ink-soft` (`#46535f`): Secondary labels, metadata, and helper copy.
- `--paper` (`#f5f2ec`): Warm off-white page background and alternate table row fill that reduces glare outdoors.
- `--white` (`#ffffff`): Elevated form card and input surface.
- `--navy` (`#0b3a5b`): Primary brand color, section rules, header band, and primary action buttons.
- `--navy-deep` (`#082a43`): Hover/active state for primary actions and dark hero overlays.
- `--water` (`#0a6aa6`): Interactive link hover accent on the main site.
- `--copper` (`#b2541b`): Trade fitting accent used for header borders, eyebrow kickers, and keyboard focus outlines.
- `--rule` (`#d9d3c8`): Crisp 1px structural dividers and card borders.
- `--danger` (`#a12a1d`): Destructive actions (deleting rows or saved quotations).
- `--r-card` (`10px`): Outer section card border radius.
- `--r-box` (`8px`): Nested container border radius (paste well, grand total bar, brand badge, toast).
- `--r-ctrl` (`7px`): Interactive control border radius (inputs, selects, textareas, buttons, row delete buttons).

## 3. Layout Structure
- **Quotation Generator (`quote.html`)**: Single-column numbered ledger workflow (`max-width: 980px`) divided into four task cards (Client/Quotation Details, Materials List with bulk paste parser, Other Charges, Notes/Terms) plus Saved Quotations and a pinned bottom action bar.
- **Small-Device Responsiveness (`<= 860px` and `<= 480px`)**: Compact two-column item cards where the item number and description occupy the top row with a pinned top-right remove button, followed by paired Quantity/Unit inputs (and Unit Price/Amount when enabled), preventing horizontal overflow at 320px-375px viewports and 200% zoom.
- **Signature Element**: The live plumbing materials paste-parser and dual-mode ledger (switching between an unpriced site materials list and a priced client quotation with live A4 PDF generation matching Enock's trade header and copper rule).

## 4. Motion Policy
- **What moves**: Toast notifications fade in/out (`opacity 0.2s`), button and link color transitions (`0.2s`), and smooth window scroll when loading a saved quotation (disabled when `prefers-reduced-motion: reduce` is active).
- **What stays still**: Form cards, table rows, and totals update instantaneously without layout-shifting entrance animations or bounce effects.
