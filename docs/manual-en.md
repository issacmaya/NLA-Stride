<a href="images/NLA-Stride_LOGO2.png"><img src="images/NLA-Stride_LOGO2.png" width="250"></a>  

# User Manual

> This manual introduces the functions and techniques of the NLA-Stride Blender add-on, as well as answers to some common known issues.

---

## 📘 Contents

1. [Quick Start](#Quick_Start)  
2. [Version Updates](#Version_Updates)
3. [Feature Overview](#Feature_Overview)      
4. [FAQ](#FAQ) 
5. [Others](#Others) 
6. [Technical Reference](#Technical_Reference)

---

## 🚀 Quick Start
<a id="Quick_Start"></a>

### 1. Add-on Installation

1. Follow the official Blender installation steps ( **[General Installation Guide](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)** )

2. After installation, you can find the **NLA Stride Tool** in the Blender 3D Viewport under the **Sidebar → Animation** tab. 
<br>![alt text](images/img_1001.png)



---

### 2. Select Objects with Animation  
<a href="images/img_1002.png">
  <img src="images/img_1002.png" width="650">
</a>  

Select one or more objects containing animation data. If using standard animations instead of NLA animations, please refer to the "Batch Push to NLA" instructions.

---

### 3. Add to List

![alt text](images/img_1003.png)

⚠️ Note: The add-on operates based on the list, independent of real-time object selection in the viewport.

---

### 4. NLA Alignment / Offset Operations


<a href="images/img_1004.png"><img src="images/img_1004.png" width="650"></a>  

<a href="images/img_1005.png"><img src="images/img_1005.png" width="650"></a>  

<a href="images/img_1006.png"><img src="images/img_1006.png" width="650"></a>  


The above demonstrations show the NLA alignment and offset functions.

---

### 5. Enjoy Animation Magic

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
## 🌟 Version Updates
<a id="Version_Updates"></a>
  
#### v1.0.0 Key Updates
- List Export / Import / Append  
  ![alt text](images/v100_001.png)  
  1. Three new functions added to List Operations.
  2. Export and Import use *.json files.
  3. "Append" adds items to the end of the list.
  4. In case of duplicate names, the existing entry takes priority.
#### v0.9.8 Key Updates  
- Initial public release  
---
## 🧰 Feature Overview
<a id="Feature_Overview"></a>
 

#### 1. Animation Source 

![alt text](images/img_2001.png)

- A : Initialize and Add Selected    
  Clears the current list and adds objects currently selected in the Scene.  
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
- D : Add / Remove Objects in List  
  Adding **will not** clear the list; objects are added to the end **based on selection order**. Existing objects will be moved to the end. This differs from method A. Removal also differs from 1-J.  
  <br>

- E : List Operations (Dropdown Menu)  
  See [1-1 List Operations](#List_Functions) for details.
  <br>

- F : Move Selected Item Up / Down  
  Manually adjust order. Once adjusted, this becomes the **"Cached Original Order"**.
  <br>

- G : Push to NLA (Dropdown Menu)  
  Converts only the objects in the list to NLA strips.
  <br>  
  
-  PS. [3. List Icon Meanings](#List_Icon_Meanings)

#### 1-1. List Operations
<a id="List_Functions"></a>

![alt text](images/img_2002.png)

- H : Initialize and Add Selected   
  Clears list data and adds objects selected in the Scene.
  <br>

- I : Four Sorting States    
  The most important is the **Original Order** recorded by the add-on; the others are temporary sort states.
  <br>

- J : Remove Scene Selected   
  Removes objects currently selected in the 3D Scene from the list (different from 1-D).
  <br>

#### 2. Specify Offset Strips

![alt text](images/img_2003.png)

- K : Three Strip Modes  
  - Single Strip : Affects only a specific strip.
  - Single Track : Treats all strips on a track as a single unit (relative positions remain).
  - All Tracks : All tracks of the object change together (relative positions remain).
  <br>

- L : Three Locators  
  - Which Slot : For Material Mode only, calculated **top to bottom** in the NLA UI.
  - Which Track : Calculated **bottom to top** in the NLA UI.
  - Which Strip : Calculated **left to right** in the NLA UI.
  <br>

  **!! Note: If the target is not correctly specified, NLA offset cannot be executed.**

#### 3. NLA Align Tools (Initialization Values)
![alt text](images/img_2004.png)

- M : Five Align Modes  
  - By Max Start Frame : Based on the **latest** start point of strips in the list.
  - By Min Start Frame : Based on the **earliest** start point of strips in the list (Common).
  - By Max End Frame : Based on the **latest** end point of strips in the list (Common).
  - By Min End Frame : Based on the **earliest** end point of strips in the list.
  - By Current Time : Based on the current playhead position (Most common).
  <br>

- N : Three Alignment Methods  
  - Align Start : Align left side to target (common for start points).
  - Align Middle : Align center to target.
  - Align End : Align right side to target (common for end points).
  <br>

- O : Reset Scale  
  Resets the scale of all NLA strips in the list to 1.
  <br>


#### 4. Simple Mode

![alt text](images/img_2005.png)  
- P : Simple Mode Falloff [(Detailed Description)](#Stride_Description)  
  Four calculation formulas: 1. Linear / 2. Ease In / 3. Ease Out / 4. Ease In Out.
  <br>

- Q : Offset Amount (Unit: **Frames**)  
  Total difference between the first and last object in the list (supports negative values).
  <br>

- R : Scale  
  Scale difference between the first and last object in the list (0 ~ 1).
  <br>

- S : Execute Simple NLA Stride (Repeated clicks accumulate calculations).
  <br>

#### 5. Professional Mode
![alt text](images/img_2006.png)  
  **>> Core feature: Offset and Scale are adjusted automatically with simple settings <<**

- T : Pro Start Falloff [(Detailed Description)](#Stride_Description)  
  Four formulas: 1. Linear / 2. Ease In / 3. Ease Out / 4. Ease In Out.
  <br>

- U : Set Start Frame  
  Sets the overall animation **start** time for all objects in the list.
  <br>

- V : Offset Ratio (Start)    
  Offset amount multiplied by falloff (T) to automate start points for all strips.
  <br>

- W : Pro End Falloff [(Detailed Description)](#Stride_Description)    
  Four formulas: 1. Linear / 2. Ease In / 3. Ease Out / 4. Ease In Out.
  <br>

- X : Set End Frame    
  Sets the overall animation **end** time for all objects in the list.
  <br>

- Y : Offset Ratio (End)    
  Difference between the first and last object (supports negative values).
  <br>

- Z : Execute Professional NLA Stride (Repeated clicks **do not** accumulate).
  <br>


---

## ❓ FAQ
<a id="FAQ"></a>


#### 1. ⚠️ Note on "Instanced Data" Details

This add-on targets the NLA Strips themselves for offset and alignment;  
it **does not** automatically handle Blender's "Instanced Data" relationships.

#### What is Instanced Data?

When **multiple objects share the same data block**, that data is "Instanced."

- For example:  
  - Two objects sharing the same Material.  
  - Sharing the same Action (animation), Mesh, or other data blocks.  

In the NLA Editor, these appear as independent strips, but they **point to the same underlying data**.
As a result, using **NLA Stride** on instanced strips will move the strips, but because they share data, the **intended offset will not be achieved**.


#### ✅ Solution (Follow steps below)

> 💡 **Key: Make data "Single User" before applying offset.**

Steps (as shown in image):

1. Select objects in the 3D Viewport.  
2. Go to **Object → Relations**.  
3. Click **Make Single User**.  
4. Select the required data type (e.g., Object Animation).
5. Once data is independent, use **NLA Stride** for offset.  



![alt text](images/img_3001.png)

> Once data is independent, each object has its own "True NLA Data."
> NLA Stride can then **shift strips normally and predictably**.
---


#### 2. ⚠️ Batch Push to NLA

This add-on works on NLA Strips. Standard animations (Active Actions) that haven't been pushed to NLA will not be affected.

#### ✅ Solution: Batch Conversion Tool

The add-on provides a tool to convert objects in the list to NLA in one go (green arrow below). Note: this affects the **List**, not just the 3D selection.

![alt text](images/img_3002.png)

---



## 📖 Others
<a id="Others"></a>


#### 1. Alignment and Offset Strategy Tips

- Press **Alt A** in the 3D Viewport to deselect everything, then use **Select List Objects** to verify exactly what is in your list.  
<br>

- **Order** is crucial as it directly affects the resulting animation. Use naming conventions for order when possible. For many objects, consider using the [`Export / Import`](#Version_Updates) feature or processing in batches.  
<br>

- If things get messy, use the Alignment tools to sync everything back to a starting point.  
<br>

- Since offsetting is now easy, focus on creating one **perfect movement**.  
<br>

- Regarding movement design: If **Location** is keyed, note that copying or playing may cause objects to jump back to their recorded coordinates. Use **Ctrl A** (Apply Transformation) to write new locations into the **Delta Transform** data.  
  <br>![alt text](images/img_4001.png)  

---

#### 2. Stride Description
<a id="Stride_Description"></a>

- Linear Stacking Mode:  
  - Simple Mode:   
  <a href="images/img_4002.png"><img src="images/img_4002.png" width="650"></a>  
  Simple Mode calculates based on the original state (leftmost image). For example, with Offset 100 and Scale 1.5, the last strip's start point and length will always be the same; however, different falloff modes will create different intermediate start points, resulting in varied offset "feelings."

    ---
  - Professional Mode:    
  <a href="images/img_4003.png"><img src="images/img_4003.png" width="650"></a>  
  Unlike Simple Mode, Professional Mode allows separate control of the Head and Tail, with individual falloff settings for each.  
  
    ---
  - **Warning**:   
  <a href="images/img_4004.png"><img src="images/img_4004.png" width="650"></a>  
  If the falloff modes for head and tail are **different**, watch out for animation strips becoming too short or disappearing.
---

#### 3. List Icon Meanings
<a id="List_Icon_Meanings"></a>

![alt text](images/img_3003.gif)

Icon A: Data Mode
Icon B: Action represents standard animation data (non-NLA)
Icon C: Available NLA Data

- The symbols in B and C change based on the Data Mode selected in column A:
  - ✔ : Contains **correct** data matching the Mode in column A.
  - ・: Contains data, but **not** of the type set in column A.
  - ✕ : No data found.

Data in the example:
| Item | Object Animation | Material Animation | Shape Key Animation |
|------|------|------|--------|
| **NLA Strip** | cube.049 | cube.050 | cube.051 | 
| **Active Action** | cube.027 | cube.037 | cube.038 | 

- Others: cube.000 (Has all 3 types of NLA) / cube.039 (No animation data at all)

---




## 🔧 Technical Reference
<a id="Technical_Reference"></a>

  [Blender NLA Official Manual](https://docs.blender.org/manual/en/latest/editors/nla/index.html)

  [Blender API Official Manual](https://docs.blender.org/api/current/bpy.ops.nla.html)

  


## 📘 Contents

1. [Quick Start](#Quick_Start) 
2. [Version Updates](#Version_Updates) 
3. [Feature Overview](#Feature_Overview)      
4. [FAQ](#FAQ) 
5. [Others](#Others) 
6. [Technical Reference](#Technical_Reference)