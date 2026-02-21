---
name: general-strategic-docx
description: Formats Word documents (.docx) to match General Strategic's corporate style. Use when creating white papers, reports, briefs, or any professional documents for General Strategic. Applies correct typography (Helvetica Neue, HelveticaNowDisplay, Newsreader), page setup (A4 with asymmetric margins), cover page layout with logo, headers/footers with copyright, and table of contents styling.
---

# General Strategic Document Formatting

This skill formats Word documents to match General Strategic's corporate identity.

## Overview

General Strategic documents use a distinctive typographic hierarchy combining HelveticaNowDisplay for display text, Helvetica Neue for headings and UI elements, and Newsreader for body text. Documents are formatted on A4 with asymmetric margins (wider right margin for binding/notes).

## Page Setup

| Property | Value | Notes |
|----------|-------|-------|
| Page size | A4 (210 × 297mm) | Portrait orientation |
| Top margin | 20mm (1133 DXA) | |
| Bottom margin | 20mm (1133 DXA) | |
| Left margin | 25mm (1440 DXA) | |
| Right margin | 35mm (1967 DXA) | Wider for binding/margin notes |
| Header | 12.7mm (720 DXA) | From top edge |
| Footer | 11mm (623 DXA) | From bottom edge |

Enable "Different first page" for header/footer (first page has different footer, empty header).

## Typography

### Font Stack

**Display text (cover page):**
- HelveticaNowDisplay-Bold for titles
- HelveticaNowDisplay-Regular for subtitles and dates
- HelveticaNowDisplay-ExtLt for TOC entries

**Headings:**
- Helvetica Neue Bold for section headings

**Body text:**
- Newsreader 16pt Regular Light (or "Newsreader" if unavailable)

**Headers/Footers:**
- Helvetica Neue Light

### Style Definitions

| Style | Font | Size | Spacing | Notes |
|-------|------|------|---------|-------|
| Body | Newsreader 16pt Regular Light | 10pt | Line: 1.2× (288 twips) | Black text |
| Heading 2 | Helvetica Neue Bold | 10.5pt | Before: 0, After: 2pt, Line: 1.5× | Keep with next |
| Heading (generic) | Helvetica Neue Bold | 13.5pt | Line: 1.5× | |
| TOC 1 | HelveticaNowDisplay-ExtLt | 9pt | Before: 8pt | Right-aligned page numbers |
| TOC 2 | HelveticaNowDisplay-Regular | 7pt | First-line indent | |
| Header & Footer | Helvetica Neue Light | 7pt | | |

### Cover Page Typography

| Element | Font | Size |
|---------|------|------|
| Main title | HelveticaNowDisplay-Bold | 32pt |
| Subtitle | HelveticaNowDisplay-Regular | 15.5pt |
| Document type (e.g. "WHITE PAPER") | HelveticaNowDisplay-Bold | 13.5pt |
| Date | HelveticaNowDisplay-Regular | 13.5pt |
| Authors | HelveticaNowDisplay-Regular | 11.5pt |

### Section Heading Borders

Major section headings may have a grey bottom border:
- Style: Single line
- Colour: #a7a7a7
- Width: 1pt (8 eighths)
- Space below border: 3pt

## Logo Placement

The General Strategic logo (`assets/gs-logo.png`) appears at the top of the cover page.

**Positioning:**
- Insert as anchored image behind text
- Position: Top-left of first paragraph
- Approximate size: 5.5cm × 0.6cm
- Wrap: None (behind text)

The logo displays the text "[ ] General Strategic" in black.

## Cover Page Structure

Build the cover page in this order:

1. **Logo** — Anchored image at top (behind text)
2. **Vertical spacing** — Empty paragraphs (approximately 12–15) to push content down
3. **Main title** — 32pt bold, the document's primary title
4. **Subtitle** — 15.5pt regular, one or two lines describing the document
5. **More vertical spacing** — Empty paragraphs (approximately 6–8)
6. **Document type** — 13.5pt bold, e.g. "WHITE PAPER", "BRIEF", "REPORT"
7. **Date** — 13.5pt regular, e.g. "May 2025"
8. **Authors** — 11.5pt regular (optional)

Insert a section break after the cover page to allow different headers/footers.

## Headers and Footers

### Default Header (pages 2+)

Empty (no content).

### First Page Header

Empty (no content).

### Default Footer (pages 2+)

Right-aligned, containing:
- "© General Strategic Group [YEAR]" in Helvetica Neue Light 7pt
- Page number field in Helvetica Neue Bold 7pt

Example: `© General Strategic Group 2025    Page 3`

### First Page Footer

Left-aligned, containing:
- "© General Strategic Group Pty Ltd [YEAR]" in Helvetica Neue Light 7pt

Note the first page uses "Pty Ltd" while subsequent pages omit it.

## Table of Contents

Use a two-level TOC (Heading 2 entries only, as documents typically don't use Heading 1).

**TOC Field code:** `TOC \o 1-2`

**TOC 1 style:**
- HelveticaNowDisplay-ExtLt 9pt
- Space before: 8pt
- Tab stop with dot leader for page numbers

**TOC 2 style:**
- HelveticaNowDisplay-Regular 7pt
- First-line indent

## Content Structure

- Use **Heading 2** for all section headings (Heading 1 is not used)
- Body text uses 1.2× line spacing
- Use smart quotes: ' ' for single, " " for double
- Bookmarks are used for TOC navigation (auto-generated)

## Colour Scheme

| Element | Colour |
|---------|--------|
| All text | Black (#000000) |
| Heading borders | Grey (#a7a7a7) |

## Quick Reference: Creating a New Document

1. Set page size to A4, apply asymmetric margins
2. Enable "Different first page" for headers/footers
3. Insert logo at top of first page (anchored, behind text)
4. Create cover page with title, subtitle, document type, date
5. Insert section break (continuous or next page)
6. Set up footers: first page (left, Pty Ltd), subsequent (right, no Pty Ltd, with page number)
7. Insert TOC with Heading 2 entries
8. Apply Heading 2 style to section headings
9. Write body content using Body style
10. Update TOC fields before finalising

## Implementation Notes

When creating documents programmatically using python-docx or similar:

- Font names must match exactly: "Helvetica Neue", "HelveticaNowDisplay-Bold", etc.
- DXA units: 1440 DXA = 1 inch = 2.54cm
- EMU units for images: 914400 EMU = 1 inch
- Line spacing multiplier 288 = 1.2× (multiply by 240 for twips)
- Use `titlePg` in section properties for different first page headers/footers
