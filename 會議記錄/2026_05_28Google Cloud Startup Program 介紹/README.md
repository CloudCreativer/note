---
type: meeting-notes
title: Google Cloud Startup Program 介紹
date: 2026-05-28
attendees:
  - Angel Yu（TDCX · Google Cloud 台灣 Business Development）
  - Cloudia
status: final
tags:
  - Google Cloud
  - Startup Program
  - FortyOneTech
  - Elemy
source:
  - 20260528_GoogleStartUp說明.vtt
---

# Google Cloud Startup Program 介紹

## 與會人員

| 姓名 | 單位 | 角色 | 聯絡方式 |
|------|------|------|----------|
| Angel Yu | TDCX（代表 Google Cloud） | Business Development - Taiwan | youa@xwf.google.com · +886-2-8726-0407 · +886-956812820 |
| Cloudia | AI 股份有限公司（FortyOneTech） | 創辦人／技術 | — |

---

## 🎯 本次會議目標

了解 Google Cloud Startup Program 資格、補助 tier、申請流程，並確認 FortyOneTech／Elemy 是否符合 Start Tier 及後續加速器路徑。

---

## 📌 本次結論（必看）

### 決議 1：先申請 Start Tier（$2K USD）

- **內容**：團隊符合成立兩年內、自有產品解決方案，可先申請 Start Tier，取得 **$2,000 USD** 雲端點數（一年內用完）。
- **原因**：公司今年 2 月通過台北市政府核准、產品 Elemy 已上線且技術棧以 GCP／Firebase／Vertex AI 為主，Angel 評估「蠻適合升級」。

### 決議 2：申請前必須完成企業網域與帳號對齊

- **內容**：以 **`41.tech`** 為主軸——申請企業網域 → 開 Workspace → 官網與 Billing ID 網域一致 → 用新 GCP 帳號申請 Program。
- **原因**：現有 GCP 為個人 Gmail 開立，**審核不會過**；系統會比對官網網域與 Billing ID，且企業方案僅限企業網域。

### 決議 3：加速器路徑可再疊 $23K（總 $25K）

- **內容**：若年底入選指定加速器之一，可再申請 **$23K USD**，與 Start Tier 合計 **$25K**（使用期限兩年）。
- **原因**：Google 與四間加速器有合作，入選後由 Angel 協助 escalate 升級。

### 決議 4：現階段不急著透過代理商採購

- **內容**：在 Startup Program 申請完成前，**不必急著**透過中華電信等代理商買 GCP／AI 方案。
- **原因**：Program 點數可折抵 Vertex AI、VM、Firestore 等 GCP 服務；MongoDB 為第三方不在折抵範圍。代理商購買與 Program 可並存，但新創補助應優先申請。

---

## 💡 重要討論與觀察

### 主題：Program 四大資源

| 類別 | 內容 |
|------|------|
| **Financial** | 依 tier 核發雲端點數，直接折抵 GCP 帳單 |
| **Business** | 未使用 Workspace 者：一年免費 Workspace（含企業版 Gemini App、NotebookLM 企業版）；已有 Workspace 者可申請 **Google Maps $300–$1,000 USD** 點數 |
| **Technical** | Partner 技術團隊：顧問（架構／AI 目標規劃）+ 第一線除錯（無法排除再開 Support Ticket）；**排查不另收費**，外包開發／代維才另議 |
| **Community** | 每月 Startup 活動、LeaderConnect（VC／加速器／校友新創交流）、Partner 每月 GCP workshop |

### 主題：Tier 與點數（金額為 USD）

| Tier | 資格 | 點數 | 期限 |
|------|------|------|------|
| **Start** | 成立 ≤2 年、有自有解決方案 | $2K | 1 年 |
| **Ecosystem** | 入選指定加速器 | +$23K（合計 $25K） | 2 年 |
| **Scale** | Pre-A／A 輪募資 > $50 萬 | $100K–$350K | 依方案；AI 時代最高 $350K（含 $150K for AI） |

**指定加速器（四間）**：StarFab、Plug and Play、Edworks、Garage+、**AppWorks**（與 Google 有合作，入選後可 escalate）。

### 主題：FortyOneTech 現況（會議中簡報）

- **公司**：AI 股份有限公司（FortyOneTech / `41.tech`），2026 年 2 月經台北市政府核准成立。
- **團隊**：3 人（Cloudia、Justin、Paul）；理念為「盡可能用 AI 做出產品」。
- **產品 Elemy**：AI 客服（可匯入文件、人設、商品；已可 demo）；長期目標對齊 Google Next 案例（視覺／服飾查詢類 AI）。
- **技術棧**：GCP、Cloud Storage、MongoDB、**Vertex AI**、完整 **Firebase** 服務；未使用 GKE。LINE 已串接，規劃 FB、Threads。
- **成本**：GCP 每月約 **NT$5,000–6,000**；AI 主要走 Vertex，近期 **Gemini 回覆不穩** 曾評估他牌，仍希望留在 Google 生態。
- **其他**：Cloudia 為 GDG 志工；官網審核要件（公司介紹、團隊）Angel 初看無大問題；團隊照為 AI 圖（兼職成員不便曝光 LinkedIn）— 若審核需補件再以信件說明。

### 主題：折抵範圍

- **可折抵**：Vertex AI（含 Model Garden 連其他模型）、VM、Firestore 等 GCP 服務。
- **不可折抵**：MongoDB（第三方，需另付 MongoDB）。
- **建議**：Google 仍希望新創多用 Gemini；近期升級導致不穩，預期會改善。

### 風險

| 風險 | 說明 |
|------|------|
| 無企業網域 | 個人 Gmail 帳號**無法通過**審核，為當前最大卡關 |
| 團隊／LinkedIn 驗證 | 審核團隊在印度、重視真實新創；無 LinkedIn 或無法顯示全員經歷時可能要求補件 |
| 官網與 Billing 不一致 | 官網網域須與 GCP Billing ID 網域一致，否則系統階段會擋 |

---

## ✅ Action Items

| 負責人 | 任務 | 截止日 | 狀態 |
|--------|------|--------|------|
| Cloudia | 申請 **`41.tech` 企業網域**（與公司名稱一致） | 儘快 | 未開始 |
| Cloudia | 以企業網域申請 **Google Workspace** | 網域完成後 | 未開始 |
| Cloudia | 用 `41.tech` 開立**新 GCP 帳號**（另享約 $300 試用額度），取得 **18 碼 Billing ID** | Workspace 後 | 未開始 |
| Cloudia | 確認官網 **`41.tech` 網域**與 Billing、申請表一致 | 申請前 | 未開始 |
| Cloudia | 填寫 **Startup Program 申請表**，完成後**通知 Angel** | 帳號就緒後 | 未開始 |
| Cloudia | （建議）LinkedIn 經歷加註 FortyOneTech；或準備補件說明兼職／團隊照狀況 | 視審核 | 未開始 |
| Cloudia | 規劃年底加速器申請：**AppWorks、Garage+、StarFab** 等（入選後通知 Angel 升級 Ecosystem） | 2026 年底前 | 未開始 |
| Cloudia | （可選）需要時安排 Partner **15–30 分**技術介紹（含回覆速度優化顧問） | 入 Program 後 | 未開始 |
| Angel | 以 Email 整理申請流程與連結 | — | 進行中 |

---

## ⚠️ 待確認事項

| 項目 | 負責人 | 備註 |
|------|--------|------|
| 企業網域申請管道與費用 | Cloudia | 會議中提到企業網域「有點太貴」，需評估方案 |
| Workspace 一年免費是否適用 | Cloudia | 入 Program 後 **90 天內**新開 Workspace 帳號仍可申請一年免費（填 Google 表單申請 license） |
| 審核若因團隊資訊／LinkedIn 被退 | Cloudia / Angel | 以信件補件給審核團隊 |
| Gemini 穩定度與是否全面回 Vertex | Cloudia | 技術面持續觀察 |
| GDE 相關窗口 | Cloudia | Angel **不負責** GDE，為不同團隊；需另找 GDE 聯絡人 |
| Scale Tier（募資 > $50 萬後 $100K–$350K） | Cloudia | 中長期目標，本次未深入 |

---

## 📈 本次學到什麼

- Startup Program 的價值不只是點數，還包含 Workspace／Maps、Partner 第一線技術、每月社群與 VC 交流（LeaderConnect）。
- **企業網域是硬門檻**：個人 Gmail 開的 GCP 再怎麼用也無法申請，必須用公司網域重建帳號與 Billing 對齊官網。
- 路徑可分段：**先 $2K Start** → 入選加速器 **+$23K** → 募資後 **Scale $100K–$350K**，不必一次到位。
- 與代理商合作仍可扣 Program 點數，技術排查透過 Partner **不另收費**；外包開發才另計。
- 審核重「真實新創」：官網、Billing 網域、LinkedIn（若有）會交叉驗證；團隊呈現方式需有補件心理準備。
- 在 Program 申請完成前，不必急著為 AI 用量去談代理商採購；Vertex AI 與多數 GCP 服務都可吃補助點數。

---

## 🔄 下次會議

- **目標**：（待 Angel 寄出申請連結後）確認表單填寫、審核狀態；若需 Partner 技術介紹則安排時段。
- **時間**：未定（會議結束時無約下次，以 Email 非同步為主）

---

## 附錄：申請流程摘要

```text
1. 申請 41.tech 企業網域
2. 開 Google Workspace（企業信箱）
3. 用 41.tech 開新 GCP → 取得 Billing ID（約 $300 試用額度）
4. 確認官網網域 = Billing 網域
5. 填 Startup Program 申請表 → 通知 Angel
6. 審核約 1–2 天（Angel 可於系統查看進度）
7. 入 Program 後 90 天內可申請 Workspace 一年免費（若尚未使用）
8. 年底評估加速器 → 入選後通知 Angel 升級 Ecosystem (+$23K)
```

## 相關連結

- Angel Yu LinkedIn：（會議提供，請見邀請信）
- 原始逐字稿：[`20260528_GoogleStartUp說明.vtt`](./20260528_GoogleStartUp說明.vtt)

## 更新紀錄

- 2026-05-29：依 VTT 與會議記錄架構整理初版
