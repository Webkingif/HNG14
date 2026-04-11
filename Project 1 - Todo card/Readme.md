# 📝 Todo Item Card Component

A production-ready, testable Todo Card component built with vanilla HTML, CSS, and JavaScript. This component demonstrates modern frontend development practices including semantic HTML5, WCAG AA accessibility compliance, responsive design, and comprehensive testability with `data-testid` attributes.

## ✨ Features

### Core Functionality
- **Task Display**: Shows task title, description, priority level (Low/Medium/High), and completion status
- **Smart Time Remaining**: Automatically calculates and displays human-readable time remaining (Due in X days, Due tomorrow, Due in X hours, Due now!, Overdue by X days/hours)
- **Completion Toggle**: Checkbox that strikes through title and changes status from "In Progress" to "Done"
- **Tag System**: Displays categorized tags (Work, Urgent, Design) with visual chips
- **Edit/Delete Actions**: Interactive buttons with console logging (easily extensible for real functionality)

### Accessibility (WCAG AA Compliant)
- **Keyboard Navigation**: Full keyboard support with logical tab order (checkbox → edit → delete)
- **Visible Focus Indicators**: High-contrast focus outlines for all interactive elements
- **Screen Reader Ready**: Semantic HTML5 elements, ARIA labels, and `aria-live="polite"` for time updates
- **Color Contrast**: Minimum 4.5:1 ratio for all text elements
- **Proper Form Labels**: Checkbox has associated `<label>` element

### Responsive Design
- **Mobile (320px - 480px)**: Full width, stacked vertical layout, flexible tags
- **Tablet (481px - 768px)**: Centered card, comfortable padding
- **Desktop (769px+)**: Max-width 500px, centered layout

### Testability
- **13 Required `data-testid` Attributes**: Complete coverage for automated testing
- **Predictable Behavior**: Fixed due date ensures consistent time calculations
- **No External Dependencies**: Pure vanilla implementation for reliable testing

### Technical Highlights
- **Live Updates**: Time remaining refreshes every 45 seconds
- **Performance Optimized**: Updates pause when browser tab is in background
- **Semantic HTML**: Proper use of `<article>`, `<time datetime>`, `<ul role="list>`, `<button>`
- **Cross-Browser Compatible**: Works on Chrome, Firefox, Safari, and Edge