<!-- Manual Cover -->

<a href="images/NLA-Stride_LOGO2.png"><img src="images/NLA-Stride_LOGO2.png" width="250"></a>

# User Manual (English)

> This manual introduces the quick start, operation guide, and advanced techniques for the **NLA Stride** Blender add-on.

---

## 📘 Table of Contents

1. [Quick Start](#-quick-start)  
2. [Feature Overview](#-feature-overview)      
3. [Frequently Asked Questions](#-frequently-asked-questions) 
4. [Additional Tips](#-additional-tips) 
5. [Technical References](#-technical-references)

---

## 🚀 Quick Start

### 1. Add-on Installation

1. Install via Blender's official method ( **[General Installation Guide](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)** )

2. After installation, you can find **NLA Stride Tool** in the **3D Viewport → Sidebar → Animation** tab.

![alt text](images/img_1001.png)

---

### 2. Select Objects with Animation

<a href="images/img_1002.png">
  <img src="images/img_1002.png" width="650">
</a>

Select one or more objects that contain animation data.  
If you are using regular (non-NLA) animation, please refer to the "Bulk Push to NLA" section.

---

### 3. Add to List

![alt text](images/img_1003.png)

⚠️ **Important**: The add-on works based on the **list**, not the current scene selection.

---

### 4. NLA Align / Stride Operations

<a href="images/img_1004.png"><img src="images/img_1004.png" width="650"></a>

<a href="images/img_1005.png"><img src="images/img_1005.png" width="650"></a>

<a href="images/img_1006.png"><img src="images/img_1006.png" width="650"></a>

Above are demonstration images of NLA alignment and stride features.

---

### 5. Enjoy Your Animation!

<a href="images/DEMO_01.mp4">
  <img src="images/DEMO_01.gif" width="720">
</a>

<a href="images/DEMO_02.mp4">
  <img src="images/DEMO_02.gif" width="720">
</a>

<a href="images/DEM3_03.mp4">
  <img src="images/DEMO_03.gif" width="720">
</a>

<a href="images/DEM3_04.mp4">
  <img src="images/DEMO_04.gif" width="720">
</a>

Demo models courtesy of Taiwan **[SANSUI](https://www.sansuitw.com/)**

---

## 🧰 Feature Overview

#### 1. Data Source

![alt text](images/img_2001.png)

- **A** : Initialize and Add Selected  
  Clears the list first, then adds currently selected scene objects.

- **B** : Clear List  
  Removes all items from the list.

- **C** : Animation Source  
  Currently supports three types:  
    - Object Animation  
    - Shape Key Animation  
    - Material Animation

- **D** : Add / Remove Items from List  
  Add does **not** clear the list. Objects are appended in selection order. Already existing items are moved to the end.

- **E** : List Operations (dropdown menu)  
  See [1-1 List Operations](#1-1-list-operations) for details.

- **F** : Move selected list item **Up** / **Down**  
  Manually adjust order. After manual adjustment, the new order becomes the **"original order"**.

- **G** : Push Animations to NLA (dropdown menu)  
  Only affects objects in the current list.

- **PS.** See [3. List Icon Meanings](#3-list-icon-meanings)

#### 1-1. List Operations

![alt text](images/img_2002.png)

- **H** : Initialize and Add Selected  
  Clears list then adds currently selected scene objects.

- **I** : Four sorting options  
  The most important is **Restore Original Order**. The add-on remembers this order.

- **J** : Remove Scene Selected  
  Removes objects currently selected in the scene (different from 1-D).

#### 2. Strip Targeting

![alt text](images/img_2003.png)

- **K** : Three targeting modes  
  - **Single Strip**  
  - **Single Track** (all strips on one track move together, relative positions preserved)  
  - **All Tracks** (all tracks of the object move together)

- **L** : Targeting indices (Material mode only)  
  - **Slot** (calculated top to bottom in NLA Editor)  
  - **Track** (calculated bottom to top in NLA Editor)  
  - **Strip** (calculated left to right in NLA Editor)

  **!! Note**: If the target strip/track/slot is not correctly specified, stride will not work.

#### 3. NLA Align Tools (Reset / Initialize)

![alt text](images/img_2004.png)

- **M** : Five alignment references  
  - By Max Start Frame  
  - By Min Start Frame (most commonly used)  
  - By Max End Frame  
  - By Min End Frame  
  - By Current Time (most commonly used)

- **N** : Three alignment methods  
  - Align Start (left)  
  - Align Middle (center)  
  - Align End (right)

- **O** : Reset Scale  
  Resets scale of all NLA strips in the list to 1.0

#### 4. Simple Mode

![alt text](images/img_2005.png)

- **P** : Falloff Type  
  - Linear / Equal Spacing  
  - Ease In  
  - Ease Out  
  - Ease In Out

- **Q** : Offset Amount (in **frames**)  
  Total offset between the **first** and **last** item in the list (can be negative).

- **R** : Scale  
  Total scale difference between first and last item (0 ~ 1 range recommended).

- **S** : Execute Simple Stride  
  Applies the above values. Repeated clicks will accumulate the effect.

#### 5. Professional Mode

![alt text](images/img_2006.png)

**>> The core feature of this add-on – automatic stride & scale with simple settings <<**

- **T** : Start Falloff Type  
- **U** : Set Start Frame (overall animation start)  
- **V** : Start Offset Ratio  
- **W** : End Falloff Type  
- **X** : Set End Frame (overall animation end)  
- **Y** : End Offset Ratio  
- **Z** : Execute Professional Stride  
  (Does **not** accumulate when clicked multiple times)

---

## ❓ Frequently Asked Questions

#### 1. ⚠️ Attention: **Instanced Data** (Shared Data Blocks)

The add-on modifies **NLA strips** directly and **does not** automatically handle Blender's data instancing.

**What is instanced data?**

When multiple objects share the same data block (material, action, mesh, etc.), modifying one strip may affect all instances.

**✅ Solution: Make Data Single User**

1. Select the objects in 3D Viewport  
2. Go to **Object → Relations → Make Single User**  
3. Choose the data types you want to make unique  
4. After making data single-user, NLA Stride will work as expected.

![alt text](images/img_3001.png)

---

#### 2. ⚠️ Bulk Push Animations to NLA

The add-on mainly works with existing **NLA strips**. Regular (non-NLA) animations are not affected by stride.

**✅ Solution: Bulk Push to NLA**

Use the green arrow dropdown in the interface to convert and push animations from the **list** to NLA.

![alt text](images/img_3002.png)

---

## 📖 Additional Tips

#### 1. Alignment & Stride Strategy Tips

- Press **Alt + A** to deselect everything, then use **Select List Objects** to verify which objects are actually in the list.  
- **Order matters** a lot. Consider sorting by name or processing in batches.  
- When things get messy, use the **Align** tools to reset everything.  
- Focus on creating one **perfect motion cycle** — stride makes duplication & offset very easy.  
- If you animated **location** and want to keep new positions after duplicating, use **Ctrl + A → Apply Location** before pushing to NLA.

![alt text](images/img_4001.png)

#### 2. Falloff / Stride Explanation

- **Linear mode** (Simple):  
  <a href="images/img_4002.png"><img src="images/img_4002.png" width="650"></a>

- **Professional mode** allows independent control of **start** and **end** falloff:  
  <a href="images/img_4003.png"><img src="images/img_4003.png" width="650"></a>

  **Warning**: If start and end falloff types are different, very short or disappearing strips may occur.  
  <a href="images/img_4004.png"><img src="images/img_4004.png" width="650"></a>

#### 3. List Icon Meanings

![alt text](images/img_3003.gif)

- **A** : Data mode (Object / Shape Key / Material)  
- **B** : Current Action (non-NLA animation data)  
- **C** : Available NLA data

Icons change meaning depending on the selected **Animation Source** (A):

- ✔ : Has **matching** data for current mode  
- ・ : Has data, but **not** the current mode  
- ✕ : No data

---

## 🔧 Technical References

- [Blender NLA Official Manual](https://docs.blender.org/manual/en/latest/editors/nla/index.html)  
- [Blender Python API – NLA](https://docs.blender.org/api/current/bpy.ops.nla.html)

---

## 📘 Table of Contents

1. [Quick Start](#-quick-start)  
2. [Feature Overview](#-feature-overview)      
3. [Frequently Asked Questions](#-frequently-asked-questions) 
4. [Additional Tips](#-additional-tips) 
5. [Technical References](#-technical-references)

<!-- End of Manual -->