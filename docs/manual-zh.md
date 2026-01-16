<!-- 手冊封面 -->
# NLA-Stride 使用手冊（中文）

> 本手冊介紹 NLA-Stride Blender 外掛的快速開始、操作指南與深入技巧。

---

## 📘 目錄

1. [快速開始](#快速開始)  
2. [功能總覽](#功能總覽)  
3. [詳細指南](#詳細指南)  
4. [常見問題](#常見問題)  
5. [技術參考](#技術參考)

---

## 🚀 快速開始

### 1. 一般外掛安裝

<a href="images/img_1001.png">
  <img src="images/img_1001.png" width="650">
</a>

安裝外掛後，在 Blender 3D 檢視中的 **側欄 → 動畫** 頁籤可以看到 **NLA Stride Tool**。

---

### 2. 選取具有動畫的物件

<a href="images/img_1002.png">
  <img src="images/img_1002.png" width="650">
</a>

選取一或多個含有動畫資料的物件。如果是標準動畫而非 NLA 動畫，請參閱「大量建立 NLA」說明。

---

### 3. 加入清單

<a href="images/img_1003.png">
  <img src="images/img_1003.png" width="650">
</a>

⚠️ 請注意：外掛是依靠清單運作，與即時選取物件無關。

---

### 4. NLA 對齊 / 錯位操作


<a href="images/img_1004.png"><img src="images/img_1004.png" width="650"></a>

<a href="images/img_1005.png"><img src="images/img_1005.png" width="650"></a>

<a href="images/img_1006.png"><img src="images/img_1006.png" width="650"></a>


以上是 NLA 對齊與錯位功能示意。

---

### 5. 享受動畫魅力

<a href="images/DEMO_01.mp4">
  <img src="images/DEMO_01.gif" width="720">
</a>

<a href="images/DEMO_02.mp4">
  <img src="images/DEMO_02.gif" width="720">
</a>

<a href="images/DEM3_02.mp4">
  <img src="images/DEMO_03.gif" width="720">
</a>

---

## 🧰 功能總覽

> - 物件順序
> - NLA 自動對齊
> - 錯位動畫片段
> - 大量建立 NLA  
> - 跨物件操作  
> - 路徑與控制設定  


---

## 📖 詳細指南


#### 1. ⚠️ 注意「實例化資料（Instanced Data）」的細節

本外掛主要針對 NLA 片段（Strips）本身進行錯位與對齊處理，  
並 **不會** 自動處理 Blender 的「實例化資料」關係。

#### 什麼是實例化資料？

當**多個物件共用同一份資料**時，這些資料就是「實例化（Instanced）」的。

- 例如：  
  - 兩個物件共用同一個材質球  
  - 或共用同一個動畫、網格、或其他資料區塊  

在NLA 編輯器中看起來像是兩條獨立片段，但實際上**背後指向的是同一份資料**。
結果就是，在這種情況下使用 **NLA Stride 進行錯位**時，外掛看似在移動不同片段，但實際上仍在影響同一份資料，因此**無法達成你預期的錯位效果**。


#### ✅ 解決方式（ 搭配下方截圖操作 ）

> 💡 **關鍵做法：先將資料獨立化，再進行錯位**

步驟如下（ 如圖所示 ）：

1. 在 3D 視窗中選取需要處理的物件  
2. 開啟 **物件 → 關聯資料（Relations）**  
3. 點擊 **使單一使用者（Make Single User）**  
4. 依需求選取需要獨立的資料類型
5. 確認資料已獨立後，再使用 **NLA Stride** 進行錯位  



<a href="images/img_3001.png">
  <img src="images/img_3001.png" width="650">
</a>

> 資料獨立後，每個物件都會擁有「真正獨立的 NLA 資料」，NLA Stride 即可 **正常、可預期地錯位 NLA 片段** 。
---


### 大量建立 NLA

> ❗ 請在這裡描述如何針對多物件建立 NLA。

### 對齊與錯位策略小技巧

> ❗ 加入一些實用操作技巧與快捷鍵提示。

---

## ❓ 常見問題

> ❗ FAQ 範例：
>
> **Q：我的圖片未顯示？**  
> A：請確定 images 資料夾與 MD 文件同路徑。  

> **Q：點擊圖片無反應？**  
> A：GitHub 上預覽會跳出大圖；VSCode FLU 效果也類似。

---

## 🔧 技術參考

> ❗ 若需引用 Blender NLA 核心概念，這裡可以貼官方連結或摘要：

例如：Blender 提供的 NLA 編輯器基本介紹可參考官方手冊。:contentReference[oaicite:1]{index=1}

---

<!-- 手冊結束 -->

