---
type: event-notes
title: AppWorks AI Founder Day — CTO / Builder 專場
date: 2026-06-03
track: CTO / Builder
location: 台北市信義區（報名後顯示詳細地址）
status: final
has_images: true
tags:
  - AppWorks
  - AI-native
  - Codex
  - Zeabur
  - OpenAB
  - OpenAI
  - VC
  - ABConvert
source:
  - 20260603_AppWorks AI Founder Day_1.vtt
  - 20260603_AppWorks AI Founder Day_2.vtt
  - 20260603_AppWorks AI Founder Day_1.m4a
  - 20260603_AppWorks AI Founder Day_2.m4a
  - assets/images/jpeg/（現場簡報 40 張）
  - https://luma.com/px31nbtx
  - https://www.cebillhsu.xyz/ai-employee-setup
  - https://github.com/zeabur/agent-skills
---

# AppWorks AI Founder Day — CTO / Builder 專場筆記

## 活動資訊

| 項目 | 內容 |
|------|------|
| **活動** | [2026 AppWorks AI Founder Day](https://luma.com/px31nbtx) |
| **主辦** | AppWorks AI Arm（協力：OpenAI、Zeabur） |
| **本筆記涵蓋** | 全場（VTT #1 主題分享 + VTT #2 OpenAI／工作坊）+ 簡報照片 |
| **逐字稿** | `_1.vtt`（開場～OpenAB）· `_2.vtt`（Thomas／Codex 工作坊～散場） |
| **錄音** | 同檔名 `.m4a` 兩段 |
| **現場照片** | 40 張 JPEG → [`assets/images/照片索引.md`](assets/images/照片索引.md) |
| **處理流程** | VTT 五階 Pipeline + 簡報 OCR 補強（規範見 [`活動紀錄架構.md`](../活動紀錄架構.md)） |

### 素材涵蓋範圍

| 區段 | VTT | 簡報照片 | 備註 |
|------|-----|----------|------|
| 開場 · AppWorks | ✅ | ✅ | |
| Bill · AI-native VC | ✅ | ✅ | 含 5 AI 員工架構圖、Section 01/05 |
| Jeffrey · ABConvert | ✅ | ✅ | 含 AW#28 簡報頁、對談照 |
| Zeabur · Brian | ✅ | ✅ | Agent Skills、Nufus |
| OpenAB · Allen | ✅ | ✅ | Bot2Bot、Discord review 截圖 |
| OpenAI · Thomas Jeng | ✅ | ✅ | VTT #2 |
| Codex 工作坊 · Jane / Jordan | ✅ | ✅ | 含現場福利、三組 demo 得獎 |

### 官方議程對照（CTO 場）

| 時間 | 內容 |
|------|------|
| 09:30–09:45 | AppWorks 開場 |
| 09:45–10:00 | Jeffrey（ABConvert）AI-native 實務 |
| 10:00–10:25 | Zeabur × OpenAB（Allen） |
| 10:25–10:35 | OpenAI 最新動態（Thomas Jeng） |
| 10:35–12:30 | Codex 實作工作坊 |
| 12:30–13:30 | 午餐與交流 |

> 本逐字稿實際收錄順序為：開場 → **Bill（AI-native VC）** → Jeffrey → Zeabur（Brian）→ OpenAB（Allen）。與 Luma 公佈順序略有不同，以現場為準。

---

## 30 秒看懂

AppWorks × OpenAI 的 CTO 場是一條完整 **AI-native 堆疊**：**VC** 用 5 個 AI 員工 + Notion 鏡像層（Bill）→ **新創** 5 人百萬 ARR、workflow 串行導入 Agent（Jeffrey）→ **基建** 一句話部署（Zeabur）與 Agent @ Agent 協作（OpenAB）→ **模型方** 主張 2026 是「隊友」而非工具，並用 **Agents SDK** 在 30–45 分鐘內做出 Pictionary Lab 示範。共通原則：**Intelligence 自動化、Judgment 留人；今天的 judgment 會變成明天的 intelligence。**

---

## 處理紀錄（Pipeline）

```
原始 VTT + 現場簡報照片（PNG → JPEG）
        ↓
【AI 清理】校正專有名詞、講者、ASR 錯字
        ↓
【章節切分】時間軸 + 簡報 SECTION 對齊
        ↓
【重點摘要】全場 TL;DR（VTT 與投影片交叉驗證）
        ↓
【知識卡片】可複用框架
        ↓
【本 MD】+ assets/images/jpeg/
```

---

## 章節切分

### 第 0 章｜開場與活動行政（00:00–05:38）

**講者**：AppWorks 主持人（Sophie 團隊）

**重點**

- AppWorks：2009 年起、亞洲加速器 + VC；**不收股權、不收費**；約 **650** 間活躍新創、四支基金總管理規模近 **$400M**、投資 **100+** 間；C 到 B 輪都有佈局。
- **AI Arm**（前身 AppWorks School）做企業 AI 轉型，為 **OpenAI 官方合作夥伴**。
- **BAT#30**：2026 年 9 月開跑，招募約 6–7 月；現場 QR Code 可報名。
- 今日無固定休息；主程式 **12:30** 結束，外場午餐與交流至約 **14:00**。
- 下午 **Codex Workshop** 有 OpenAI 技術團隊在場答疑。

---

### 第 1 章｜Bill Hsu — AI-native VC（05:38–20:35）

**身份**：AppWorks Principal（iFund / LiveeVC 專案）  
**延伸閱讀**：[五個 AI 員工的系統架構](https://www.cebillhsu.xyz/ai-employee-setup)

#### 1.1 為什麼 VC 要 AI 化（SECTION 01）

![VC 工作 = Intelligence + Judgment](assets/images/jpeg/IMG_7052.jpg)

- 外界以為 VC「出一張嘴」；實際平均看 **30–50** 個案子才投 **1** 個，大量 research、legal、財務會議等 **不能靠嘴**。
- 投影片結論：**AI 接管 Intelligence，Judgment 留給人** — 能自動化的不重複做，最終判斷留給人。

| 類型 | 簡報列舉 | 口頭補充 |
|------|----------|----------|
| **Intelligence** | Deal 篩選與資料建檔、財務建模與估值、市場研究與數據追蹤、Portfolio 數據監控 | 同上 |
| **Judgment** | Founder 評估與投資信念、市場 Timing 與 Thesis、Portfolio 策略與配置、關係建立與信任 | Why you / why now、票據大小 |
| **Trust** | （歸在 Judgment） | 信任決定你能拿到多少真實資訊 |

#### 1.2 系統架構（SECTION 02 · 5 個 AI 員工）

![5 個 AI 員工架構](assets/images/jpeg/IMG_7081.jpg)

| 層級 | 元件 | 權限／角色 |
|------|------|------------|
| **人** | Bill | 透過 Notion Dashboard 同步狀態；Telegram 直接 DM 各員工 |
| **鏡像** | Notion | **R/W** — agents 寫這裡；= GWS mirror，**不寫公司真正 SoT** |
| **SoT** | Google Workspace | **READ** — Deal pipeline、Founder、Content |
| **工具** | Slack、Telegram、Fireflies、LINE WORKS、Dune、GitHub、Obsidian Second Brain | 見簡報標示 READ/R/W |
| **Runtime** | Mac Pro | 全能員工 · 所有 skill |
| **Runtime** | Mac Mini | Telegram 與 **5 員工 24×7**；各員工獨立 workspace |

**五位 AI 員工**：Jared（EA）、Bobby（VC）、Steve（PM）、Samantha（Content）、Taylor（CFO）。

**實作備註（簡報 footer）**

- Config 全在 **git repo**
- Mac Mini **Cron** 觸發 heartbeat / retro
- **Guardrails with hook**（如 npm 套件年齡檢查、Telegram zombie 清理、遠端 restart）
- 完整架構網頁 QR → [ai-employee-setup](https://www.cebillhsu.xyz/ai-employee-setup)

**安全設計**：主帳號（GWS）不被 Agent 直接寫入；human-in-the-loop 在 Notion review／指示。

#### 1.3 Deal 生命週期 × AI

| 階段 | AI 做什麼 | 人做什麼 |
|------|-----------|----------|
| **Sourcing** | 追蹤 X 上 GP 新 follow 的帳號 → web search → 主動 reach out | 判斷要不要追 |
| **Screening** | 掃 inbound（email、Telegram、WhatsApp）→ early screening | 每案 human-in-the-loop |
| **First call 前** | 讀 deck、LinkedIn、YouTube 訪談全文 → 產出待 verify 清單 | 帶問題深問 |
| **Call 後** | Fireflies 逐字稿 → 對照 verify 清單、建議 follow-up | 決定是否進 DD |
| **DD / IC** | 產 IC memo 草稿 | 投委 judgment |
| **Portfolio** | 標準化週報；一年後回顧「說到做到」early detection | 介入時機 |

> 單步從 30–60 分鐘 → **1–2 分鐘**；但**沒有任何階段全自動進下一關**。

#### 1.4 一日節奏（Heartbeat）

| 時間 (TPE) | 事件 |
|------------|------|
| 晨間 | 彙整行事曆、Gmail、Slack、Telegram、LINE、Google Tasks → 今日優先序 |
| 08:00 | Heartbeat #1：掃 Notion Task、處理低風險項 |
| 11:00 前後 | Founder call |
| 12:00 | 自動拉逐字稿、更新 Notion |
| 下午 | 看 AI employee dashboard、下指令 |
| 20:00 | 每日回顧 → **只提 1 項**改進（skill / 設定），避免輸出爆量看不完 |
| 睡前 | Bill 在 Notion 回覆「Waiting on Bill」任務 |

**Tune 心得**：Agent 輸出是最大瓶頸——資訊不能太少也不能太多，要持續調溝通密度。

**長期迴圈**：每個 judgment（為何拒絕、為何喜歡）都是訓練資料；今天拒絕的理由，未來可能變成可自動化的 intelligence——但 VC **feedback cycle 5–10 年**，比 coding 慢很多。

#### 1.5 實驗：Zeabur 上的 inbound agent

- 與 portfolio **Zeabur** 合作，對外聊天機器人作 **inbound deal 的 pre-judgment**，有機會進入 AppWorks deal pipeline。
- 完整 AI employee repo 有對外開放（現場 QR / 會後可問 Bill）。

#### 1.6 長期迭代（SECTION 05）

![不只 skill — 架構也在進步](assets/images/jpeg/IMG_7086.jpg)

- 每寫完一篇文章、每投完一個案子 → 回去修 **skill**；跑久了發現問題 → 連 **heartbeat 節奏、權限設計** 也持續調。
- **今天的 judgment，會變成明天的 intelligence**（與 VC 5–10 年 feedback cycle 並存 — 靠 log 密度餵資料）。

#### 1.7 One More Thing：Bill AI Bot

![Bill AI Bot · LINE](assets/images/jpeg/IMG_7089.jpg)

- **Bill AI Bot**，powered by **Raccoon AI**；現場 LINE QR 可試玩（與 Zeabur inbound 實驗呼應）。

---

### 第 2 章｜Jeffrey — ABConvert AI-native 新創（20:35–41:34）

![Jeffrey Lin · ABConvert AW#28](assets/images/jpeg/IMG_7059.jpg)

**公司**：ABConvert — Shopify 商家 **A/B 測試**，幫商家在找到 product-market fit 後做轉換優化（scale 段）。

#### 2.1 成績與團隊

| 指標 | 數據（口頭分享，以公司官方為準） |
|------|----------------------------------|
| 團隊 | 約 **5 人** |
| ARR | 去年約 **$120 萬** |
| 營運 | 主要業務相關流量/轉換持續優化；自稱 **#1 Token User**（現場貼紙梗） |

#### 2.2 用人 → 用 Agent

- 傳統招聘：不合適的 engineer 可能「掐住」公司；Agent：**好處都在你這邊**，可隨時換版、持續進化，談判籌碼不同。
- 關鍵不是「有 Agent」，是 **Agent 品質** 與你下的規格。

#### 2.3 Agent 導入順序（與網路下載 skill 相反）

```
❌ 不要：從網路拉一堆 skill 同時開做
✅ 要：依「會賺錢的 workflow」一條條完成

1. 從 Copy / 主題素材（一個行銷活動）做滿做穩
2. 再做 QA
3. 再做 TR（轉換）相關比較
4. 再補阻塞、短鏈等周邊
→ 做完一個再開下一個，日落後沒時間重拍
```

**專注機制**：刻意限制並行（例如 PR 開啟數量、每人同時 PR 數）——看似限制，實際適合小團隊 **深度 > 廣度**。

#### 2.4 Go-to-Market

- 渠道（Meta、Google 等）本身中性；重點是 **每個漏斗的 conversion + ROI** 都要算清楚。
- 產品架構：**Unified Converter** — 行銷、廣告、SEO、產品頁、品牌頁轉換 **同一套數據** 可寫、可比較。
- 以往行銷說「可以優化」但難驗證；現在要 **全年持續跑得出數字** 的流程。

#### 2.5 Token Maxing vs Outcome Maxing

| 階段 | 策略 |
|------|------|
| **第一階段**（個人/小團隊、PMF 前） | 先拼命用 AI 把 **護城河** 建起來，不必急著省 token |
| **第二階段**（5→10→100 人規模） | 再談 **token / outcome** 最佳化，把花樣串進財務模型 |

#### 2.6 Codex 使用心得

- **Codex** 像「會把活做完的初階工程師」：適合 **規格清楚、難度高** 的任務；流程中會自動做很多檢查，**產出結束才交付**。
- **Claude**（對話型）像「好人」：適合 **2 分鐘內要方向** 的試探。
- 兩者都可接 skill；要理解各自 **context / runtime** 特性，避免一個 session 太長後亂輸出。
- 建議：**持續用 Codex 處理高價值工程** + 其他工具輔助。

#### 2.7 工程時間分配與組織

- 以前約 **30%** 時間在 AoT（AI 相關工作），含閱讀與精進；現在多數循環內建 **檢查 → 追蹤 → 修正**，不必刻意「擠壓」進度。
- 團隊：**2 個 head** 概念 — 一人偏產品、一人偏工程；兩邊都會做 feature / 維運 / 實驗，**通才化**。
- **Sprint**：仍在演進；產出從「demo」轉向「**這個 sprint 改變了什麼原則**」；傳統 sprint 的 demo / 驗收邏輯在 AI 時代需重寫。
- **跨 IDE skill 同步**：靠 **Git 版控** 管理，不要靠各工具內建 sync。

---

### 第 2 章補充｜現場

- 由 **Natasha Chou**（AppWorks）與 Jeffrey 對談形式分享（見 [`IMG_7090.jpg`](assets/images/jpeg/IMG_7090.jpg)）。

---

### 第 3 章｜Brian — Zeabur × Agent 部署（41:37–50:18）

**主題**：Year of Agents — 用自然語言 **開發 + 部署 + 維運**

![Zeabur Agent Skills](assets/images/jpeg/IMG_7066.jpg)

- 開源 Skills：`https://github.com/zeabur/agent-skills` — *The skills your agent needs to deploy in one sentence*

#### 3.1 核心能力（Agent Skills）

| 場景 | 一句話指令範例 |
|------|----------------|
| **部署** | 「幫我把這個 Next.js 部署上線 + PostgreSQL + provision website」 |
| **Debug** | 「去看 project/service 為什麼 provision 慢 / 資料不見」 |
| **SSH** | 「SSH 進伺服器把 Ingress timeout 改成 300s」 |
| **模板** | 「把這個 GitHub repo 轉成 Zeabur 模板並發佈」 |

- Agent 擅長讀 log、一次修配置錯誤。
- Skills 支援 **Codex**（主推）與 **Claude Code**。
- **模板獎勵**：使用量回饋 credits，未來可換現金（「躺著賺」梗）。

#### 3.2 新產品預告：Nufus（簡報拼字）

![Nufus · Agentic DevOps](assets/images/jpeg/IMG_7070.jpg)

- 簡報品牌 **Nufus**（口頭亦稱 Nufus）：**你有 AWS/GCP，但想要 AI DevOps 幫你運維？**
- 尚未正式 publish；概念是 **Agentic DevOps harness 進你的雲**（非把你搬上 Zeabur 平台）。
- Deck 網址現場為 `0603-deck.zeabur.app`（活動用）。

---

### 第 4 章｜Allen — Open Agent Broker（OpenAB）（50:18–63:17）

![OPENAB FOR CODEX](assets/images/jpeg/IMG_7061.jpg)

**講者**：Allen Tseng（曾啟倫）· OpenAB maintainer  
**標語**：*Let AI agents collaborate in your chat*  
**專案**：Open Agent Broker（Rust、輕量、開源）— 用「減法」設計的 Agent harness

#### 4.1 問題意識

- 個人用 Gemini / Claude 很常見；團隊要的是 **數位員工** 嵌入 **業務流程**，而非一人一個聊天視窗。

#### 4.2 架構

```
Discord / Slack / Telegram / LINE / Google Chat
        ↓
OpenAB（Rust 橋接層，支援 ACP）
        ↓
Coding CLI（Codex 等；全球首批支援 Antigravity CLI）
        ↓
每個 Agent 獨立 Pod（高隔離）
```

- 哲學：**最少內建功能**，其餘自己加 — 比「功能很多但用不到」更貼近個人習慣。

#### 4.3 Agent ↔ Agent

![Agents talking to agents](assets/images/jpeg/IMG_7072.jpg)

- 在 **Discord**（亦支援 Slack、Telegram 等）用 **@mention** 交接：寫 code、測試、review。
- **人類只下第一道指令**；OpenAB 把每個 @ 當 message event 派給對應 agent。
- Demo 角色：**Jarvis** 統整 → **Friday**、**Ultron** 分別 review（三國梗簡報）；現場 Slack/Discord 截圖可見 Rust `.unwrap()` 等具體評語（[`IMG_7065.jpg`](assets/images/jpeg/IMG_7065.jpg)）。

#### 4.4 還能做什麼（簡報）

![OpenAB 其他能力](assets/images/jpeg/IMG_7078.jpg)

| 功能 | 說明 |
|------|------|
| **內建排程** | 定時讓 agent 自動執行 |
| **訊息批次派發** | per-lane 智慧排隊 |
| **語音訊息** | 轉文字送 agent — 用講的寫 code |
| **多 thread 並行** | 同 agent 多 thread、獨立 context |

- 延伸：multi-agent 寫 issue、proposal、開 PR、review 能否 merge；一小時可開 **10 個 thread** 各跑不同 review。

#### 4.5 落地

- 全開源；**Zeabur 一鍵模板**安裝；團隊以台灣 contributor 為主。

---

### 第 5 章｜OpenAI — Thomas Jeng & Tyler（10:25–12:15 前半）｜VTT #2

**講者**：Thomas Jeng（OpenAI 亞洲新創）  
**現場團隊**：Johnny（新加坡 ADE）、Neil（Account Director · 新創）、Kyler（Codex）

#### 5.1 Paradigm Shift：2026 = 隊友

![2022 → 2025 → 2026](assets/images/jpeg/IMG_7056.jpg)

| 年份 | 定位 | 能做什麼 |
|------|------|----------|
| **2022** | 聊天機器人 | 文字進出、趣味應用 |
| **2025** | 工具 | Deep Research、圖片、文件、**Codex** — 嵌入 workflow |
| **2026+** | **隊友** | ① 自動化軟體開發 ② 超級個人助理 ③ **End-to-end 商業工作流**（最難） |

**要完成 paradigm shift 的六項條件（Thomas 歸納）**

1. Agent **自主執行時間拉長**（複雜任務需長 runtime）
2. **多模態** I/O（語音、影像、圖片、文件）
3. 適用 **非 AI-native 介面**（不是每件事都有 MCP/API）
4. **長期記憶**與理解
5. **安全、簡易部署**
6. **治理**（企業不能把 AI 隨便丟進去）

#### 5.2 模型與 benchmark（簡報 + 口頭）

![ARC-AGI-2 能力 vs 成本](assets/images/jpeg/IMG_7058.jpg)

| 標竿 | 重點 |
|------|------|
| **ARC-AGI-2** | 抽象推理；能力急速上升、**CP 值**相對高 |
| **SWE-bench 系** | 編碼能力；**GPT-5.5** 在成本與時間上表現突出（簡報橘色標示） |
| **GDPval** | 非程式工作（財模、簡報等）；AI 輸出與人類專家盲測 — **GPT-5.5 約 85%+** 場次優於人類 |

> Thomas 強調：模型輸出已很好，但 **AI 系統建構** 仍不完善 — 這是 OpenAI 做 SDK、Responses API、Codex harness 的原因。  
> 簡報標 **Confidential** — 精確分數見投影片，筆記不逐格抄錄。

**其他能力線**：語音 Speech-to-Speech、影像（Character 級品質已可進工作場景）、財模／簡報／程式等基礎模型廣化。

**台灣聯絡**：商務找 **Neil**；技術找 **ADE**（新加坡團隊服務台灣）。AI-native 新創歡迎合作。

#### 5.3 現場福利（工作坊前公布）

| 項目 | 內容 |
|------|------|
| 點數 | 每人 **$250** API credits + **3 個月** Technology Pro |
| 申請 | 活動表格（Thomas 請**先不要掃**，統一說明後填） |
| Email | 必須是已登入過 **ChatGPT 的同一信箱** |
| Org ID | 開發者平台 → Settings → General → `org-...`（不是公司名稱） |
| 登入 Codex | 建議 **ChatGPT SSO**，勿只用 API key（否則無法用 plugins） |

#### 5.4 Tyler · Agents SDK & Pictionary Lab

![Pictionary Lab 架構](assets/images/jpeg/IMG_7079.jpg)  
![現場 demo](assets/images/jpeg/IMG_7080.jpg)

- **Codex 30–45 分鐘** 做完可玩專案，再請 AI **畫架構圖**（與簡報字幕一致）。
- 主體：**Agents SDK**（TypeScript / JavaScript，**免費**開源）。
- 玩法：一人畫、AI **語音猜**（背後有「隱藏 actor」聽關鍵字 — 現場猜測用 **GPT-5.5** + computer use）。
- 架構：Guesser 走 **RealtimeSession**；Drawer 走 server **Agents SDK** + tools 當 **guardrail**（見 §5.3 簡報表與 [`IMG_7079`](assets/images/jpeg/IMG_7079.jpg)）。

---

### 第 6 章｜Codex 工作坊（10:35–12:50）｜VTT #2

#### 6.1 流程總覽

| 時間 | 內容 |
|------|------|
| ~10:35 | 下載 Codex、填表、ADE 現場協助 |
| ~11:00 | 點數發放；**自由實作 ~1hr**（建議做到 12:15） |
| ~11:00–11:40 | **Jane**（台灣 Codex Ambassador）功能導覽 |
| ~11:40+ | **Jordan**（OpenAI）Fast mode、Subagents、Sites |
| ~12:15–12:50 | 三組 **Demo 發表** + 評選 |
| 12:50 | 正式結束；空間與午餐交流至 **14:00** |

**任務**：新產品或既有產品**新功能**均可；做出可給評審看的 MVP / flow。

**獎勵**：發表且評估通過 — 額外 **$5,000** API credits（現場稱三組得獎；原宣傳亦有 $250 + 3mo Pro）。

#### 6.2 Jane · Codex 新功能（Ambassador 導覽）

![Prompt 層級](assets/images/jpeg/IMG_7068.jpg)

| 功能 | 用法與心法 |
|------|------------|
| **imageGen v2**（4 月） | 先產 **UI mockup**（文字渲染佳），再讓 Codex 實作 app |
| **Prompt（UI）** | ① 列出畫面**內容與層級**（標題、hero、vendor 列表…）② 視覺用**具體**描述（避免「高級、夢幻」）③ 給參考圖更佳 ④ 要求 **Safari / iPhone frame** → 較像可實作的產品圖 |
| **Goal** | 設**可驗證**目標（例：延遲低於 100ms、測試全綠）；可 **Pause / 改目標 / Steer** |
| **Side 臨時對話** | Fork 主線 context，問「現在做到哪」不打斷 Goal — 搭配 Goal 很好用 |
| **管理對話** | 一句話開多個 worktree（例：GitHub 找簡單 bug → 開 5 個獨立對話） |
| **手機遠端** | 外出可改文案、**Approve 權限**、切多台機器上的 agent |

Jane 角色：連結**在地社群 ↔ OpenAI 官方**（辦活動、合作可找 Ambassador）。

#### 6.3 Jordan · 進階操作

| 功能 | 重點 |
|------|------|
| **Sites** | 新 hosting；目前偏 **Business / Enterprise**（現場帳號可能看不到） |
| **Fast mode** | 更快、**耗更多 token/credits**；適合 production triage，不代表更聰明 |
| **Subagents** | 大 repo / monorepo 可並行；預設最多 **6** 個，可 prompt 加開；**明確指定**各 subagent 負責範圍（安全 / 品質 / bug）效果較好；**credits 消耗較多** |
| **登入** | API key 登入無 SSO → **plugins 受限**；建議 ChatGPT 登入 |

#### 6.4 工作坊 Demo 得獎（三組）

**第一組 — 題庫／家教輔助（家長場景）**

- 痛點：每期下載 **康軒等版本** 題庫、列印給孩子寫。
- 實作：語音「小學康軒三年級數學」→ 自動對應年級題庫；**OCR / 切題** + 卡通化；規劃 **語音互動**、會員、多科。
- 技術：工作坊中用 **GPT-5.5 Fast** 等（現場強調很快）。

**第二組 — SafeTrap（保險科技 · 銷售會議教練）**

- 公司：保險科技起家；新產品輔助 **保險業務銷售會議**（不只逐字稿）。
- 差異：會中即時 **節奏建議** — 對方沉默、拒絕時怎麼回；可為每家公司客製 **agent persona**。
- 定位：從 Fintech 銷售場景擴到更多銷售會議類型。

**第三組 — Zero Application（一人公司 / CLI 多 agent）**

- 概念：Individual founder 難 hire → **CLI + 多 VM「辦公室」**，每室有專長 agent，可**互相溝通**（類 OpenClaw / Hermes 想像）。
- 工作坊成果：原本無 iOS，用 **Codex 約 1 小時** 做出 iOS 介面 + chat + SSH 連線等。
- 願景：像 Mac **開箱即用**，不需自己「組裝」agent（對比 PC 自組 CPU/GPU）。

> 現場：「大家都做得很棒」，僅 showcase 三組；其餘參與者仍享 $250 + Pro。

#### 6.5 散場

- 12:50 工作坊結束；午餐外場；可交流至 14:00。
- VTT #2 後段多為交流與背景音，**不納入章節正文**。

---

## 重點摘要（全場）

### 一句話

> **AI-native 不是買更多工具，而是：Intelligence/Judgment 分工、Notion 鏡像、多 Agent runtime、git 集中設定；模型方則把 AI 推進「隊友」與 Agents SDK 實作 — judgment 日誌最後會變成可自動化的 intelligence。**

### 四條主線對照

| 維度 | Bill（VC） | Jeffrey（新創） | Zeabur + OpenAB | OpenAI |
|------|------------|-----------------|-----------------|--------|
| **目標** | 多看案、少雜事 | 5 人百萬 ARR | NL 部署 / multi-agent | 隊友 + SDK 示範 |
| **組織** | 5 Agent + Mac Pro | workflow 串行 | Skills + Nufus | Realtime + Server agent |
| **節奏** | Heartbeat / retro | 做完再下一條 | 一句話 deploy | Goal + Side + 1hr MVP |
| **風險** | GWS 唯讀 | PR/WIP 限制 | Pod 隔離 | Tool = guardrail |

### 與 Bill 公開架構的對照

現場分享與 [AI Employee Setup](https://www.cebillhsu.xyz/ai-employee-setup) 高度一致：

- Notion Task 狀態機（Waiting on Bill → Bill Replied → In Progress → Done）
- Mac Mini 五 session / Mac Pro 全 context
- Telegram `clear_*` 遠端重啟
- 每日 20:00 回顧、睡前 Notion 回覆

---

## 知識卡片

### 卡片 1｜Intelligence vs Judgment

```
┌─────────────────────────────────────┐
│ Intelligence（可自動化）              │
│ 篩案、拉數據、初稿、監控、整理逐字稿    │
└─────────────────┬───────────────────┘
                  │ 人類拍板
                  ▼
┌─────────────────────────────────────┐
│ Judgment（保留給人）                  │
│ 投不投、投多少、信任、策略、時機        │
└─────────────────────────────────────┘
```

**可複用**：任何知識工作崗（PM、CTO、投資、營運）都可先畫這兩欄，再決定 Agent 邊界。

---

### 卡片 2｜資料鏡像原則

- **Source of truth**：公司正式系統（如 Google Workspace）— **唯讀** 對 Agent。
- **Agent workspace**：Notion（或同級）mirror — **可讀寫**。
- **為什麼**：撤不回的動作要人審；可撤回的研究/草稿 Agent 做。

---

### 卡片 3｜單一 Repo 可攜性

- `CLAUDE.md` / skill / memory / hook / `install.sh` → **一個 git repo**。
- 換機器、換模型（Claude → Codex）、Mac Mini ↔ Mac Pro **同一套 config**。
- Jeffrey 補充：跨 IDE 的 skill 也應走 **Git**，不要依賴工具內建 sync。

---

### 卡片 4｜Agent 導入順序（新創版）

1. 選 **會賺錢** 或 **會省時間** 的一條 workflow（不是最酷的功能）。
2. **做滿、做穩、可驗證 ROI** 再開下一個 Agent。
3. 用 **WIP 限制**（PR 數、並行專案數）保護專注力。
4. PMF 前 **Token Maxing**；規模化後再 **Outcome Maxing**。

---

### 卡片 5｜Codex vs 對話型模型

| | Codex | 對話型（如 Claude Chat） |
|--|-------|--------------------------|
| **隱喻** | 初階工程師，會做完 | 顧問，快速給方向 |
| **適合** | 規格清楚、長 runtime、要交付物 | 2 分鐘內探索想法 |
| **注意** | session 過長可能品質漂移 | 不會自動幫你 deploy |

---

### 卡片 6｜Multi-Agent 協作（OpenAB）

- **Agent @ Agent** = 程式化的 peer review / 分工。
- **Thread 並行** = 多任務不污染 context。
- **排程鏈** = A 完成 → B 接手，適合 issue → PR → review 流水線。
- 安全：**一 Agent 一 Pod**，降低橫向移動風險。

---

### 卡片 7｜VC 獨特限制

- Coding feedback：**天～週**；投資結果：**5–10 年**。
- 因此 AI 在 VC 的價值在 **累積 judgment 日誌** 與 **縮短 research latency**，不在「全自動決策投資」。

---

### 卡片 8｜人腦三旋鈕（Bill 網站原則，場內呼應）

1. **Cadence**：Heartbeat 間隔（2h vs 4h）影響心流。
2. **Dashboard**：非同步任務看板（Notion）避免進度流失在聊天窗。
3. **資訊密度**：結論 + next action + 3 options；細節等追問再展開。

---

### 卡片 9｜Judgment → Intelligence 飛輪（Bill SECTION 05）

- 每篇文章、每個案子 → 修 skill；跑久了 → 調 heartbeat、權限。
- **今天的 judgment = 明天的 intelligence**（需密集 log + 長 feedback cycle 耐心）。

---

### 卡片 10｜OpenAB Bot2Bot

- 人 @ agent；**agent @ agent** 交接 review。
- Discord **thread** 並行多任務；**語音→文字** 下指令；**per-lane** 排隊。

---

### 卡片 11｜Agents SDK 雙分支（Pictionary Lab）

- **Realtime**（瀏覽器）：語音猜詞、ephemeral token、tool 當 guardrail。
- **Server agent**（伺服器）：`computer_action` 畫筆、非 realtime。
- 通訊統一走 Socket.IO 事件，不讓 model 直接改 UI。

---

### 卡片 12｜Codex Goal 介面

- 長任務：**Pause · Edit Goal · Steer** — 人類在關鍵點校正，不是 fire-and-forget。
- Prompt 要寫清**畫面資訊架構**（有哪些區塊、層級），不只風格形容詞。

---

### 卡片 13｜Codex 工作坊心法（Jane）

1. **imageGen → Codex**：先 mockup 再實作，降低「Fancy 但做不出來」。
2. **Goal 要有驗收條件** — 測試綠燈、指標達標，不是模糊「幫我做好」。
3. **Side 問進度、主線繼續跑** — 分工釐清監控 vs 執行。
4. **Fast mode / Subagents** — 救急用，日常注意 **credits 燒速**。

---

### 卡片 14｜2026 隊友六條件（Thomas）

部署 AI 前自問：任務夠長嗎？多模態齊嗎？非 API 介面怎麼操作？有記憶嗎？好部署嗎？誰治理？

---

## 簡報與現場照片

- 全部 JPEG：`assets/images/jpeg/`（40 張）
- 分類索引：[`assets/images/照片索引.md`](assets/images/照片索引.md)
- 活動全景：[`IMG_7091.jpg`](assets/images/jpeg/IMG_7091.jpg) — *2026 AppWorks AI Founder Day · Powered by OpenAI*

---

## 金句與現場梗

- 「VC 出一張嘴」是誤會；**30–50 案才投 1 案**。
- 「最大的瓶頸是 **Agent 輸出** — 不是模型不夠聰明，是你看不完。」
- 「日落後沒時間重拍」— 所以 **一次只做一條 workflow**。
- 「#1 Token User」— ABConvert 自嘲貼紙。
- 「一個 Agent 不行，三個 Agent 總可以吧。」— OpenAB。
- 「搞定了所有東西，大概三十到四十五分鐘……它給我畫了這張架構圖。」— Pictionary Lab（簡報字幕）。
- 「今天的 judgment，會變成明天的 intelligence。」— Bill SECTION 05。

---

## 連結與資源

| 資源 | URL |
|------|-----|
| 活動頁 | https://luma.com/px31nbtx |
| Bill AI Employee 架構 | https://www.cebillhsu.xyz/ai-employee-setup |
| Bill AI Bot | 現場 LINE QR（Raccoon AI） |
| OpenAI Platform | https://platform.openai.com/ |
| Zeabur Agent Skills | https://github.com/zeabur/agent-skills |
| OpenAB | 開源 repo + Zeabur 模板 |
| 照片索引 | [assets/images/照片索引.md](assets/images/照片索引.md) |

---

## ✅ 可採取的 Action Items

| 負責人 | 任務 | 備註 |
|--------|------|------|
| 自己 | 掃描 Bill 架構 QR / 讀完 ai-employee-setup 網頁 | 對照自家工具鏈缺口 |
| 自己 | 畫出 Intelligence / Judgment 分工表 | 套用到目前專案 |
| 自己 | 若用 Zeabur：安裝 Agent Skills，試「一句話 deploy」 | Codex + Zeabur 工作坊延伸 |
| 自己 | 評估 OpenAB：Discord + Codex multi-agent review | 小專案 pilot |
| 自己 | BAT#30 有意者 | 6–7 月留意 AppWorks 招募 |
| 自己 | 若參加工作坊：用 ChatGPT 信箱填表領 $250 + Pro | 需 `org-...` ID |
| 自己 | 試 imageGen mockup → Codex 實作流程 | Jane 建議 |
| 自己 | 試玩 Pictionary Lab / Agents SDK 開源 repo | 對照簡報架構圖 |

---

## ⚠️ 待確認

| 項目 | 說明 |
|------|------|
| OpenAI benchmark 精確分數 | 簡報 Confidential；僅記趨勢 |
| 得獎團隊公司正式名稱 | VTT 音譯（SafeTrap、Zero Application 等）待查 |
| 申請表 / Technology Pro 細節 | 現場未逐字念 URL |
| ABConvert 精確 ARR | 以官方為準 |
| Nufus 上線時程 | Zeabur 簡報預告 |

---

## 📈 本次學到什麼

1. **AI-native 的單位是 workflow** — Bill（VC）、Jeffrey（新創）、OpenAB（協作）同一套「分工 + 鏡像 + 人類拍板」。
2. **2026 = 隊友** — 六條件（長任務、多模態、非 native UI、記憶、部署、治理）是檢查表，不是口號。
3. **模型強 ≠ 系統強** — GDPval 85% 仍要自己做 harness；這也是 Zeabur / OpenAB 機會。
4. **Codex 產品節奏** — Goal（可驗證）+ Side（監控）+ 管理多對話（編排）+ 手機 approve = 完整「隊友」操作面。
5. **工作坊 MVP** — 1 小時可做出語音題庫、銷售教練、多 agent CLI — 關鍵是目標夠具體、可 demo。
6. **燒錢意識** — Fast mode、Subagents 省時間但吃 credits；Jeffrey 的 Token Maxing 與 Jordan 提醒呼應。

---

## 逐字稿對照

| 檔案 | 約略時間軸 | 內容 |
|------|------------|------|
| `…_1.vtt` / `…_1.m4a` | 00:00–01:03 | 開場 → Bill → Jeffrey → Zeabur → OpenAB |
| `…_2.vtt` / `…_2.m4a` | 00:00–03:27+ | Thomas → 工作坊 → Demo → 交流（後段多雜訊） |

---

## 更新紀錄

- 2026-06-03：VTT #1 + 簡報照片 → 初版
- 2026-06-03：VTT #2 併入第 5–6 章、工作坊得獎、現場福利；`status: final`
