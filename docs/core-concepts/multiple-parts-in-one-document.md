# Creating Multiple Parts in a Document (FreeCAD)

This page explains how to manage **multiple variations of a part** inside a single FreeCAD document using:
- clear naming
- color-coding
- duplication
- safe export practices

This approach is ideal for iterative design (example: O-ring sizes, gasket thickness tests).

---

## Core concepts (terminology refresher)

- **Document** = the FreeCAD project file (`.FCStd`)
- **Body** = one solid printable part
- **Part** = a container that can hold multiple bodies

FreeCAD does **not** use literal “tabs.”  
Instead, **multiple Bodies inside one Document** serve the same purpose.

---

## Recommended structure (best practice)

**One Document → Multiple Bodies**

- Keep all variants in a single document
- Create **one Body per variation**
- Hide/show bodies as needed

Example:

Document  
└─ Part: O-Ring Variants  
   ├─ Body: O-Ring_Round_2p5mm  
   ├─ Body: O-Ring_Round_3p0mm  
   └─ Body: O-Ring_Round_3p2mm  

---

## Naming convention (clear & sortable)

Rename the **Body**, not individual features.

Use a sortable format like:

- `O-Ring_Round_2p5mm`
- `O-Ring_Round_3p0mm`
- `O-Ring_Round_3p2mm`

Square gasket examples:
- `Gasket_Square_2p3mmH`
- `Gasket_Square_2p1mmH`

---

## Color-coding bodies (highly recommended)

Color makes variants instantly identifiable.

### How to set color
1. Select the **Body** in the Model tree
2. Right-click → **Appearance**
3. Set **Shape Color** (optional transparency)

---

## Fastest way to duplicate a Body (safe method)

1. Select the Body you want to copy
2. **Ctrl+C**
3. **Ctrl+V**
4. Rename the new body immediately
5. Change only the required parameter

---

## Export only the correct Body (avoid mistakes)

1. Hide all other bodies
2. Ensure only **one** body is visible
3. Select the visible body
4. File → Export → **STL / 3MF**

---

## Rules of thumb

- One Document = one project
- One Body = one printable part
- Variations = multiple bodies
- Always rename bodies
- Always color-code variants
- Export only what’s visible

---

## Key takeaway

**Multiple bodies in one document** is the cleanest, safest way to manage design variations in FreeCAD.
