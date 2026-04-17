# 📝 Advanced Todo Item Card Component (Stage 1a)

A production-ready, interactive Todo Card component built with vanilla HTML, CSS, and JavaScript. This component extends the Stage 0 version with full edit capabilities, status management, priority indicators, expand/collapse, overdue alerts, and enhanced accessibility – all while maintaining testability via `data-testid` attributes.

## ✨ Features (Stage 1a Additions)

### 🔧 Edit Mode (Complete CRUD)
- **Edit Button**: Switches card into inline edit form
- **Editable Fields**: Title, description, priority, due date & time
- **Save / Cancel**: Save persists changes; Cancel restores previous values
- **Focus Management**: Returns focus to Edit button after closing form
- **Form Test IDs**: All edit form elements have dedicated `data-testid` for testing

### 🎛️ Status Controls
- **Status Dropdown**: Manually set status to `Pending`, `In Progress`, or `Done`
- **Bidirectional Sync**: Checkbox ↔ Status dropdown ↔ Status badge stay perfectly in sync
- **Visual Status Styles**:
  - `Done` → strikethrough title + muted card
  - `In Progress` → distinct blue badge with left border
  - `Pending` → neutral badge

### 🚦 Priority Indicator Enhancements
- **Priority Dot**: Colored dot next to title (`test-todo-priority-indicator`)
- **Left Border Accent**: Card gets a coloured left border matching priority (red = High, orange = Medium, green = Low)
- **Badge Styling**: Dynamic background and border colour change

### 📝 Expand / Collapse Description
- **Collapsible Text**: Description collapses to 2 lines if longer than ~80 characters
- **Toggle Button**: `Expand` / `Collapse` with `aria-expanded` and `aria-controls`
- **Keyboard Accessible**: Fully operable via keyboard

### ⏰ Time Management Enhancements
- **Overdue Indicator**: Explicit badge (`⚠️ Overdue`) appears when due date has passed
- **Granular Time Strings**: 
  - `Due in 2 days`, `Due tomorrow`, `Due in 3 hours`, `Due in 45 minutes`
  - `Overdue by 1 hour`, `Overdue by 2 days`
- **Live Updates**: Time remaining recalculates every 30 seconds
- **Smart Stop**: When status = `Done`, timer stops and displays `Completed`
- **Overdue Sync**: Overdue badge updates automatically with timer

### ♿ Accessibility Improvements (Stage 1a)
- **ARIA Expanded**: Expand/collapse button uses `aria-expanded` and `aria-controls`
- **Form Labels**: Every edit field has `<label for="...">` for screen readers
- **Status Dropdown Label**: Accessible name via `aria-labelledby`
- **Focus Trapping (optional)**: Focus stays within edit form while open
- **Live Region**: Time remaining uses `aria-live="polite"` for automatic announcements

### 📱 Responsive Enhancements
- **Edit Form Stacking**: On mobile (<480px), edit form fields stack vertically
- **Button Full Width**: Action buttons stretch on narrow screens
- **No Overflow**: Long titles, tags, and descriptions wrap gracefully

## 🆚 What Changed from Stage 0

| Stage 0 | Stage 1a |
|---------|----------|
| Static display only | Full inline editing with Save/Cancel |
| No status control | Status dropdown + full sync with checkbox |
| Priority badge only | Priority dot + left border accent + dynamic styling |
| Always expanded description | Collapsible with toggle button (if text long) |
| No overdue indicator | Overdue badge + dynamic updates |
| Time remaining updates every 45s | Updates every 30s + overdue sync |
| No explicit `In Progress` style | Distinct visual style for `In Progress` |
| Cancel not available | Cancel restores original values |
| Status reset on save (bug) | Fixed: status persists after edit |
| Timer leaks on status change | Fixed: single timer, cleaned up properly |
| Missing ARIA for expand | Added `aria-expanded`, `aria-controls` |
| Edit form missing labels | All fields have proper `<label>` |

## 🧪 Test IDs (All Stage 0 + Stage 1a)

| Test ID | Element |
|---------|---------|
| `test-todo-card` | Main card container |
| `test-todo-title` | Task title |
| `test-todo-description` | Task description (collapsible) |
| `test-todo-priority` | Priority text inside badge |
| `test-todo-due-date` | Due date display |
| `test-todo-status` | Status badge |
| `test-todo-time-remaining` | Time remaining text |
| `test-todo-tags` | Tags list container |
| `test-todo-tag-work` | Work tag chip |
| `test-todo-tag-urgent` | Urgent tag chip |
| `test-todo-complete-toggle` | Completion checkbox |
| `test-todo-edit-button` | Edit button |
| `test-todo-delete-button` | Delete button |
| **NEW** `test-todo-priority-indicator` | Priority dot / left border indicator |
| **NEW** `test-todo-status-control` | Status dropdown |
| **NEW** `test-todo-expand-toggle` | Expand/collapse button |
| **NEW** `test-todo-collapsible-section` | Collapsible description container |
| **NEW** `test-todo-overdue-indicator` | Overdue badge |
| **NEW** `test-todo-edit-form` | Edit mode container |
| **NEW** `test-todo-edit-title-input` | Edit title input |
| **NEW** `test-todo-edit-description-input` | Edit description textarea |
| **NEW** `test-todo-edit-priority-select` | Edit priority dropdown |
| **NEW** `test-todo-edit-due-date-input` | Edit due date picker |
| **NEW** `test-todo-save-button` | Save button |
| **NEW** `test-todo-cancel-button` | Cancel button |

## ♿ Accessibility Notes

- **Keyboard Tab Order**: Checkbox → Status dropdown → Expand toggle → Edit button → Delete button (Save/Cancel in edit mode)
- **Focus Indicators**: 3px blue outline with offset on all interactive elements
- **ARIA Live**: Time remaining uses `aria-live="polite"` so screen readers announce changes
- **Semantic HTML**: `<article>`, `<time datetime>`, `<ul role="list>`, `<button>` with proper types
- **Colour Contrast**: All dynamic colours (priority, status, overdue) maintain 4.5:1 minimum contrast
- **Focus Return**: After closing edit mode, focus returns to Edit button (no keyboard trap)

## 📦 Technical Implementation

### State Management
Global `state` object holds:
- `title`, `description`, `priority`, `dueDateUTC`, `status`

### Core Functions
- `refreshAll()` – applies state to UI
- `updateTimeAndOverdue()` – calculates and displays time remaining + overdue badge
- `openEditMode()` / `closeEditMode(save)` – handles edit flow with backup/restore
- `startTimer()` – manages 30-second interval (cleaned up on status `Done`)

### Event Handling
- Checkbox → updates status to `Done` / `Pending`
- Status dropdown → updates status, syncs checkbox & badge
- Expand toggle → toggles `collapsed` / `expanded` classes
- Edit button → opens form, populates current values, backs up state
- Cancel button → restores from backup, closes form
- Save button → applies new values, keeps existing status, refreshes UI

## 🧪 Known Limitations (Stage 1a)

1. **Focus trapping inside edit form** – Not implemented (optional bonus), but focus returns to Edit button on close.
2. **Description length threshold** – Fixed at ~80 characters; could be made configurable.
3. **Time zone handling** – Due date stored as UTC, displayed in local browser time.
4. **Delete action** – Still shows `alert()` (no actual removal to keep demo simple).
5. **Tag editing** – Tags are static; not part of edit mode.
6. **Overdue badge** – Does not animate; simply appears/disappears.
7. **Mobile datetime picker** – Relies on browser native input; appearance varies.


