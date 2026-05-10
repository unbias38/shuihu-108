# 水滸傳 一百零八將 · 互動名錄

> 百回本《水滸傳》108 位好漢的互動式網頁名錄。五種視圖、人物關係、AI 繪圖提示詞、配樂氛圍。

> *An interactive web directory of the 108 heroes from the classical Chinese novel* Water Margin *(by Shi Nai'an, 14th century).*

🌐 **線上 demo**：<https://unbias38.github.io/shuihu-108/>

---

## 特色

- **108 位好漢完整名錄**：依百回本《水滸傳》整理人物姓名、綽號、星宿、派系、武器、出場章回、結局、人際關係
- **五種視圖**自由切換，互不干擾
- **人物彈窗**：在天罡地煞 / 派系統計 / 關係圖 / 招安路線等視圖點任何人物，會跳出 modal 顯示完整資料，**不會切走原本的視圖**
- **繪圖提示詞**：每個人物都附 GPT Image 用的中文 prompt（含外貌、服裝、武器、左上題款 + 朱紅印章），一鍵複製
- **音效氛圍**：開場編鐘（純 Web Audio 合成）+ 章節提示音 + 翻書聲 + 真實樂器 BGM mp3
- **純前端**：無 build step、無後端、單一 HTML 即可運行
- **公共領域題材**：原作《水滸傳》為施耐庵所著（明代百回本）

## 五種視圖

| 視圖 | 內容 |
|---|---|
| **時間軸** | 按章回出場順序，每位好漢一張卡片，可展開看詳情 |
| **天罡地煞** | 依第 71 回大聚義時的「排座次」分為 36 天罡 + 72 地煞 |
| **派系統計** | 各派系（梁山元老、降將、二龍山、清風山、貴族莊主等）人數分布 + 結局類型統計圖（戰死/善終/出家/失蹤/瘟疫⋯⋯） |
| **關係圖** | D3.js 力導向圖，視覺化結義、救援、仇敵關係 |
| **招安路線** | 按招安立場分群（贊成 / 反對 / 中立），看派系矛盾的根源 |

## 互動操作

| 動作 | 結果 |
|---|---|
| 點時間軸卡片 | 展開 / 收起 |
| 點天罡地煞 / 招安路線 / 關係圖的人物 | 跳出 modal 顯示完整資料 |
| 卡片內點「結義 / 救過 / 仇敵」標籤 | 跳到該人物（可連跳） |
| 卡片底部「繪 圖 提 示 詞 ▾」 | 展開中文繪圖 prompt，右上角「複 製」鈕一鍵複製 |
| 點 🔇（變 🔊） | 啟用音效 + 播放開場編鐘 |
| 點 🎵 | 切換背景音樂 |
| ESC / 點背景遮罩 / 點 × | 關閉 modal |
| 搜尋框 | 即時篩選姓名 / 綽號 / 星宿 |
| 派系 chip | 篩選派系 |

## 技術棧

- **HTML / CSS / Vanilla JavaScript**：無框架、無 build step
- **D3.js v7**（關係圖力導向布局）via jsDelivr CDN
- **Web Audio API**：開場編鐘 / 章節鐘鼓 / 翻書聲 / 鑼聲全部即時合成（`OscillatorNode` + `BiquadFilterNode` + `AudioBufferSourceNode`）
- **HTML5 `<audio>`**：BGM mp3 自託管 loop
- **Google Fonts**：Noto Serif TC、ZCOOL XiaoWei、Ma Shan Zheng、Cormorant Garamond
- **單檔架構**：除 `examples/*.mp3` 外，所有程式碼、CSS、資料都在 `index.html` 裡（約 4500 行）

## 本地開發

```bash
git clone https://github.com/unbias38/shuihu-108.git
cd shuihu-108

# 用任一本地伺服器啟動（不能直接 file:// 開，因為 mp3 跨來源限制）
python -m http.server 8000
# 或
npx serve

# 開瀏覽器到 http://localhost:8000
```

## 部署

本 repo 已啟用 GitHub Pages（`main` 分支根目錄）。每次 `git push` 後 1-2 分鐘自動更新。

---

## 授權與致謝

### 📜 程式碼

[**MIT License**](LICENSE) — 自由使用、修改、商用，保留版權聲明即可。

### 📜 內容（人物資料、繪圖提示詞）

[**CC BY 4.0**](https://creativecommons.org/licenses/by/4.0/deed.zh-Hant) — 自由分享改編，引用請標註來源連結至本 repo。

> **關於繪圖提示詞**：108 個 prompt 由 AI 協助、依《水滸傳》原著描寫 + 綽號合理推論生成。主要好漢（特別是 36 天罡）有原著明確描寫；部分邊緣地煞原著著墨極少，描述含合理想像，使用時請審酌。

### 📜 第三方素材

| 項目 | 授權 | 來源 |
|---|---|---|
| 背景音樂《Asian Epic Adventure Music》 | [Pixabay Content License](https://pixabay.com/service/license-summary/) | Tunetank（[原連結](https://pixabay.com/music/main-title-asian-epic-adventure-music-414102/)） |
| D3.js v7 | ISC License | <https://d3js.org/> |
| Google Fonts（Noto Serif TC、ZCOOL XiaoWei、Ma Shan Zheng、Cormorant Garamond） | SIL Open Font License 1.1 | <https://fonts.google.com/> |

### 📜 原作

《水滸傳》**施耐庵**著（百回本，明代）—— **公共領域**。  
本網頁人物資料整理自百回本《水滸傳》。

### 📜 致謝

- 施耐庵與《水滸傳》六百年來的讀者
- Tunetank 提供 CC0 等級的免費 BGM
- D3.js / Google Fonts 開源社群

---

## 已知限制

- **行動裝置**：CSS 已做 RWD，但 D3 關係圖在小螢幕上節點較密、可讀性下降
- **首次音效啟動**：瀏覽器要求使用者手勢觸發，第一次點 🔇 才會初始化 AudioContext
- **BGM 載入**：4.4 MB mp3，首次載入有 1-2 秒延遲（之後瀏覽器快取）
- **資料勘誤**：邊緣地煞的細節（出場章回、結局、人際關係）若有誤歡迎開 issue 指正

## Roadmap（未開）

- [ ] 加 Open Graph / Twitter Card 元資料（讓貼連結時有預覽縮圖）
- [ ] 加 hash routing：每位好漢有獨立網址（`#hero/13` 直連魯智深）
- [ ] 加 AI 生成的人物畫像（用 repo 內的繪圖提示詞）
- [ ] 加英文版

歡迎 PR / Issue。
