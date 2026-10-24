# PCB Process Flow & Cross-Section Evolution Generator
## 互動式 PCB 製程流程與橫切面微觀結構演進模擬器

一個純前端、單一檔案（Zero-dependency, Single-file HTML5）、免安裝即可運行的高階印刷電路板（PCB / Substrate）製程流程設計與橫切面微觀結構物理演進模擬工具。

🔗 **線上即時體驗 (Live Demo)**: [https://thomm1124-afk.github.io/pcb-process-generator/](https://thomm1124-afk.github.io/pcb-process-generator/)

---

## 🌟 核心特色 (Key Features)

### 1. 28+ 完整 PCB 物理製程算子庫
涵蓋從基板開料到最終表面處理的完整真實製造步驟：
- **基板與壓合**：CCL 開料、棕化/黑化粗化 (Oxide)、多層板壓合 (Lamination)、多芯板對疊壓合 (Multi-Core Lamination)、RCC/ABF 增層壓合 (RCC Buildup)
- **鑽孔與成孔**：
  - CNC 機械鑽孔貫穿 (Mechanical Drilling)
  - 雷射盲孔 (Single-Sided Laser μVia)
  - **Core 雙面對鑽沙漏雷射孔 (Core X-Via)**
  - 選擇性同時雙孔鑽孔
- **化學與電鍍**：
  - 膠渣清除與電漿微蝕 (Desmear & Plasma)
  - 化學銅沉積 (PTH Seed Electroless Cu)
  - 全板一銅電鍍 (Panel Plating)
  - 圖形二銅電鍍 (Pattern Plating)
  - 填孔電鍍 (Via Fill Plating)
  - 蓋帽電鍍 (Cap Plating / VIPPO Overplate)
  - mSAP / SAP 超薄銅閃蝕 (Flash Etching)
- **塞孔與平坦化**：
  - 樹脂塞孔與高溫烘烤 (Resin Plug)
  - **選擇性塞孔 (Selective Plugging)**：以遮蔽擋片 (Mask Shield) 保護特定通孔維持空孔，僅對指定通孔塞孔
  - 陶瓷滾輪刷磨平坦化 (Planarization Grinding)
- **外層與表面處理**：
  - 乾膜壓膜與黃光顯影 (DFR Photoresist)
  - 酸性/鹼性藥水蝕刻 (Acid/Alkaline Etching)
  - 防焊油墨印刷與 SRO 開窗 (Solder Mask)
  - 化學鎳金表面處理 (ENIG Surface Finish)
  - 白字文字印刷 (Silkscreen Legend)
  - 飛針測試與光學檢驗 (AOI / E-Test)
  - 基板挖槽貼裝內埋元件 (Cavity & Embedded Components)

### 2. M+N 異質子板各自獨立設計與對接壓合 (M+N Hybrid Bonding)
- 支援先獨立推演 **子板 M (Sub-Board M)** 之線路、鑽孔與塞孔流程後進行存檔封存。
- 切換至 **子板 N (Sub-Board N)** 獨立推演其不同基材（如 PTFE 高頻板）與結構。
- 透過「M+N 兩板對接壓合」算子，將上下兩塊子板與中間黏合層 (Bonding Sheet) 自動完成物理結合，後續更可接續外層貫穿孔鑽鍍與表面防焊。

### 3. 即時真實向量渲染 (Real-time SVG Cross-Section Renderer)
- 依據製程算子的先後順序，自動精確推演銅層厚度、孔壁化銅層、介電層厚度、雷射錐形輪廓、沙漏型 X-Via 幾何形狀、塞孔凸起與刷磨平整度。
- 動態製程光效（雷射光束、鑽頭進給、電漿紫光、陶瓷滾輪、光學 AOI 掃描線）。

### 4. 雙視圖設計與海報導出
- **雙聯互動視圖 (Dual Interactive View)**：左側 Serpentine 流程圖 + 右側即時單站/前後對比橫切面結構。
- **流程海報總覽 (Storyboard Poster View)**：一次將所有站點排列為高解析度工程展示海報。
- **一鍵匯出**：支援將當前站點或全站海報一鍵匯出為高解析度 **SVG 向量圖檔** 或 **PNG 點陣圖檔**。
- **專案進度存取**：支援將流程匯出為標準 JSON 專案檔，並可隨時載入恢復編輯。

---

## 🚀 快速上手 (Getting Started)

### 線上直接使用
直接瀏覽 [GitHub Pages 線上版本](https://thomm1124-afk.github.io/pcb-process-generator/)。

### 本地運行
本專案為純 HTML5 + Vanilla JavaScript 架構，無需安裝 Node.js、npm 或任何編譯環境：
1. Clone 儲存庫：
   ```bash
   git clone https://github.com/thomm1124-afk/pcb-process-generator.git
   cd pcb-process-generator
   ```
2. 直接使用任意瀏覽器開啟 `index.html`（或滑鼠連按兩下）：
   ```bash
   open index.html # macOS
   # 或
   xdg-open index.html # Linux
   # 或
   start index.html # Windows
   ```

---

## 📄 授權條款 (License)

本專案採用 [MIT License](LICENSE) 開源授權，歡迎自由修改與分享。
