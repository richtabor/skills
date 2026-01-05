---
name: accessibility-review
description: Conducts manual accessibility reviews of UI components, pages, and applications against WCAG 2.1/2.2 Level AA standards. Triggers when users ask questions like "Is this accessible?", "Can you review the color contrast?", or request accessibility checks. Provides prioritized findings (Critical/Warning) focused on practical, modern web accessibility standards.
---

# Accessibility Review

## Overview

This skill enables manual accessibility reviews of web content, components, and applications against WCAG 2.1/2.2 Level AA standards. Reviews focus on practical, modern accessibility requirements without being overly pedantic.

## When to Use This Skill

Use this skill when the user asks questions like:
- "Is this accessible?"
- "Can you review the color contrast?"
- "Check this component for accessibility issues"
- "Does this meet accessibility standards?"
- Any request to review, check, or validate accessibility

## Review Process

### 1. Identify the Target

Determine what needs to be reviewed:
- Specific component (button, form, modal, etc.)
- Full page or application
- Code file or set of files
- Design mockup or screenshot

### 2. Conduct Manual Review

Use the WCAG checklist in `references/wcag-checklist.md` to systematically review the target against modern accessibility standards.

Focus on the most common and impactful issues:
- **Perceivable**: Color contrast, text alternatives, semantic structure
- **Operable**: Keyboard navigation, focus management, interactive elements
- **Understandable**: Clear labels, error handling, consistent navigation
- **Robust**: Valid HTML, ARIA usage, compatibility

### 3. Prioritize Findings

Classify each issue as:

**Critical** - Blocks users from accessing core functionality:
- Missing alt text on meaningful images
- Non-keyboard accessible interactive elements
- Insufficient color contrast (below 4.5:1 for normal text, 3:1 for large text)
- Forms without proper labels
- Missing focus indicators
- Inaccessible modal/dialog patterns
- Auto-playing media without controls

**Warning** - Creates friction but doesn't fully block access:
- Suboptimal heading hierarchy (skipped levels)
- Missing ARIA landmarks
- Link text that's unclear out of context
- Redundant or unnecessary ARIA
- Touch targets smaller than 44x44px
- Missing skip links
- Non-descriptive error messages

### 4. Present Findings

Structure the report as:

```
## Accessibility Review

### Critical Issues
1. [Issue description with location reference]
   - Impact: [How this affects users]
   - Fix: [Specific recommendation]

### Warnings
1. [Issue description with location reference]
   - Impact: [How this affects users]
   - Fix: [Specific recommendation]

### Summary
[Brief overview of findings and general recommendations]
```

## Review Guidelines

**Be Practical**: Focus on issues that genuinely impact users. Modern WCAG 2.1/2.2 Level AA is the standard—avoid over-engineering or citing obscure edge cases.

**Be Specific**: Reference actual code locations using `file_path:line_number` format when possible.

**Be Constructive**: Provide actionable fixes, not just problems. Include code examples when helpful.

**Consider Context**: Some patterns may have accessibility trade-offs. Acknowledge these and suggest the most accessible approach for the use case.

## Common Patterns to Check

### Interactive Elements
- All interactive elements must be keyboard accessible (Enter/Space to activate)
- Focus must be visible with clear indicators
- Custom controls need proper ARIA roles and states

### Forms
- All inputs must have associated labels (explicit or aria-label)
- Error messages must be programmatically associated with fields
- Required fields must be indicated clearly

### Color and Contrast
- Text contrast: 4.5:1 minimum for normal text, 3:1 for large text (18pt+ or 14pt+ bold)
- UI components: 3:1 contrast for interactive elements and their states
- Don't rely on color alone to convey information

### Images and Media
- Meaningful images need descriptive alt text
- Decorative images should have empty alt (alt="")
- Videos need captions, audio content needs transcripts

### Structure
- Use semantic HTML (nav, main, article, etc.)
- Heading hierarchy should be logical (h1 → h2 → h3)
- ARIA landmarks help screen reader navigation

## Resources

This skill includes:

### references/wcag-checklist.md
Comprehensive checklist of WCAG 2.1/2.2 Level AA requirements organized by principle (Perceivable, Operable, Understandable, Robust). Reference this during reviews to ensure thorough coverage of accessibility standards.
