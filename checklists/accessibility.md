# Accessibility Checklist (WCAG 2.1 AA, basics)

Legend: tick when checked and OK, write the defect id when it fails, write N/A with a reason when it does not apply.

> An automated scanner (axe, Lighthouse) finds only part of the problems. Keep the keyboard and screen-reader sections as manual work.

## Automated scan
- [ ] Scan every main page and every state that changes content (dialogs, errors, results). Attach the results.
- [ ] No critical or serious violations. Review the rest.

## Keyboard (no mouse)
- [ ] Every interactive control receives focus with Tab, in a logical order. **Walk the whole purchase or main task**, not only the first page.
- [ ] Every control works with Enter (buttons, links) or Space (buttons, checkboxes). A link without an `href` or a clickable `<div>` usually fails here.
- [ ] Focus is clearly visible on every control (outline, border or colour change).
- [ ] Focus is never trapped; Escape closes menus and dialogs and focus returns where it came from.
- [ ] No keyboard shortcut works only on a single letter without a way to turn it off.

## Structure and content
- [ ] Page has a unique, meaningful title and a language (`<html lang>`).
- [ ] One main heading; headings are in order.
- [ ] Images have meaningful `alt` text; decorative images have empty `alt`.
- [ ] Form fields have visible labels; errors say what is wrong and how to fix it, and are tied to the field.
- [ ] Links and buttons have names that make sense out of context ("Add Backpack to cart", not "Click here").

## Colour and size
- [ ] Text contrast is at least 4.5:1 (3:1 for large text); controls and focus indicators at least 3:1.
- [ ] Information is never given by colour alone.
- [ ] Page works at 200% zoom and at 320 px wide with no horizontal scroll or lost content.

## Screen reader (NVDA, VoiceOver, TalkBack)
- [ ] Page title, headings and landmarks are announced sensibly.
- [ ] Form errors and status messages are announced when they appear.
- [ ] Reading order matches the visual order.
