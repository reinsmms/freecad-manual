# Dependencies (Plain-English Explanation)

This page explains **dependencies** in FreeCAD using everyday language.
You do **not** need to understand FreeCAD’s internal dependency system to work safely and predictably.

---

## The key idea

> **Dependencies describe what an object uses, not what it contains.**

This distinction removes most confusion.

---

## “Uses” vs “Contains”

In FreeCAD:

- **Contains** means *physically holds* something in the model tree  
- **Uses** means *relies on as a reference*

Most dependencies are **uses**, not **contains**.

---

## Examples

### Example 1: A sketch on a plane

- The Body **contains** the sketch
- The sketch **uses** the plane
- The plane is **not part of** the sketch

Deleting the plane does not delete the sketch, but it may break its references.

---

### Example 2: Geometry using the Origin

- Geometry **uses** the Origin’s planes and axes
- The Origin does **not contain** the geometry
- Geometry does **not belong** to the Origin

The Origin is a reference framework, not a parent part.

---

## Why the model tree can be misleading

The model tree shows **structure**, not **ownership**.

Just because something appears “under” another item does not mean:
- it will export together
- it will duplicate together
- it will be deleted together

Tree position ≠ dependency direction.

---

## What the Object Selection dialog is telling you

When copying or exporting, FreeCAD may say:

> “The selected objects contain other dependencies.”

What it really means:

> “Other objects rely on this one, or this one relies on others.”

The dialog exists to keep those relationships intact.

---

## Safe mental model

When working in FreeCAD, think in these terms:

- Bodies **contain** geometry
- Geometry **uses** references
- References **support**, but do not own
- Dependencies describe **support relationships**, not hierarchy

---

## Practical rules of thumb

- Don’t delete reference geometry casually
- Accept default dependency selections when copying
- Hide objects to control export, not dependencies
- If something breaks, a reference was removed — not the geometry

---

## One-sentence takeaway

> **Dependencies explain support relationships, not ownership or containment.**
