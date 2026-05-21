# Product Requirements Document (PRD) - TODO App Upgrade

## 1. Overview

We are upgrading the basic TODO app (currently only `title` and `completed`) to make it more practical for organizing tasks without adding excessive complexity. The upgrade introduces optional due dates, a simple three-level priority system, and filter tabs so users can quickly focus on what is due today or overdue. Storage remains local; no backend changes are required.

---

## 2. MVP Scope

- Add `dueDate` field to tasks
  - Optional
  - ISO format `YYYY-MM-DD`
  - Invalid values are ignored (treated as absent)
- Add `priority` field to tasks
  - Enum: `P1 | P2 | P3`
  - Default: `P3`
- `title` remains required
- Filter tabs: **All**, **Today**, **Overdue**
  - **All** view includes completed tasks
  - **Today** and **Overdue** views show only incomplete tasks
- Keep storage local (no backend, no external storage)

---

## 3. Post-MVP Scope

- Overdue tasks visually highlighted (e.g., red)
- Priority color-coded badges
  - P1: red
  - P2: orange
  - P3: gray
- Sorting rules:
  1. Overdue first
  2. Then by priority (P1 → P2 → P3)
  3. Then by due date ascending
  4. Undated tasks last

---

## 4. Out of Scope

- Notifications
- Recurring tasks
- Multi-user support
- Keyboard navigation and additional accessibility features
- External storage (remains local only)
