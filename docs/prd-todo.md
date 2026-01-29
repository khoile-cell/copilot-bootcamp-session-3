# Product Requirements Document (PRD) - Todo App Upgrade (Due Dates, Priority, Filters)

## 1. Overview

We are upgrading the basic TODO app to support due dates, simple priority levels, and filters so users can better organize tasks and focus on what’s urgent. The MVP intentionally keeps storage local and avoids backend changes to ensure a teachable, lightweight implementation.

---

## 2. MVP Scope

- Data model:
  - `title`: required.
  - `priority`: enum `"P1" | "P2" | "P3"`; default `"P3"`.
  - `dueDate`: optional; ISO `YYYY-MM-DD`. Invalid values are ignored (treated as absent).
- Filters:
  - Views: **All**, **Today**, **Overdue**.
  - Behavior: **All** shows all tasks (including completed). **Today** and **Overdue** show only incomplete tasks.
- Storage & architecture:
  - Local storage only; no backend or external storage changes.
- UI & components:
  - Use Material UI (MUI) for form elements, lists, buttons, and tabs/filters.
  - Display priority as `P1`, `P2`, or `P3` labels.
- Validation:
  - `title` must be present.
  - `priority` must be one of `P1`, `P2`, `P3`.
  - `dueDate` must be valid ISO `YYYY-MM-DD`; otherwise ignore.

---

## 3. Post-MVP Scope

- Overdue highlighting: visually emphasize overdue tasks.
- Sorting rules (list ordering):
  - Overdue first → Priority (P1 → P3) → Due date ascending → Undated last.

---

## 4. Out of Scope

- Notifications.
- Recurring tasks.
- Multi-user features.
- Keyboard navigation.
- External storage or backend changes (remain local-only).
