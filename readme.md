# NLA_stride

**NLA_stride** is a Blender add-on designed to batch align, offset, and manage
NLA strips in a non-destructive workflow.

- **NLA** refers to Blender’s Non-Linear Animation editor  
- **Stride** is inspired by Cinema 4D’s stride concept, where animation timing
  can be offset to create staggered motion

This add-on focuses on **efficient timing control across multiple objects,
tracks, and animation types**.

---

## Features

- **Selection Order Aware**
  - Records object selection order and applies it directly to NLA offset logic

- **Batch Push to NLA**
  - Push keyframes from multiple objects into NLA strips at once

- **Align & Reset Tools**
  - 5 alignment targets
  - 3 alignment reference modes
  - One-click scale reset for NLA strips

- **Stride Offset Modes**
  - Simple Stride Mode (quick offset)
  - Professional Stride Mode (precise start / end control)

- **Multiple Animation Sources**
  - Object animation
  - Shape Key animation
  - Material animation

- **Falloff Support**
  - Linear / Ease In / Ease Out / Ease In-Out

- **Three Operation Modes**
  1. **Object Mode**
     - All strips move together  
     - (Material mode allows specifying offset targets)
  2. **Single Track Mode**
     - All strips on one track move together
  3. **Single Strip Mode**
     - Overlap detection when moving multiple strips

---

## When to Use

- **Motion Graphics / Procedural Visual Effects**
  - Create complex staggered motion from simple base animations

- **Multi-object Animation Management**
  - Product explosion animations
  - Architectural construction sequences
  - Any scenario requiring consistent timing adjustments

- **Non-destructive Animation Editing**
  - Using NLA instead of modifying original actions directly

---

## Installation

1. Download the add-on as a ZIP file
2. Open Blender  
   `Edit → Preferences → Add-ons → Install`
3. Select the ZIP file
4. Enable **NLA_stride**

(Standard Blender add-on installation workflow)

---

## Basic Usage

1. Select animated objects in the scene  
   Click **「Initialize and Add Selected」**
2. Choose the target strip mode
3. Select one of the following:
   - Simple Stride Mode
   - Professional Stride Mode
4. Press **Play** and enjoy the staggered NLA result

---

## Supported Animation Types & Limitations

### Supported NLA Types

- Object animation
- Shape Key animation
- Material animation

> Blender supports many internal animation data types.
> Currently, only the three listed above are supported.

**Advanced workaround**  
If you need to animate unsupported data:
- Add custom properties to objects
- Drive them with expressions
- Push them into NLA  
(Custom properties can be recorded by NLA strips)

---

### Important Notes

- Shape Key and Material animations are **data-based**
- If multiple objects share the same data (instanced data),
  results may not behave as expected

Examples:
- Multiple objects using the same material
- Shape keys shared across instances

**Recommendation**  
Use Blender’s built-in:
to ensure predictable results.

---

## Compatibility

- **Blender**: 5.0 and above
- **Python**: Bundled with Blender

---

## Language Note

The author is a native **Traditional Chinese (zh-TW)** speaker.  
Some English wording may sound non-native.

Feedback, issues, and pull requests are welcome.
