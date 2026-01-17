# Visibility, Selection, and Export (How They Work Together)

This page explains a common source of confusion in FreeCAD:
**visibility**, **selection**, and **export** are related, but they are not the same thing.

Understanding how they interact prevents accidental exports and missing geometry.

---

## The three concepts (short version)

- **Visibility** controls what you can *see*
- **Selection** controls what you are *acting on*
- **Export** uses *both* visibility and selection rules

Keeping these separate in your head makes FreeCAD much easier to predict.

---

## Visibility

Visibility answers one question:

> **Is this object currently shown?**

- Visible objects appear in the 3D view
- Hidden objects do not appear
- Visibility is toggled with the **Spacebar**

Important:
- Hidden objects are **ignored during export**
- Visibility does not mean the object is selected

---

## Selection

Selection answers a different question:

> **Which object am I working on right now?**

- Clicking an object selects it
- Selected objects highlight in the tree and 3D view
- You can select objects that are visible or hidden (via the tree)

Selection alone does **not** guarantee export.

---

## Export (what FreeCAD actually does)

When exporting, FreeCAD follows these rules:

1. Only **visible** objects are considered
2. If something is **selected**, only the selected visible objects export
3. If nothing is selected, **all visible objects** export

This is why accidental multi-body exports happen.

---

## Safe export workflow (recommended)

To export a single Body safely:

1. Hide all other Bodies (Spacebar)
2. Confirm only **one Body is visible**
3. Select that Body
4. File → Export → STL / 3MF

This removes ambiguity and prevents mixed exports.

---

## Common mistakes (and why they happen)

### “Why did my export include multiple parts?”
- More than one Body was visible

### “Why did nothing export?”
- The Body was hidden

### “Why did the wrong thing export?”
- Selection did not match visibility

These are visibility issues, not file format problems.

---

## How this relates to duplication and dependencies

- Duplication uses **selection**
- Export uses **visibility + selection**
- Dependencies determine *what must exist*, not *what exports*

Each system has a different purpose.

---

## One-sentence takeaway

> **If you can’t see it, it won’t export. If you don’t select it, FreeCAD may export more than you expect.**
