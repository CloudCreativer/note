---
program: Google 數位人才探索計劃
course: AI職場通識學程
topic: 使用 Gemini：數據資料學家和分析師
parent_topic: 將生成式 AI 整合至資料工作流程
source: Google Skills · Gemini for Data Scientists and Analysts
date: 2026-05-29
status: inbox
tags:
  - Gemini
  - BigQuery
  - BigQuery ML
  - Vertex AI
  - Looker
  - RAG
  - K-means
  - 資料科學
  - 資料分析
  - Colab Enterprise
---

# 使用 Gemini：數據資料學家和分析師

> Google Skills · 將生成式 AI 整合至資料工作流程 · Gemini for Data Scientists and Analysts

## Insight

資料工作的核心轉變是：**不必離開 BigQuery 控制台**，就能用自然語言完成「探索 → SQL → 建模 → 預測 → 業務洞察」。Gemini 在 BigQuery 中扮演三角色——**自動生成 SQL、自動補全、白話解釋**；進階場景則結合 **BigQuery ML（ARIMA_PLUS、K-means）** 與 **Gemini 2.5 Pro（客群畫像、行銷策略）**，甚至透過 **Vertex AI + RAG** 把非結構化維修報告轉成可執行的預測性維護建議。執行 AI 產出的程式碼前，**務必核對 Schema**，因為生成式 AI 仍可能幻覺。

## Input

- **來源**：Google Skills ·「Gemini for Data Scientists and Analysts」課程（影片 × 3、實作實驗室 × 2、隨堂測驗）
- **附件**：[`assets/將生成式 AI 整合至資料工作流程_後續步驟.pdf`](assets/將生成式 AI 整合至資料工作流程_後續步驟.pdf)
- **內容摘要**：
  - 影片：生產線資訊主頁從被動式升級為預測性維護（Looker + BigQuery + Vertex AI RAG）
  - 實驗室（分析師）：Cymbal Superstore 電商資料 · Gemini 輔助 SQL · ARIMA_PLUS 銷售預測
  - 影片：BigQuery Studio 一站式資料分析流程（15～20 分鐘）
  - 實驗室（資料科學家）：K-means 客群分群 + Gemini 2.5 Pro 行銷企劃
  - 影片：LLM 連結模型設計（分群 → 視覺化 → 策略生成）
  - 隨堂測驗：100% 通過

## Translation

| 原文 / 課程說法 | 我的理解 |
|----------------|----------|
| Duet AI 已更名為 Gemini。 | Google Cloud 介面若看到舊稱，一律視為 Gemini；不必困惑版本名稱。 |
| Gemini 的三大 SQL 能力。 | 不是取代資料科學家，而是把「寫語法、讀語法、查文件」的時間壓縮——人專注在問題定義與結果解讀。 |
| BigQuery Studio 一站式工作區。 | 過去要在控制台、文件、Colab、ML 平台間切換；現在在同一個 Studio 裡用 `#` 自然語言生成 SQL、用 Gemini 解釋 ARIMA 原理。 |
| K-means + Gemini Pro 的兩段式流程。 | 第一段用傳統 ML 做量化分群（CENTROID_ID）；第二段把統計摘要餵給 LLM，把數字翻成「流失忠誠客」「大金主」等可執行行銷語言。 |
| RAG 降低幻覺。 | 預測性維護不能只靠 LLM 瞎猜；要把設備檢查報告向量化，檢索後再生成建議，才有依據。 |
| 執行前檢查 Schema。 | AI 寫的 SQL 可能引用不存在的欄位；養成「生成 → 對照 Schema → 執行」的習慣，是負責任使用 AI 的底線。 |

## Why

| 以前覺得 | 現在覺得 |
|----------|----------|
| 資料分析 = 自己寫 SQL + 查 Stack Overflow。 | 自然語言可生成、補全、解釋 SQL，但業務邏輯與資料品質仍要靠人把關。 |
| 機器學習要另開 Python 環境、搬資料。 | BigQuery ML 可在 SQL 層建 ARIMA、K-means；Colab Enterprise 筆記本嵌在 Studio 內，DataFrames 直接連 BigQuery。 |
| 分群結果 = 一堆數字和圖表。 | LLM 可把 cluster 統計轉成 Persona 與 Next marketing step，縮短「分析 → 決策」的最後一哩。 |
| 生成式 AI 只適合文字任務。 | 在資料流程中，它是 SQL 助手、程式碼生成器、業務策略師——多角色整合在同一平台。 |

## Action

- [ ] 在 BigQuery 啟用 `cloudaicompanion.googleapis.com`，勾選自動補全、自動生成、說明
- [ ] 用 Cymbal 公開資料集練習：貼一段複雜 SQL → 請 Gemini「說明目前選取的查詢」
- [ ] 用 `#` 提示詞生成跨表 JOIN 日銷量查詢，執行前對照 Schema
- [ ] 建一個 ARIMA_PLUS 模型，並用 Gemini 生成 `ML.FORECAST` 語法
- [ ] 完成 K-means 分群後，把 cluster 摘要餵給 Gemini 2.5 Pro，產出行銷畫像草稿
- [ ] 閱讀附件 PDF，挑一條 [Gemini 版 Google Cloud 學習路徑](https://www.cloudskillsboost.google/) 繼續深入

## Question

- 我們的資料是否已具備「結構化交易 + 非結構化報告」兩類，才能複製 RAG 維護場景？
- ARIMA_PLUS 訓練約 10 分鐘——在正式環境如何排程與監控成本？
- K-means 的 k=5 是業務假設還是統計驗證？如何選擇最佳群數？
- Gemini 生成的 SQL 在我們的多雲 / 跨專案 Schema 下，錯誤率有多高？需要什麼審核流程？

---

## 重點整理

### 模組一：影片 — 生產線資訊主頁與預測性維護（概覽）

**情境**：資料專家將工廠生產線資訊主頁從「被動（出事才處理）」升級為「主動（預測性維護）」。

| 步驟 | 工具 | 重點 |
|------|------|------|
| 1. 發現問題與即時診斷 | Looker + Gemini | 下午 2 點產量異常 → 在 Looker 用 Prompt 問 Gemini → 定位某產線產量降 4 倍，建議查相關指標 |
| 2. 數據探索與自動化分析 | BigQuery Studio | 內建資料品質檢查；Gemini 在 Insights 分頁預先分析，協助理解多雲環境資料表 |
| 3. 快速撰寫程式碼與建模 | Gemini 輔助 Code | Python 筆記本中用自然語言生成 Logistic Regression 所需 SQL，跨雲連結資料 |
| 4. 非結構化資料與 RAG | Vertex AI + BigQuery ML | 設備檢查報告 → 向量 + 摘要 → RAG Agent → 精準、低幻覺的預測性操作建議 |

**總結**：BigQuery + Gemini + Vertex AI 整合後，過去需大量時間的工作可在數分鐘內於安全環境一站式完成，協助企業防範停機風險。

---

### 模組二：實作實驗室 — 分析師：在 Gemini 協助下分析資料

**角色**：資料分析師 · **企業**：Cymbal Superstore（虛擬電商）  
**目標**：電子商務資料分析與銷售預測

#### 核心學習目標

| 目標 | 說明 |
|------|------|
| 探索與諮詢 | 用自然語言向 Gemini 了解 Google Cloud 資料分析產品 |
| SQL 查詢優化 | 用 Prompt 解釋複雜 SQL 或自動生成新查詢 |
| 預測建模 | 用 BigQuery ML 建構 ML 模型預測未來銷售 |

#### 主要任務步驟

| 工作 | 主要操作 |
|------|----------|
| 工作 1：環境與帳戶 | 啟動 Cloud Shell；啟用 `cloudaicompanion.googleapis.com`；配置 IAM |
| 工作 2：建立資料集 | 建立 `bqml_tutorial`；勾選 Gemini 自動補全、自動產生、說明 |
| 工作 3：提示詞互動 | 練習向 Gemini Cloud Assist 發問（如：如何在 BigQuery 找到可用資料集與表） |
| 工作 4：AI 解釋 SQL | 貼上複雜 SQL →「說明目前選取的查詢」→ 白話業務解讀 |
| 工作 5：自動生成 SQL | 輸入需求 Prompt → 生成含 LEFT JOIN、SUM、GROUP BY 的跨表日銷量查詢 |
| 工作 6：ARIMA 預測 | 建立 `ARIMA_PLUS` 時間序列模型（約 10 分鐘）→ 用 Gemini 生成 `ML.FORECAST` 語法 |

#### 重要注意事項

- **Duet AI → Gemini**：介面舊稱皆視為 Gemini
- **幻覺風險**：執行生成 SQL 前，先手動檢查資料表 Schema

---

### 模組三：影片 — 如何使用 Gemini 分析資料

**場景**：BigQuery Studio · **時間**：約 15～20 分鐘完成完整流程

| 階段 | 重點 |
|------|------|
| 1. 環境與探索 | 啟用 Gemini API；勾選自動補全、自動生成、說明；自然語言詢問可用資料集與表 |
| 2. SQL 輔助 | 選取 SQL →「說明這項查詢」；編輯器輸入 `#` + 自然語言需求 → Tab 採用生成語法 |
| 3. BigQuery ML | 建構 `ARIMA_PLUS`；訓練等待時可問 Gemini 模型原理；完成後請 Gemini 生成預測語法（如 7 個預測點、信心 0.95） |

**核心價值**：分析師不需離開 Cloud 控制台，即可加速「從資料到 AI」的開發流程。

---

### 模組四：實作實驗室 — 資料科學家：Gemini for Data Scientists

**目標**：K-means 將顧客分為 5 群，並用 **Gemini 2.5 Pro** 生成行銷客群畫像與策略

#### 核心學習目標

| 目標 | 說明 |
|------|------|
| 一站式開發 | BigQuery Studio 內嵌 Colab Enterprise Python 筆記本 |
| 高效處理 | BigQuery DataFrames 探索與操作大規模資料 |
| AI 輔助編程 | Prompt 生成資料分割與 ML 建模程式碼 |
| 生成式業務應用 | Gemini Pro 將分群統計轉為可執行行銷企劃 |

#### 主要任務步驟

| 工作 | 主要操作與 Gemini 應用 |
|------|------------------------|
| 工作 1 | 建立 `ecommerce` 資料集 |
| 工作 2～3 | 建立 Python 筆記本，連線 Colab Enterprise Runtime |
| 工作 4：建模 | ① 整理公開電商資料為 `customer_stats`（Recency、Frequency、Monetary）<br>② Gemini 生成 DataFrame + `train_test_split`<br>③ Gemini 生成 5 叢集 KMeans 並存回 BigQuery<br>④ Gemini 生成 matplotlib 散布圖 |
| 工作 5：行銷洞察 | SQL 彙整各群平均消費、訂單數、流失天數 → 呼叫 `gemini-2.5-pro` 扮演品牌策略師 → 產出 Title、Persona、Next marketing step |
| 工作 6 | 刪除資料表與模型，避免不必要雲端費用 |

**客群範例（課程產出）**：流失潛力客、高單價偶發客、大金主、價格敏感客等。

---

### 模組五：影片 — 使用 Gemini 設計與 LLM 連結的模型

**五步驟實作流程**（與模組四呼應，影片示範版）

| 步驟 | 內容 |
|------|------|
| 1. 環境初始化 | 一鍵啟用 BigQuery Studio 所需 API；建立 Python 筆記本，連線 Colab Enterprise |
| 2. 資料準備 | SQL 建立 `customer_stats`；「Generate with AI」將表轉為 BigFrames DataFrame |
| 3. K-means 建模 | Prompt：`train_test_split(0.2)`、5 群 KMeans、存回 BigQuery → 約 2 分鐘完成，產出 `CENTROID_ID` |
| 4. 視覺化與摘要 | Gemini 生成 matplotlib 散布圖；SQL 彙整統計 → Python 轉為 `cluster_info` 字串 |
| 5. 連結 LLM | Gemini 2.5 Pro 扮演「創意品牌策略師」→ 輸出客群稱謂、畫像、具體行銷下一步 |

**範例客群稱謂**：The Lapsed Loyalists、The Occasional Treaters、The Big Spenders 等。

---

### 模組六：隨堂測驗（100%）

#### 題 1：BigQuery 中 Gemini 的資料分析應用（多選）

正確三大功能：

1. **自動生成 SQL 查詢** — 依白話描述寫出 SQL
2. **自動補全 SQL 查詢** — 撰寫時智慧補全
3. **解釋 SQL 語法原理** — 白話解讀複雜查詢

#### 題 2：識別客群的 Vertex AI 模型（單選）

**正確答案**：**K-means clustering model** — 用於劃分客戶群體（Customer clusters / segments）

> 非 Text-bison 或多模態嵌入模型之文字生成場景。

---

## 工具與 API 速查

| 項目 | 說明 |
|------|------|
| Gemini API | `cloudaicompanion.googleapis.com` |
| 分析師實驗資料集 | `bqml_tutorial` |
| 資料科學家實驗資料集 | `ecommerce` |
| 時間序列模型 | `ARIMA_PLUS` + `ML.FORECAST` |
| 分群模型 | K-means（5 clusters） |
| LLM 行銷洞察 | `gemini-2.5-pro` |
| 自然語言生成 SQL | 編輯器中 `#` + 需求描述 |
| 舊稱提醒 | Duet AI = Gemini |

---

## 延伸資源

課程後續步驟（見 [`assets/將生成式 AI 整合至資料工作流程_後續步驟.pdf`](assets/將生成式 AI 整合至資料工作流程_後續步驟.pdf)）：

| 資源 | 說明 |
|------|------|
| [Gemini 版 Google Cloud 學習路徑](https://www.cloudskillsboost.google/) | Google Cloud Skills Boost · 各類開發者範例 |
| [Google Cloud Tech YouTube](https://www.youtube.com/googlecloudtech) | Gemini、Cloud、開發工具最新資訊 |
| [Google Cloud 網誌](https://cloud.google.com/blog) | 開發人員、資料分析、AI/ML 主題 |
| [Gemini 說明文件](https://cloud.google.com/gemini/docs) | 更有效提示詞、AI 開發原則 |

---

## 更新紀錄

- 2026-05-29：建立初版（整合課程影片、實驗室、測驗與後續步驟 PDF）
