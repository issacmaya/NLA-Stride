<a href="images/NLA-Stride_LOGO2.png"><img src="images/NLA-Stride_LOGO2.png" width="250"></a>  

# User Manual (English)

> This manual introduces the features and tips for the NLA-Stride Blender Add-on, and provides answers to common known issues.

---

## 📘 Table of Contents

1. [Quick Start](#-quick-start)  
2. [Update Highlights](#-update-highlights)
3. [Features Overview](#-features-overview)      
4. [FAQ](#-faq) 
5. [Others](#-others) 
6. [Technical Reference](#-technical-reference)

---

## 🚀 Quick Start

### 1. Add-on Installation

1. Follow the official Blender installation steps ( **[General Installation Guide](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)** )

2. After installation, you can find the **NLA Stride Tool** in the Blender 3D Viewport under the **Sidebar → Animation** tab. 
<br>![alt text](images/img_1001.png)



---

### 2. Select Objects with Animation  
<a href="images/img_1002.png">
  <img src="images/img_1002.png" width="650">
</a>  

Select one or more objects containing animation data. If they contain default Actions instead of NLA Strips, please refer to the "Batch Push to NLA" section below.  

---

### 3. Add to List  
![alt text](images/img_1003.png)  

⚠️ Note: The add-on operates based on the list, regardless of the current selection in the viewport.  

---

### 4. NLA Alignment / Offset Operations  
<a href="images/img_1004.png"><img src="images/img_1004.png" width="650"></a>  
<a href="images/img_1005.png"><img src="images/img_1005.png" width="650"></a>  
<a href="images/img_1006.png"><img src="images/img_1006.png" width="650"></a>  

Above are demonstrations of the NLA Alignment and Offset features.  

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

Special thanks to the Taiwanese brand [SANSUI](https://www.sansuitw.com/?gad_source=1&gad_campaignid=23085773952&gbraid=0AAAAAoXC59ENhboAZDO-y0zK4yQpidtXM&gclid=CjwKCAiAybfLBhAjEiwAI0mBBscjnZOEYBBY127EypNMfnL1h_Vqm_HACczeJBOqMK-euDJFPb1iAxoC7rkQAvD_BwE) for providing the example models.  

---

## 🚀 Update Highlights

- **Added Professional Mode**: Supports independent Falloff control for both Head and Tail of strips.
- **Improved Selection Logic**: Now supports automatic detection of Material Slots.
- **Performance Optimization**: Significant speed increase when processing a large number of objects.
- **Multi-language Support**: Added support for English, German, French, Spanish, Dutch, Japanese, and Korean.

---

## 🧰 Features Overview

#### 1. Animation Source 
![alt text](images/img_2001.png)  

- A : Initialize and Add Selected  
  Clears the list first, then adds the objects currently selected in the scene.  
<br>

- B : Clear List  
  Clears all data in the list.  
<br>

- C : Animation Source  
  Currently supports three types: Object Animation / Shape Key Animation / Material Animation.  
<br>

- D : Add / Remove List Items  
  Adding will **NOT** clear the previous list; objects are added sequentially based on **selection order**. If an object is already in the list, it will be moved to the end. This logic differs from A. The removal tool is also different from 1-J.  
<br>

- E : List Operations (Dropdown Menu)  
  See "1-1 List Operations" for details.  
<br>

- F : Move Item Up / Down  
  Manually adjust the order. Once adjusted, this result is defined as the **"Original Order"**.  
<br>

- G : Push to NLA (Dropdown Menu)  
  Converts the current Action into NLA strips, only for objects in the list.  
<br>

- PS. [3. List Icon Meanings](#3-list-icon-meanings)  

#### 1-1. List Operations
![alt text](images/img_2002.png)  

- H : Initialize and Add Selected  
  Clears the list first, then adds the objects currently selected in the scene.  
<br>

- I : Four Sorting Options  
  The most important is **Restore Original Order**, as this add-on records that sequence. The other three are automatic sorting methods.  
<br>

- J : Remove Scene Selection  
  Removes objects from the list based on the current selection in the viewport. This is different from the 1-D removal tool.  

#### 2. Data Positioning
![alt text](images/img_2003.png)  

- K : Three Strip Modes  
  - Single Strip : Focuses on a single specified strip.  
  - Single Track : Treats all strips within that track as a group (relative positions remain unchanged).  
  - All Tracks : Equivalent to changing all tracks of the object simultaneously (relative positions remain unchanged).  
<br>

- L : Three Positioning Points  
  - Which Slot : (Material Mode only) Calculated from **top to bottom** in the UI.  
  - Which Track : Calculated from **bottom to top** in the NLA Editor.  
  - Which Strip : Calculated from **left to right** in the NLA Editor.  
<br>

  **!! Note: If the target positioning is incorrect, NLA Stride will not be able to perform the offset.** #### 3. NLA Align Tools (Initial Values)
![alt text](images/img_2004.png)  

- M : Five Alignment Targets  
  - Align Max Start Frame : Aligns to the **start** point of the strip that starts **latest** in the list.  
  - Align Min Start Frame : Aligns to the **start** point of the strip that starts **earliest** (Commonly used).  
  - Align Max End Frame : Aligns to the **end** point of the strip that ends **latest** (Commonly used).  
  - Align Min End Frame : Aligns to the **end** point of the strip that ends **earliest**.  
  - Align Current Time : Aligns to the current playhead position (Most common).  
<br>

- N : Three Alignment Modes  
  - Align Start : The left side of the strip aligns with the target. Usually used for **Start** alignment.  
  - Align Middle : The center of the strip aligns with the target.  
  - Align End : The right side of the strip aligns with the target. Usually used for **End** alignment.  
<br>

- O : Reset Scale  
  Resets the scale value of all NLA strips in the list to 1.0.  


#### 4. Simple Mode
![alt text](images/img_2005.png)  

- P : Falloff Mode [(Detailed Description)](#2-offset-explanation)  
  - Four calculation formulas: 1. Linear / 2. Ease In / 3. Ease Out / 4. Ease In Out.  
<br>

- Q : Offset Amount (Unit: **Frames**)  
  - This is not the spacing between single strips, but the total difference from the first object to the last object in the list (negative values allowed).  
<br>

- R : Scale  
  - Not incremental scaling, but the scale difference between the first and last object in the list (0 ~ 1).  
<br>

- S : Run Simple NLA Stride (Repeated clicking will accumulate calculations).  
<br>

#### 5. Professional Mode
![alt text](images/img_2006.png)  
  **>> The core of this add-on. Through simple settings, it automatically adjusts strip offset and scaling <<** - T : Falloff Mode [(Detailed Description)](#2-offset-explanation)  
  - Four calculation formulas: 1. Linear / 2. Ease In / 3. Ease Out / 4. Ease In Out.  
<br>

- U : Set Start Frame  
  - Sets the **start** time for the entire animation sequence of all objects in the list.  
<br>

- V : Offset Ratio (Head)  
  - Multiplied by the Falloff Mode (T) to calculate the offset value used to automatically position all strip start points.  
<br>

- W : Falloff Mode [(Detailed Description)](#2-offset-explanation)  
  - Four calculation formulas: 1. Linear / 2. Ease In / 3. Ease Out / 4. Ease In Out.  
<br>

- X : Set End Frame  
  - Sets the **end** time for the entire animation sequence of all objects in the list.  
<br>

- Y : Offset Ratio (Tail)  
  - The offset ratio for the end points of the strips.  
<br>

- Z : Run Professional NLA Stride (Repeated clicking will **NOT** accumulate calculations).  
<br>


---

## ❓ FAQ


#### 1. ⚠️ Beware of "Instanced Data"

This add-on primarily processes the offset and alignment of NLA strips themselves; it does **NOT** automatically manage "Instanced Data" relationships within Blender.  

#### What is Instanced Data?

When **multiple objects share the same data**, those data blocks are "instanced."  

- For example:  
  - Two objects sharing the same material.  
  - Sharing the same Action, Mesh, or other data blocks.  

In the NLA Editor, these might look like two independent strips, but in reality, they both **point to the same underlying data block**.
This results in a situation where, when using **NLA Stride for offset**, the add-on appears to move different strips, but is actually modifying the same piece of data, thus **failing to achieve the expected offset effect**.


#### ✅ Solution (Refer to the image steps)

> 💡 **Core Logic: Make data independent before performing the offset.** Steps (as shown in the image):  

1. Select the objects to be processed in the 3D Viewport.  
2. Go to **Object → Relations**.  
3. Click **Make Single User**.  
4. Select the data types that need to be independent (e.g., Object Animation).  
5. Once the data is independent, use **NLA Stride** to perform the offset.  



![alt text](images/img_3001.png)  

> When data is independent, each object will have its own exclusive NLA data.
> NLA Stride can then **properly and predictably help you offset the NLA strips**.  

---


#### 2. ⚠️ Batch NLA Creation

The target of this add-on is NLA strips. If animation data has not yet been "Pushed Down" to become NLA strips, it will not be affected.  

#### ✅ Solution: Push to NLA Tool

The add-on provides a batch conversion tool (marked by the green arrow below). Note that the target is objects **in the list**, not the viewport selection.  

![alt text](images/img_3002.png)  

---



## 📖 Others


#### 1. Alignment and Offset Strategy Tips

- You can first press **Alt A** in the 3D Viewport to deselect all, then use the **Select List Objects** feature to accurately confirm who is in your list.  
<br>

- **Order** is crucial as it directly affects the animation state after offset. Use naming conventions to determine order whenever possible. For large numbers of objects, please process in batches.  
<br>

- If things get messy, use the alignment tools to unify everyone first.  
<br>

- Since animation offset becomes very easy, focus your energy on creating a **perfect dynamic feel**.  
<br>

- If your dynamic design involves **Location**, be careful when duplicating; when playing the animation, it might jump back to the same position because location information is hardcoded into the NLA. In this case, you can use the **Ctrl A** function to apply transformations and write the new position into the **Delta Transforms** data.  
<br>![alt text](images/img_4001.png)  

---

#### 2. Offset Explanation
- Linear Falloff Mode:  
  - Simple Mode:   
  <a href="images/img_4002.png"><img src="images/img_4002.png" width="650"></a>  
  Simple Mode calculates based on the original state (far left in the image). As shown, with Offset 100 and Scale 1.5, the start point and length (end point) of the last strip will always be the same; however, you can see that due to different Falloff Modes, the start points of other strips vary, creating a different sense of offset.  

    ---
  - Professional Mode:    
  <a href="images/img_4003.png"><img src="images/img_4003.png" width="650"></a>  
  The only difference from Simple Mode is that Professional Mode allows independent control of the "Head" and "Tail," providing two separately adjustable Falloff Modes.  
  
    ---
  - **Note**:   
  <a href="images/img_4004.png"><img src="images/img_4004.png" width="650"></a>  
  Be aware that if the Head and Tail Falloff Modes are **different**, you need to check if the animation strips encounter issues (becoming too short or disappearing).  

---

#### 3. List Icon Meanings

![alt text](images/img_3003.gif)  

Icon A : Data Mode  
Icon B : Action represents standard animation data (non-NLA).  
Icon C : Existing NLA data.  

- The meaning of icons B and C changes based on the data mode in column A:  
  - ✔ : Contains the **correct** data matching the mode in column A.  
  - ・ : Contains data, but **NOT** of the type configured in column A.  
  - ✕ : No data found.  

Data in Viewport:  
| Item | Object Animation | Material Animation | Shape Key Animation |
|------|------|------|--------|
| **NLA Strip** | cube.049 | cube.050 | cube.051 | 
| **Active Action** | cube.027 | cube.037 | cube.038 |  

- Others: cube.000 (has all three NLA types) / cube.039 (no animation data).  

---

## 🔧 Technical Reference

  [Blender NLA Official Manual](https://docs.blender.org/manual/en/latest/editors/nla/index.html)  

  [Blender API Official Manual](https://docs.blender.org/api/current/bpy.ops.nla.html)  

  


## 📘 Table of Contents

1. [Quick Start](#-quick-start)  
2. [Update Highlights](#-update-highlights)
3. [Features Overview](#-features-overview)      
4. [FAQ](#-faq) 
5. [Others](#-others) 
6. [Technical Reference](#-technical-reference)