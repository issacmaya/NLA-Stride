# NLA_stride

**NLA_stride** is a Blender add-on designed to batch align, offset, and manage
NLA strips in a non-destructive workflow.

- **NLA**: Refers to Blender’s Non-Linear Animation editor.
- **Stride**: Inspired by Cinema 4D’s stride concept, where animation timing
  can be offset to create staggered motion.

The core value of this add-on is: **efficient timing control across multiple objects, tracks, and animation types**.

---

## Compatibility & Installation

Since Blender 4.0, a new Extensions framework has been introduced. The installation packages are divided into two types based on your version:

| File Name | Supported Blender Version | Description |
| :--- | :--- | :--- |
| **`NLA_stride_v1.0.0.zip`** | **3.0 ~ 5.x+** | Legacy add-on format with wide compatibility. |
| **`nla_stride-1.0.0.zip`** | **4.0 and above** | New 4.0+ packaging specification (Recommended). |

**Installation Steps:**
1. Download the corresponding ZIP file.
2. Open Blender, go to `Edit → Preferences → Add-ons` 
   or for 4.0+: `Edit → Preferences → Extensions`.
3. Go to the top-right dropdown menu, click `Install from Disk...` and select the corresponding ZIP file from the table.
4. Enable **NLA stride**.

---

## Core Features

### 1. Selection Order Aware
* Records object selection order and applies it directly to the NLA offset logic.

### 2. Batch Push to NLA
* Push keyframes from multiple objects into NLA strips with a single click.

### 3. Support for External Export/Import Lists
* Complex projects can utilize export lists to record the current selection order.

### 4. Align & Reset Tools
* **5 Alignment targets** and **3 Alignment reference modes**.
* One-click scale reset for NLA strips.

### 5. Stride Offset Modes
* **Simple Stride Mode**: Quickly set a fixed frame offset.
* **Professional Stride Mode**: Precisely control the start and end time of the overall animation.

### 6. Multiple Animation Types Supported
* Object animation
* Shape Key animation
* Material animation

### 7. Falloff Support
* Supports Linear / Ease In / Ease Out / Ease In-Out to give staggered offsets more rhythm.

---

## Three Operation Modes

1.  **Object Mode**: All strips move together (Material mode allows specifying offset targets).
2.  **Single Track Mode**: All strips on the same track move together as a group.
3.  **Single Strip Mode**: Supports overlap detection when moving multiple selected strips.

---

## When to Use

* **Motion Graphics**: Quickly transform simple base animations into complex staggered motion.
* **Multi-object Animation Management**: Scenarios requiring strict timing control, such as product explosions or architectural sequences.
* **Non-destructive Editing**: Adjust timing using NLA tracks without modifying original Actions.

---

## Important Notes & Limitations

* **Data Sharing Issues**:
    Shape Key and Material animations are "Data-based." If multiple objects share the same material or data (Instanced Data), adjustments may lead to unexpected results.
* **Recommended Practice**:
    Before using this add-on, it is recommended to execute Blender’s built-in:
    `Object -> Relations -> Make Single User -> Materials / Object Data`
* **Advanced Workflow**:
    If you need to adjust data types not yet supported, it is suggested to drive that data via **Custom Properties**, then push those properties to the NLA to be managed by this add-on.

---

## Language Note

The author is a native **Traditional Chinese (zh-TW)** speaker. If there are any inaccuracies in the English wording, feedback via Issues or Pull Requests is welcome.
