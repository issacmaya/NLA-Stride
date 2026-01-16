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

<p align="center">
<a href="images/img_1004.png"><img src="images/img_1004.png" width="380"></a>
<a href="images/img_1005.png"><img src="images/img_1005.png" width="380"></a>
<a href="images/img_1006.png"><img src="images/img_1006.png" width="380"></a>
</p>

以上是 NLA 對齊與錯位功能示意。

---

### 5. 享受動畫魅力

<a href="images/DEMO_01.gif">
  <img src="images/DEMO_01.gif" width="720">
</a>

<a href="images/DEMO_02.gif">
  <img src="images/DEMO_02.gif" width="720">
</a>

---

## 🧰 功能總覽

> ❗ 此部分請補充你外掛的所有功能清單，例如：
> - NLA 自動對齊
> - 錯位動畫片段
> - 大量建立 NLA  
> - 跨物件操作  
> - 路徑與控制設定  
> - …etc

---

## 📖 詳細指南

### 注意資料是否為 "實例化資料"

> ❗ 外掛本身只針對，片段去做調整，所以如果有實例化資料，也就是類似的共用資料，的情況，NLA 在錯位時會不如原本預期。

> 例如 : 兩個物件，共用同一個材質球 ( 舉例 : M材質 ) ，也可以說 M材質是一種實例化的狀態，雖然在兩個物體的 NLA 中，看似是兩個獨立的片段，但實際操作就可以得知，是同樣的東西；這時候如果用 NLA Stride 外掛錯位，將無法錯位

```
 💡 解決方式 : 
    用 blender 內建的功能，將資料獨立出來，就可以正常錯位了 ^ +++^
```
<a href="images/img_3001.png">
  <img src="images/img_3001.png" width="650">
</a>
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

