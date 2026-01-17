# Origin vs Geometry (How to Think About It)

This page explains the difference between **Origins**, **reference geometry**, and **actual model geometry** in FreeCAD,
using simple, non-technical language.

The goal is to help you understand *what things are*, not how FreeCAD internally tracks dependencies.

---

## The most important idea

> **Origins provide references. Bodies create geometry.**

If you understand that sentence, most FreeCAD confusion disappears.

---

## What the Origin is

Each Body in FreeCAD has an **Origin**.

The Origin:
- defines where **zero** is
- provides **X, Y, Z axes**
- provides **XY, XZ, YZ planes**
- never creates printable geometry

Think of the Origin as a **coordinate system** or **reference framework**.

You build *relative to* it, but it never becomes part of your part.

---

## What Origin children really are

Under an Origin you see:
- axes
- planes

These are **tools**, not parts.

They exist so you can:
- attach sketches
- align features
- place geometry accurately

They are shown as “children” only because they belong to the Origin as references,
not because they are pieces of the model.

---

## What geometry is

Geometry is anything that:
- creates a visible solid
- can be exported
- can be printed

Examples:
- Pad
- Pocket
- Revolve
- Torus
- Fillet

Geometry lives **inside a Body**, not inside the Origin.

---

## The relationship between Origin and geometry

A simple way to think about it:

- The Origin does **not contain** geometry
- Geometry does **not belong to** the Origin
- Geometry is **defined relative to** the Origin

In other words:

> The Origin helps place geometry, but does not own it.

---

## A helpful analogy

Think of the Origin like graph paper taped to your desk.

- You draw shapes *on* the grid
- The grid helps you stay aligned
- The drawing is not part of the grid

FreeCAD works the same way.

---

## Why this matters

Understanding this helps you avoid common mistakes:
- trying to “move” the Origin instead of the geometry
- assuming deleting an Origin will delete a part
- thinking planes are solid objects

Once you separate **references** from **geometry**, the model tree becomes much easier to read.

---

## One-sentence takeaway

> **Origins define space. Bodies create parts. Geometry may use references without being their child.**
