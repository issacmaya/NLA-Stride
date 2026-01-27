<a href="images/NLA-Stride_LOGO2.png"><img src="images/NLA-Stride_LOGO2.png" width="250"></a>  

# 使用手册（简体中文）

> 本手册介绍 NLA-Stride Blender 插件的相关功能与一些技巧，也有一些常见的问题解答。

---

## 📘 目录

1. [快速开始](#Quick_Start)  
2. [版本更新重点](#Version_Updates)
3. [功能总览](#Feature_Overview)      
4. [常见问题](#FAQ) 
5. [其他](#Others) 
6. [技术参考](#Technical_Reference)

---

## 🚀 快速开始
<a id="Quick_Start"></a>

### 1. 插件安装

1. 使用 Blender 官方的安装步骤即可 ( **[通用安装教学](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)** )

2. 安装插件后，在 Blender 3D 视图中的 **侧栏 → 动画** 页签可以看到 **NLA Stride Tool**。 
<br>![alt text](images/img_1001.png)



---

### 2. 选取具有动画的物件  
<a href="images/img_1002.png">
  <img src="images/img_1002.png" width="650">
</a>  

选取一个或多个包含动画数据的物件。如果您使用的是标准动画而非 NLA 动画，请参阅“NLA 批次建立”说明。

---

### 3. 加入清单

![alt text](images/img_1003.png)

⚠️ 注意：插件运行逻辑是以清单为主，与视图中即时的物件选取是相互独立的。

---

### 4. NLA 对齐 / 错位操作


<a href="images/img_1004.png"><img src="images/img_1004.png" width="650"></a>  

<a href="images/img_1005.png"><img src="images/img_1005.png" width="650"></a>  

<a href="images/img_1006.png"><img src="images/img_1006.png" width="650"></a>  


以上为 NLA 对齐与错位功能的演示。

---

### 5. 享受动画的魔力

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

特别感谢台湾品牌 [SANSUI / 山水](https://www.sansuitw.com/?gad_source=1&gad_campaignid=23085773952&gbraid=0AAAAAoXC59ENhboAZDO-y0zK4yQpidtXM&gclid=CjwKCAiAybfLBhAjEiwAI0mBBscjnZOEYBBY127EypNMfnL1h_Vqm_HACczeJBOqMK-euDJFPb1iAxoC7rkQAvD_BwE) 提供示例模型。

---
## 🌟 版本更新重点
<a id="Version_Updates"></a>
  
#### v1.0.0 重点更新
- 清单导出 / 读取 / 追加 
  ![alt text](images/v100_001.png)  
  1. 清单操作新增了三个功能。
  2. 导出与读取清单文件使用 *.json 格式。
  3. “追加”会将项目加入清单的最末端。
  4. 若名称重复，将以清单中原有的物件为准。
#### v0.9.8 重点更新  
- 初始公开发布版  
---
## 🧰 功能总览
<a id="Feature_Overview"></a>
 

#### 1. 动画来源 

![alt text](images/img_2001.png)

- A : 初始并加入所选    
  清除目前的清单数据，并将场景中目前选取的物件加入清单。  
  <br>
- B : 清空清单  
  删除清单内的所有物件数据。  
  <br>
- C : 动画来源  
    目前支持三种类型：  
    -  物件动画 (Object Animation)  
    -  形态键动画 (Shape Key Animation)  
    -  材质动画 (Material Animation)
  <br>
- D : 加入 / 删除清单物件  
  加入时 **不会** 清空清单；物件会 **依据选取顺序** 加入清单最后方。若选取已在清单中的物件，它们会被移动到最后方。这与方式 A 不同。删除也与 1-J 不同。  
  <br>

- E : 清单操作 (下拉菜单)  
  详情请见 [1-1 清单操作](#List_Functions)。
  <br>

- F : 将选中项上移 / 下移  
  手动调整排序。一旦手动调整过顺序，该顺序即被定义为 **“缓存原始顺序”**。
  <br>

- G : 推送至 NLA (下拉菜单)  
  仅将清单内的物件动画转换为 NLA 片段。
  <br>  
  
-  PS. [3. 清单中的图标意义](#List_Icon_Meanings)

#### 1-1. 清单操作
<a id="List_Functions"></a>

![alt text](images/img_2002.png)

- H : 初始并加入所选   
  清除清单数据，并将场景中目前选取的物件加入清单。
  <br>

- I : 四种排序状态    
  最重要的是插件记录的 **原始顺序**，其他三种为暂时的排序显示状态。
  <br>

- J : 删除场景选取   
  从清单中删除目前在 3D 视图中选取的物件 (与 1-D 不同)。
  <br>

#### 2. 指定错位片段

![alt text](images/img_2003.png)

- K : 三种片段模式 (Strip Mode)  
  - 单一片段 : 仅针对特定的某一个片段。
  - 单一轨道 : 将一条轨道上的所有片段视为一个整体 (保持相对位置)。
  - 全部轨道 : 物件的所有轨道会同步变动 (保持相对位置)。
  <br>

- L : 三种定位器  
  - 哪个槽位 (Slot) : 仅限材质模式，在 NLA 界面中由 **上至下** 计算。
  - 哪条轨道 (Track) : 在 NLA 界面中由 **下至上** 计算。
  - 哪个片段 (Strip) : 在 NLA 界面中由 **左至右** 计算。
  <br>

  **!! 注意：若目标指定不正确，NLA 错位将无法执行。**

#### 3. NLA 对齐工具 (初始值)
![alt text](images/img_2004.png)

- M : 五种对齐模式 (Align Mode)  
  - 齐最大开始帧 : 以清单片段中 **最后** 的起始点为基准。
  - 齐最小开始帧 : 以清单片段中 **最早** 的起始点为基准 (常用)。
  - 齐最大结束帧 : 以清单片段中 **最后** 的结束点为基准 (常用)。
  - 齐最小结束帧 : 以清单片段中 **最早** 的结束点为基准。
  - 齐目前时间 : 以目前的播放头位置为基准 (最常用)。
  <br>

- N : 三种对齐方式  
  - 齐开始 : 将左侧对齐至基准点 (常用于起始点对齐)。
  - 齐中 : 将中心点对齐至基准点。
  - 齐结束 : 将右侧对齐至基准点 (常用于结束点对齐)。
  <br>

- O : 重置缩放  
  将清单中所有 NLA 片段的缩放值恢复为 1。
  <br>


#### 4. 简易模式

![alt text](images/img_2005.png)  
- P : 简易模式衰减 (叠加模式) [(详细说明)](#Stride_Description)  
  错位计算公式共有四种：1. 线性 / 2. 淡入 / 3. 淡出 / 4. 淡入淡出。
  <br>

- Q : 位移量 (单位：**帧**)  
  清单中第一个物件与最后一个物件的总位移差距 (支持输入负值)。
  <br>

- R : 缩放  
  清单中第一个物件与最后一个物件的缩放比例差距 (0 ~ 1)。
  <br>

- S : 执行简易 NLA 错位 (连续点击计算会累加)。
  <br>

#### 5. 专业模式
![alt text](images/img_2006.png)  
  **>> 本插件的核心：透过简单的设定，自动调整片段的错位与缩放 <<**

- T : 专业开始衰减 (叠加模式) [(详细说明)](#Stride_Description)  
  计算公式四种：1. 线性 / 2. 淡入 / 3. 淡出 / 4. 淡入淡出。
  <br>

- U : 设定开始帧  
  设定清单中所有物件动画的整体 **起始** 时间。
  <br>

- V : 位移比率 (开始)    
  位移量乘以叠加模式 (T) 的结果，用于自动设定所有片段的起始点。
  <br>

- W : 专业结束衰减 (叠加模式) [(详细说明)](#Stride_Description)    
  计算公式四种：1. 线性 / 2. 淡入 / 3. 淡出 / 4. 淡入淡出。
  <br>

- X : 设定结束帧    
  设定清单中所有物件动画的整体 **结束** 时间。
  <br>

- Y : 位移比率 (结束)    
  第一个物件与最后一个物件的差距 (支持输入负值)。
  <br>

- Z : 执行专业 NLA 错位 (连续点击 **不会** 累加计算)。
  <br>


---

## ❓ 常见问题
<a id="FAQ"></a>


#### 1. ⚠️ 请注意“关联数据 (Instanced Data)”的细节

本插件主要针对 NLA 片段 (Strips) 本身的位移与对齐处理，  
**不会** 自动处理 Blender 内部的“关联数据”关系。

#### 什么是关联数据？

当 **多个物件共享同一个数据块** 时，这些数据就是“关联”的。

- 例如：  
  - 两个物件共用同一个材质。  
  - 或者共用同一个动作 (Action/动画)、网格 (Mesh) 或其他数据块。  

在 NLA 编辑器中，它们看起来是独立的片段，但实际上 **指向同一组底层数据**。
导致的结果是，当使用 **NLA Stride 进行错位** 时，虽然片段位置移动了，但因为数据共用，**无法达到预期的错位效果**。


#### ✅ 解决方法 (请依照以下步骤操作)

> 💡 **核心概念：在错位前，先将数据转为“独立用户 (Single User)”。**

步骤说明 (如下图所示)：

1. 在 3D 视图中选取要处理的物件。  
2. 进入 **物件 (Object) → 关系 (Relations)**。  
3. 点击 **使其独立化 (Make Single User)**。  
4. 依需求选取需要独立的数据类型 (例如：物件动画)。
5. 确认数据独立后，再使用 **NLA Stride** 进行错位。  



![alt text](images/img_3001.png)

> 一旦数据独立，每个物件就拥有“真正独立的 NLA 数据”。
> 此时 NLA Stride 就能以 **正常且符合预期的方式平移片段**。
---


#### 2. ⚠️ NLA 批次建立

本插件是针对 NLA 片段进行作业，若尚未推送到 NLA 的一般动画 (Active Action) 是不会有变动的。

#### ✅ 解决方法：批次转换工具

插件提供了将清单内的物件一次转换为 NLA 的工具 (见下方绿色箭头)。注意：此功能针对 **清单** 而非 3D 选取。

![alt text](images/img_3002.png)

---



## 📖 其他
<a id="Others"></a>


#### 1. 对齐与错位策略技巧

- 您可以先在 3D 视图按 **Alt A** 全不选，再使用 **“选取清单物件”** 功能，确认清单里究竟有哪些物件。  
<br>

- **顺序** 非常重要，因为它直接影响错位后的动画状态。尽可能利用名称来决定顺序，若物件极多，建议拆分批次处理。  
<br>

- 若情况变得混乱，请利用对齐工具将所有片段同步回同一个起始点。  
<br>

- 因为动画错位变得非常简单，建议您可以专注于制作一个 **完美的动作**。  
<br>

- 关于动态设计：若 **位置 (Location)** 有设定关键帧，请注意复制出来的物件可能会跳回原位，因为位移数据已写死。此时请善用 **Ctrl A** (套用变换)，将新位置写入 **增减变换 (Delta Transform)** 数据中。  
  <br>![alt text](images/img_4001.png)  

---

#### 2. 错位说明
<a id="Stride_Description"></a>

- 线性叠加模式 :  
  - 简易模式 :   
  <a href="images/img_4002.png"><img src="images/img_4002.png" width="650"></a>  
  简易模式会以原本的状态 (如上图最左边) 叠加模式计算。如错位与缩放数值设定：错位 100、缩放 1.5，最后一个片段的起始点与长度 (结束点) 一定都会一样；但可以看到因为叠加模式的不同，导致其他片段的起始点不同，产生不同的错位感觉。

    ---
  - 专业模式 :    
  <a href="images/img_4003.png"><img src="images/img_4003.png" width="650"></a>  
  与简易模式的差异在于，专业模式可以分别设定控制“头”与“尾”，所以多了一个叠加模式可以分别设置。  
  
    ---
  - **注意** :   
  <a href="images/img_4004.png"><img src="images/img_4004.png" width="650"></a>  
  需注意头尾两种叠加模式若 **不同**，可能会导致动画片段出现问题 (过短或消失)。
---

#### 3. 清单中的图标意义
<a id="List_Icon_Meanings"></a>

![alt text](images/img_3003.gif)

图 A : 数据模式
图 B : Action 代表一般的动画数据 (非 NLA)
图 C : 可用的 NLA 数据

- B 栏与 C 栏符号的意义会随着 A 栏选取的数据模式而改变：
  - ✔ : 包含 **正确** 且符合 A 栏设置的数据。
  - ・ : 虽然有数据，但不属于 A 栏设置的类型。
  - ✕ : 无数据。

示例数据：
| 项目 | 物件动画 | 材质动画 | 形态键动画 |
|------|------|------|--------|
| **NLA 片段** | cube.049 | cube.050 | cube.051 | 
| **当前动作** | cube.027 | cube.037 | cube.038 | 

- 其他：cube.000 (拥有 3 种 NLA) / cube.039 (完全无动画数据)

---




## 🔧 技术参考
<a id="Technical_Reference"></a>

  [Blender NLA 官方手册](https://docs.blender.org/manual/en/latest/editors/nla/index.html)

  [Blender API 官方手册](https://docs.blender.org/api/current/bpy.ops.nla.html)

  


## 📘 目录

1. [快速开始](#Quick_Start) 
2. [版本更新重点](#Version_Updates) 
3. [功能总览](#Feature_Overview)      
4. [常见问题](#FAQ) 
5. [其他](#Others) 
6. [技术参考](#Technical_Reference)