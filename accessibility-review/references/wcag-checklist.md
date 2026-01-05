# WCAG 2.1/2.2 Level AA Checklist

This checklist covers the most common and impactful WCAG 2.1/2.2 Level AA requirements for modern web applications.

## 1. Perceivable

Information and UI components must be presentable to users in ways they can perceive.

### 1.1 Text Alternatives

- [ ] **Images**: All meaningful images have descriptive alt text
- [ ] **Decorative images**: Decorative images have empty alt (`alt=""`) or are CSS backgrounds
- [ ] **Complex images**: Charts, diagrams have detailed descriptions (via longdesc, adjacent text, or aria-describedby)
- [ ] **Form image buttons**: Image buttons (`<input type="image">`) have descriptive alt text
- [ ] **Icons**: Icon-only buttons have accessible labels (aria-label, sr-only text, or title)

### 1.2 Time-based Media

- [ ] **Captions**: Videos have synchronized captions
- [ ] **Transcripts**: Audio content has text transcripts
- [ ] **Audio descriptions**: Video content has audio descriptions where needed (Level AA)
- [ ] **Live captions**: Live audio has captions (Level AA)

### 1.3 Adaptable

- [ ] **Semantic HTML**: Use proper semantic elements (nav, main, article, aside, header, footer)
- [ ] **Heading hierarchy**: Logical heading structure (h1 → h2 → h3, no skipped levels)
- [ ] **Lists**: Use proper list markup (ul, ol, dl) for list content
- [ ] **Form labels**: All form inputs have associated labels
- [ ] **Reading order**: DOM order matches visual order
- [ ] **Meaningful sequence**: Content order makes sense without CSS
- [ ] **Sensory instructions**: Don't rely solely on shape, size, location, or sound (e.g., "click the round button on the right")

### 1.4 Distinguishable

- [ ] **Color alone**: Don't use color as the only way to convey information
- [ ] **Text contrast**: Minimum 4.5:1 for normal text, 3:1 for large text (18pt+ or 14pt+ bold)
- [ ] **UI component contrast**: 3:1 minimum for interactive components and graphics
- [ ] **Text resize**: Text can be resized up to 200% without loss of functionality
- [ ] **Images of text**: Avoid images of text (use actual text with CSS styling)
- [ ] **Reflow**: Content reflows at 320px width (400% zoom) without horizontal scrolling
- [ ] **Text spacing**: Content remains readable when users adjust spacing
- [ ] **Content on hover/focus**: Hoverable/focusable content is dismissible, hoverable, and persistent

## 2. Operable

UI components and navigation must be operable.

### 2.1 Keyboard Accessible

- [ ] **Keyboard navigation**: All interactive elements are keyboard accessible
- [ ] **No keyboard trap**: Users aren't trapped in any component
- [ ] **Keyboard shortcuts**: Single-key shortcuts can be disabled, remapped, or only active on focus
- [ ] **Custom controls**: Custom interactive elements respond to keyboard correctly (Enter/Space to activate)

### 2.2 Enough Time

- [ ] **Timing adjustable**: Users can extend, adjust, or disable time limits
- [ ] **Pause/Stop**: Auto-updating content can be paused, stopped, or hidden
- [ ] **No time limits**: Avoid time limits on interactions when possible
- [ ] **Timeouts**: Warn users about data loss due to inactivity (20+ hours of warning)

### 2.3 Seizures

- [ ] **No flashing**: Nothing flashes more than 3 times per second
- [ ] **Animation**: Provide option to disable non-essential motion/animations

### 2.4 Navigable

- [ ] **Skip links**: Provide skip links to bypass repetitive content
- [ ] **Page titles**: Every page has a unique, descriptive title
- [ ] **Focus order**: Focus order is logical and predictable
- [ ] **Link purpose**: Link text describes the destination (avoid "click here")
- [ ] **Multiple navigation**: Multiple ways to find pages (menu, search, sitemap)
- [ ] **Headings and labels**: Headings and labels are descriptive
- [ ] **Visible focus**: Keyboard focus is clearly visible
- [ ] **Focus appearance**: Focus indicators meet minimum size and contrast (WCAG 2.2)

### 2.5 Input Modalities

- [ ] **Pointer gestures**: Path-based or multipoint gestures have single-pointer alternatives
- [ ] **Pointer cancellation**: Click/tap activation happens on up-event (or can be aborted)
- [ ] **Label in name**: Accessible name contains the visible label text
- [ ] **Motion actuation**: Motion-based controls have alternative UI controls
- [ ] **Target size**: Interactive targets are at least 44×44px (Level AA - WCAG 2.2)
- [ ] **Dragging**: Dragging actions have single-pointer alternatives (WCAG 2.2)

## 3. Understandable

Information and UI operation must be understandable.

### 3.1 Readable

- [ ] **Language**: Page language is declared (`lang` attribute on `<html>`)
- [ ] **Language changes**: Changes in language are marked up (`lang` on element)
- [ ] **Unusual words**: Definitions provided for jargon, idioms, slang

### 3.2 Predictable

- [ ] **Focus changes**: Focus doesn't automatically trigger navigation or form submission
- [ ] **Input changes**: Changing a setting doesn't automatically cause context changes (unless user is warned)
- [ ] **Consistent navigation**: Navigation is consistent across pages
- [ ] **Consistent identification**: Components with same functionality are identified consistently
- [ ] **Change on request**: Major context changes are user-initiated

### 3.3 Input Assistance

- [ ] **Error identification**: Form errors are clearly identified
- [ ] **Labels or instructions**: Form inputs have clear labels and instructions
- [ ] **Error suggestions**: Provide suggestions for fixing input errors
- [ ] **Error prevention**: Important actions (legal, financial, data deletion) are reversible, checked, or confirmed
- [ ] **Accessible authentication**: Don't require cognitive function tests (WCAG 2.2 - puzzles, remembering patterns)
- [ ] **Redundant entry**: Don't ask for same information twice (WCAG 2.2 - unless necessary for security)

## 4. Robust

Content must be robust enough to be interpreted by a wide variety of user agents, including assistive technologies.

### 4.1 Compatible

- [ ] **Valid HTML**: No duplicate IDs, proper nesting, unique element attributes
- [ ] **Name, Role, Value**: Custom components have proper ARIA roles, states, and properties
- [ ] **Status messages**: Status messages use proper ARIA live regions or role=status/alert
- [ ] **ARIA usage**: ARIA is used correctly (don't override native semantics)
- [ ] **Form labels**: Inputs have programmatically associated labels
- [ ] **Required fields**: Required form fields are marked up correctly

## React/JSX-Specific Checks

- [ ] **Fragment keys**: List items inside fragments have unique keys
- [ ] **Button type**: Buttons have explicit type (type="button" or type="submit")
- [ ] **Event handlers**: onClick handlers have equivalent onKeyDown/onKeyPress handlers for non-button elements
- [ ] **htmlFor**: Labels use `htmlFor` (not `for`) in JSX
- [ ] **Autofocus**: Avoid autofocus on page load (only use in modals/dialogs if needed)
- [ ] **Tab index**: Avoid positive tabIndex values (use 0 or -1 only)

## Common Patterns

### Modals/Dialogs

- [ ] Focus trapped within modal when open
- [ ] Focus returns to trigger element when closed
- [ ] Escape key closes modal
- [ ] Modal has role="dialog" and aria-modal="true"
- [ ] Modal has accessible label (aria-labelledby or aria-label)

### Forms

- [ ] All inputs have labels (explicit `<label>` or aria-label)
- [ ] Required fields marked with required attribute or aria-required
- [ ] Error messages use aria-describedby or aria-errormessage
- [ ] Groups of related inputs use fieldset/legend

### Custom Dropdowns/Selects

- [ ] Proper ARIA roles (combobox, listbox, option)
- [ ] Keyboard navigation (Arrow keys, Enter, Escape)
- [ ] Proper aria-expanded state
- [ ] aria-activedescendant for focus management

### Tabs

- [ ] role="tablist" on container, role="tab" on buttons, role="tabpanel" on content
- [ ] aria-selected on active tab
- [ ] Arrow keys navigate between tabs
- [ ] Tab key moves focus out of tab list
- [ ] aria-controls links tabs to panels

### Accordions

- [ ] Buttons to toggle have aria-expanded
- [ ] Content regions have proper IDs linked via aria-controls
- [ ] Clear keyboard navigation

### Tooltips

- [ ] Dismissible with Escape key
- [ ] Persist on hover
- [ ] Don't hide on accidental mouse movement
- [ ] Use aria-describedby to link tooltip to trigger

## Testing Tools

While manual review is the focus, these tools can help validate findings:

- **Browser DevTools**: Chrome/Firefox accessibility inspector
- **Contrast checkers**: WebAIM, Colour Contrast Analyser
- **Screen readers**: NVDA (Windows), VoiceOver (Mac), JAWS (Windows)
- **Keyboard testing**: Unplug mouse and navigate with Tab, Enter, Space, Arrow keys
- **Browser extensions**: axe DevTools, WAVE, Lighthouse
