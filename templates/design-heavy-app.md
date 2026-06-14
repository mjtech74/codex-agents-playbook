# AGENTS.md - Design Heavy App

## Design Work Rules

- Build the actual usable screen, not a marketing placeholder.
- Match the existing design system before inventing new components.
- Keep density appropriate to the domain: operational tools should be calm, scannable, and efficient.
- Use familiar controls for familiar actions: icon buttons, toggles, segmented controls, sliders, tabs, menus, and tables where appropriate.
- Do not place cards inside cards unless the existing design system requires it.
- Avoid decorative backgrounds that make the product harder to read.

## Responsive Safety

- Check text fit at mobile and desktop widths.
- Use stable dimensions for grids, boards, toolbars, counters, and tiles.
- Do not scale font size directly with viewport width.
- Ensure hover, loading, and error states do not shift the layout unexpectedly.

## Browser Verification

- Verify the page in a real browser after visual changes when practical.
- Check for console errors.
- Inspect key interactions, empty states, loading states, and error states.
- For 3D/canvas/media work, verify the canvas or media is nonblank, framed correctly, and actually interactive or moving.

## Final Review

- Confirm the UI answers the user's workflow, not just the screenshot.
- Report what was visually verified and what remains unverified.
