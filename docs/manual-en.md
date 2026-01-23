<a href="images/NLA-Stride_LOGO2.png"><img src="images/NLA-Stride_LOGO2.png" width="250"></a>  

# User Manual (English)

> This manual introduces the Quick Start, Operation Guide, and Advanced Tips for the NLA-Stride Blender addon.

---

## 📘 Table of Contents

1. [Quick Start](#-quick-start)  
2. [Feature Overview](#-feature-overview)      
3. [FAQ](#-faq) 
4. [Others](#-others) 
5. [Technical Reference](#-technical-reference)

---

## 🚀 Quick Start

### 1. Addon Installation

1. Follow the official Blender installation steps (**[General Installation Guide](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)**).

2. After installation, you can find the **NLA Stride Tool** in the Blender 3D Viewport under **Sidebar (N) → Animation** tab.


![alt text](images/img_1001.png)



---

### 2. Select Objects with Animation

<a href="images/img_1002.png">
  <img src="images/img_1002.png" width="650">
</a>  

Select one or more objects containing animation data. If they contain standard Actions instead of NLA strips, please refer to the "Batch Push to NLA" section.

---

### 3. Add to List

![alt text](images/img_1003.png)

⚠️ Note: The addon operates based on the list, regardless of the current viewport selection.

---

### 4. NLA Alignment / Offset Operations


<a href="images/img_1004.png"><img src="images/img_1004.png" width="650"></a>  

<a href="images/img_1005.png"><img src="images/img_1005.png" width="650"></a>  

<a href="images/img_1006.png"><img src="images/img_1006.png" width="650"></a>  


Above are demonstrations of NLA alignment and offset functions.

---

### 5. Enjoy the Animation Magic

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

Special thanks to the Taiwanese brand [SANSUI](https://www.sansuitw.com/?gad_source=1&gad_campaignid=23085773952&gbraid=0AAAAAoXC59ENhboAZDO-y0zK4yQpidtXM&gclid=CjwKCAiAybfLBhAjEiwAI0mBBscjnZOEYBBY127EypNMfnL1h_Vqm_HACczeJBOqMK-euDJFPb1iAxoC7rkQAvD_BwE) for providing the model for this example.

---

## 🧰 Feature Overview

#### 1. Data Source 

![alt text](images/img_2001.png)

- A : Initialize and Add Selected
  
  Clears the list first, then adds currently selected objects from the scene.
<br>

- B : Clear List
  
  Clears all data within the list.
  <br>

- C : Animation Source
  
  Currently supports three types:
    -  Object Animation 
    -  Shape Key Animation
    -  Material Animation
<br>

- D : Add / Remove Items from List
  
  Adding **will not** clear existing items; objects are added to the end in the **order of selection**. If an object already in the list is selected, it will be moved to the end. The addition logic differs from 'A'. Removal also differs from '1-J'.
<br>

- E : List Operations (Dropdown Menu)
  
  See details in [1-1 List Operations](#1-1-list-operations).
<br>

- F : Move Up / Down in List
  
  Manually adjust the order. Once manual adjustments are made, this result is defined as the **"Original Order"**.
<br>

- G : Push to NLA (Dropdown Menu)
  
  Converts active actions to NLA strips for list objects only.
<br>
  
  
-  PS. [3. List Icon Meanings](#3-list-icon-meanings)

#### 1-1. List Operations

![alt text](images/img_2002.png)

- H : Initialize and Add Selected
 
  Clears the list first, then adds currently selected objects from the scene.
<br>

- I : Four Sorting Options
  
  The most important is **Restore Original Order**. This addon records this sequence. The other three are automated sorts.
<br>

- J : Remove Scene Selected
 
  Removes objects from the list based on the current viewport selection. This differs from the '1-D' removal tool.

#### 2. Data Positioning

![alt text](images/img_2003.png)

- K : Three Strip Modes
  - Single Strip: Targets only one specific strip.
  - Single Track: Treats all strips on a single track as one group (relative positions remain unchanged).
  - All Tracks: Equivalent to changing all tracks of the object simultaneously (relative positions remain unchanged).
<br>

- L : Three Positioning Points
  - Which Slot: (Material Mode only) Calculated **top-to-bottom** in the UI.
  - Which Track: Calculated **bottom-to-top** in the NLA editor.
  - Which Strip: Calculated **left-to-right** in the NLA editor.
<br>

  **!! Note: If the target is not correctly positioned, NLA Stride cannot perform offsets.**

#### 3. NLA Align Tools (Initialization Values)
![alt text](images/img_2004.png)

- M : Five Align Targets
  - By Max Start Frame: Aligns to the **start** of the **latest** starting strip in the list.
  - By Min Start Frame: Aligns to the **start** of the **earliest** starting strip (Commonly used).
  - By Max End Frame: Aligns to the **end** of the **latest** ending strip (Commonly used).
  - By Min End Frame: Aligns to the **end** of the **earliest** ending strip.
  - By Current Time: Aligns to the current playhead position (Most common).
<br>

- N : Three Align Modes
  - Align Start: Aligns the left side of the strip to the target. Commonly used for **Starting** alignment.
  - Align Middle: Aligns the center of the strip to the target.
  - Align End: Aligns the right side of the strip to the target. Commonly used for **Ending** alignment.
<br>

- O : Reset Scale
  
  Resets the scale value of all NLA strips in the list to 1.0.


#### 4. Simple Mode

![alt text](images/img_2005.png)

- P : Falloff Mode [(Detailed Description)](#2-offset-description)
  
  - Four calculation formulas: 1. Linear / 2. Ease In / 3. Ease Out / 4. Ease In Out.
<br>

- Q : Offset Amount (Unit: **Frames**)
  
  - This is not the gap between individual strips, but the total difference between the first and last object in the list (negative values are allowed).
<br>

- R : Scale
  
  - Not an incremental scale, but the scale difference between the first and last object in the list (0 ~ 1).
<br>

- S : Execute Simple NLA Stride (Repeated clicking will accumulate calculations).
<br>

#### 5. Professional Mode
![alt text](images/img_2006.png)
  **>> The core of this addon. With simple settings, strip offsets and scales are adjusted automatically <<**

- T : Falloff Mode [(Detailed Description)](#2-offset-description)
  
  - Four calculation formulas: 1. Linear / 2. Ease In / 3. Ease Out / 4. Ease In Out.
<br>

- U : Set Start Frame
  
  - Sets the **Start** time for the entire animation sequence for all list objects.
<br>

- V : Offset Ratio (Start)
  
  - Multiplied by the Falloff Mode (T) to calculate the offset, used for automated positioning of all strip start points.
<br>

- W : Falloff Mode [(Detailed Description)](#2-offset-description)
  
  - Four calculation formulas: 1. Linear / 2. Ease In / 3. Ease Out / 4. Ease In Out.
<br>

- X : Set End Frame
  
  - Sets the **End** time for the entire animation sequence for all list objects.
<br>

- Y : Offset Ratio (End)
  
  - The offset ratio for the ending points of the strips.
<br>

- Z : Execute Professional NLA Stride (Repeated clicking **will not** accumulate calculations).
<br>


---

## ❓ FAQ


#### 1. ⚠️ Be mindful of "Instanced Data"

This addon primarily processes the offset and alignment of NLA Strips themselves; it **does not** automatically handle Blender's "Instanced Data" relationships.

#### What is Instanced Data?

When **multiple objects share the same data**, those data blocks are "Instanced."

- For example:  
  - Two objects sharing the same Material.
  - Sharing the same Action, Mesh, or other data blocks.

In the NLA Editor, they may look like two independent strips, but they actually **point to the same underlying data**.
As a result, when using **NLA Stride to offset**, the addon appears to move different strips, but in reality, it is modifying the same data block, thus **failing to achieve the expected offset effect**.


#### ✅ Solution (Follow the screenshot below)

> 💡 **Key approach: Make data independent before offsetting.**

Steps (as shown in the image):

1. Select the objects to be processed in the 3D Viewport.
2. Open **Object → Relations**.
3. Click **Make Single User**.
4. Select the data types that need to be independent (e.g., Object Animation).
5. Once data is independent, use **NLA Stride** for offsetting.



![alt text](images/img_3001.png)

> Once data is independent, each object will have its own unique NLA data.
> NLA Stride will then be able to **offset NLA strips normally and predictably**.
---


#### 2. ⚠️ Batch Creating NLA

This addon focuses on NLA Strips. Animation data that hasn't been "pushed down" into NLA strips will not be affected.

#### ✅ Solution: Push to NLA Tools

The addon provides a batch conversion tool (indicated by green arrows below). Note that this applies to objects **in the list**, not the 3D viewport selection.

![alt text](images/img_3002.png)

---



## 📖 Others


#### 1. Alignment and Offset Strategy Tips

- You can press **Alt + A** in the 3D Viewport to deselect everything, then use the **Select List Objects** function to verify exactly which objects are in your list.
<br>
- Because **Order** is crucial, it directly affects the animation state after offsetting. If possible, use naming conventions to determine order. If there are many objects, process them in batches.
<br>
- When things get messy, use the Alignment Tools to unify them first.
<br>
- Since animation offsetting becomes very easy, focus your energy on creating one **perfect movement**.
<br>
- If your movement design includes **Location** keys, note that when duplicating, the animation might jump back to the original coordinates. You can use **Ctrl + A** to apply transformations so the new coordinates are written into the delta transforms.
![alt text](images/img_4001.png)
---

#### 2. Offset Description
- Linear Stacking Mode:
  - Simple Mode:  
  <a href="images/img_4002.png"><img src="images/img_4002.png" width="650"></a>  
  Simple mode calculates based on the original state (leftmost in image). If Offset is set to 100 and Scale to 1.5, the start and end points of the last strip will match the target exactly; however, different falloff modes will change the distribution of the intermediate strips.

    ---

  - Professional Mode:
  The difference is that Professional Mode allows you to control both the Start and End. There are two falloff settings.
  <a href="images/img_4003.png"><img src="images/img_4003.png" width="650"></a>  
  Note: If the Start and End falloff modes are **different**, be careful as animation strips might become too short or disappear.
  <a href="images/img_4004.png"><img src="images/img_4004.png" width="650"></a>  

---

#### 3. List Icon Meanings

![alt text](images/img_3003.gif)

Icon A: Data Mode
Icon B: Action represents standard animation data (non-NLA).
Icon C: Available NLA data.

- The meaning of icons in B and C changes based on the Data Mode in column A:
  - ✔ : Contains the **correct** data matching the mode in column A.
  - ・: Contains data, but **not** of the type set in column A.
  - ✕ : No data found.

Data in the viewport:
| Item | Object Animation | Material Animation | Shape Key Animation |
|------|------|------|--------|
| **NLA Strip** | cube.049 | cube.050 | cube.051 | 
| **Active Action** | cube.027 | cube.037 | cube.038 |

- Others: cube.000 (Has all 3 types of NLA) / cube.039 (No animation data at all).

---

## 🔧 Technical Reference

  [Blender NLA Official Manual](https://docs.blender.org/manual/en/latest/editors/nla/index.html)

  [Blender API Official Manual](https://docs.blender.org/api/current/bpy.ops.nla.html)

  


## 📘 Table of Contents

1. [Quick Start](#-quick-start)  
2. [Feature Overview](#-feature-overview)      
3. [FAQ](#-faq) 
4. [Others](#-others) 
5. [Technical Reference](#-technical-reference)