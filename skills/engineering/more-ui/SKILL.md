---
name: more-ui
description: Inspect, diagnose, and fix UI grid, alignment, spacing, sizing, and responsive layout issues with minimal changes (更多UI优化). Use when reviewing or modifying existing UI code or layouts while preserving design intent and functionality.
---

# 更多UI优化 (More UI)

## Role
Identify and fix UI layout inconsistencies with minimal changes while preserving design intent and functionality.

## Workflow
1. **Inspect:** Examine page structure, layout containers, Grid/Flex usage, reusable components, and design tokens.
2. **Identify:** Detect grid inconsistencies, misalignment, uneven spacing, inconsistent sizing, overflow, and responsive issues.
3. **Prioritize:** Fix broken layouts and major alignment issues before local visual details.
4. **Optimize:** Fix root causes using existing layout rules, components, and design tokens.
5. **Verify:** Check alignment, responsive behavior, dynamic content, and functional regressions.
6. **Report:** Summarize findings, changes, verification results, and unresolved issues.

## Rules
- Establish consistent page containers, content boundaries, grid columns, and spacing.
- Align headings, text, cards, tables, forms, icons, and controls appropriately.
- Use CSS Grid for two-dimensional layouts and Flexbox for one-dimensional layouts where appropriate.
- Reuse existing components, CSS variables, and design tokens.
- Avoid arbitrary positioning, negative-margin hacks, unnecessary pixel overrides, and unrelated refactoring.
- Preserve branding, information architecture, business logic, and existing interactions.
- Fix global issues before local details.
- Make only changes justified by identified problems.
- Never claim to have made changes or performed verification that did not occur.

## Verification
- Check major alignment boundaries and component spacing.
- Check for overflow, overlap, and layout regressions.
- Check desktop, tablet, and mobile layouts where possible.
- Ensure long text, dynamic content, and existing interactions remain functional.
- Distinguish actual test results from assumptions based on code inspection.

## Completion Criteria
- Critical layout issues are fixed or documented with blockers.
- Major grid and alignment rules are consistent.
- No known layout or functional regressions are introduced.
- Available verification is completed.
- Remaining issues and required materials are documented.

If source code, screenshots, or a preview environment are unavailable, perform the review possible and specify what is needed to continue.

## Output
### UI Grid and Visual Alignment Report

- **Overall Assessment:** Layout and alignment status.
- **Findings:** Issues, affected areas, and priorities.
- **Changes:** Modified locations and changes made.
- **Verification:** Checks performed and actual results.
- **Remaining Issues:** Unresolved problems, blockers, and required materials.
