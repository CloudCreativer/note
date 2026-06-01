---
program: Claude Code in Action
course: What is Claude Code?
topic: Introduction
source: 課程筆記（Claude Code in Action）
date: 2026-06-01
status: done
tags:
  - claude-code
  - coding-assistant
  - tool-use
---

# Introduction — 什麼是 Claude Code？

## Insight

Claude Code 不是「會寫程式的聊天機器人」，而是 **模型 + Tool Use 迴圈** 的可擴充開發助理；成效取決於脈絡是否精準、對話是否控管，以及能否用 MCP、Hooks、GitHub Actions、SDK 把自動化嵌進既有流程。

## Input

- **來源**：Claude Code in Action 課程筆記

### What is a Coding Assistant?

Coding Assistant = 使用語言模型來撰寫程式碼並完成開發任務的工具

核心流程：
1. 接收任務（例如：根據錯誤訊息修 bug）
2. 語言模型蒐集脈絡（讀取檔案、理解程式庫）
3. 擬定解決問題的計畫
4. 採取行動（更新檔案、執行測試）

關鍵限制：語言模型只能處理文字輸入／輸出——無法直接讀取檔案、執行指令，或與外部系統互動。

Tool Use System = 讓語言模型能執行動作的方法：
- 助理在使用者請求後附加指示
- 指示指定動作的格式化回應（例如：「read file: filename」）
- 語言模型以格式化的動作請求回應
- 助理執行實際動作（讀取檔案、執行指令）
- 將結果送回語言模型以產生最終回應

Claude 模型優勢：
- 相較其他語言模型，具備更優秀的工具使用能力
- 更擅長理解工具函式，並組合它們以完成複雜任務
- Claude Code 可擴充——容易新增新工具
- 透過直接程式碼搜尋，而非將程式庫送到外部伺服器建立索引，安全性更好

要點：
- 所有語言模型在非文字生成任務上都需要 tool use
- Tool use 的品質直接影響 coding assistant 的成效
- Claude 在 tool use 上的優勢，使其能適應開發上的變化

### Claude Code in Action

Claude Code = 具備以工具為基礎的能力、用於程式任務的 AI 助理

預設工具 = 檔案讀寫、指令執行、基本開發操作

效能優化示範：Claude 分析 Chalk JavaScript 函式庫（下載量第 5 名的 JS 套件，每週 4.29 億次下載）。使用 benchmark、profiling 工具、建立 todo 清單、找出瓶頸、實作修復。結果 = 吞吐量提升 3.9 倍。

資料分析示範：Claude 使用 Jupyter notebook 對影音串流平台 CSV 資料進行 churn 分析。迭代執行程式碼儲存格、檢視結果，並根據發現客製化後續分析。

工具可擴充性：Claude Code 可接受新的工具集。範例使用 Playwright MCP server 進行瀏覽器自動化。Claude 開啟瀏覽器、截圖、更新 UI 樣式，並迭代設計改進。

GitHub 整合：Claude Code 在 GitHub Actions 中執行，由 pull request／issue 觸發。取得 GitHub 專用工具（留言、commit、建立 PR）。

基礎設施審查範例：以 Terraform 定義的 AWS 基礎設施，含 DynamoDB 資料表與 S3 bucket，並與外部夥伴共用。開發者在 Lambda 函式輸出中加入使用者 email。Claude Code 在 pull request 審查中，透過分析基礎設施流程並識別外部資料共享，自動偵測到 PII 外洩風險。

核心原則：Claude Code = 透過工具擴充而非固定功能，隨團隊需求成長的彈性助理。

### Adding Context

脈絡管理 = 對 Claude Code 成效至關重要。過多無關資訊會降低表現。

/init 指令 = 首次執行時分析整個程式庫，建立含專案摘要／架構／關鍵檔案的 Claude.md。檔案內容會包含在每次請求中。

三種 Claude.md 檔案類型：
- 專案層級 = 與團隊共用，提交至版控
- 本機層級 = 個人指示，不提交
- 機器層級 = 適用所有專案的全域指示

Memory 模式（# 符號）= 以自然語言請求智慧編輯 Claude.md

@ 符號 = 在請求中提及特定檔案以納入脈絡，提供精準脈絡，而非讓 Claude 自行搜尋

最佳實務 = 在 Claude.md 中引用關鍵檔案（如資料庫 schema），使其始終可作為脈絡使用

目標 = 提供剛好足夠的相關資訊，讓 Claude 有效完成任務

### Making Changes

Claude Code 變更管理：

截圖整合 = 在 macOS 上使用 Control-V（不是 Command-V）貼上截圖，協助 Claude 理解要修改的特定 UI 元素

效能提升模式：
- Plan Mode = 按 Shift + Tab 兩次，讓 Claude 在執行前研究更多檔案並建立詳細實作計畫
- Thinking Mode = 以如「Ultra think」等片語觸發，為複雜邏輯提供延伸推理預算

Planning 與 Thinking 用法：
- Planning = 處理廣度，適合需要廣泛理解程式庫的多步驟任務
- Thinking = 處理深度，適合棘手邏輯或除錯特定問題
- 複雜任務可合併使用
- 兩者都會消耗額外 token（需考慮成本）

Git 整合 = Claude Code 可 stage／commit 變更並撰寫描述性 commit message

關鍵工作流程：對問題區域截圖 → 以 Control-V 貼上 → 描述期望變更 → 複雜任務可選用 Plan／Thinking 模式 → 審查並接受實作

### Controlling Context

脈絡控制技巧：

Escape = 在 Claude 回應中途停止，以重新導向對話流程。按一次即可中斷目前輸出。

Escape + Memory = 強大的錯誤預防。停止 Claude，用 # 快捷鍵加入關於重複錯誤的 memory，以避免再次發生。

Double Escape = 對話回溯。顯示所有先前訊息，可跳回較早時間點，同時保留相關脈絡並跳過無關的除錯／來回討論。

Compact 指令 = 摘要整段對話歷史，同時保留 Claude 對目前任務已學到的知識。適用於 Claude 已累積專業度但對話已雜亂時。

Clear 指令 = 刪除整段對話歷史以重新開始。適用於切換到完全無關的任務時。

主要效益：維持專注、減少干擾性脈絡、保留相關知識、防止重複錯誤。對長對話與任務切換最有效。

### Custom Commands

Custom Commands = 在 Claude Code 中透過斜線存取的使用者自訂自動化指令

位置 = 專案目錄下的 .Claude/commands/ 資料夾
檔名 = 檔名即成為指令名稱（audit.md 建立 /audit 指令）
啟用 = 建立指令檔後需重新啟動 Claude Code

指令結構 = 含 Claude 要執行之指示的 markdown 檔
參數 = 在指令文字中使用 $arguments 占位符以接受執行時參數
參數類型 = 任意字串（檔案路徑、描述文字等）

使用情境 = 自動化重複任務，如相依性稽核、測試產生、漏洞修復
執行 = 在 Claude Code 介面輸入 /commandname，可選擇性加上參數字串

### Extending Claude Code with MCP Servers

MCP servers = 擴充 Claude Code 能力的外部工具，可在本機或遠端執行。

Playwright MCP server = 熱門 server，讓 Claude 控制瀏覽器以進行網頁自動化。

安裝：終端機指令 `claude mcp add [name] [start-command]` 可將 MCP server 加入 Claude Code。

權限管理：初次使用工具需核准。在 settings.local.json 的 allow 陣列加入 "MCP__[servername]" 可自動核准。

實務範例：Claude 使用 Playwright 瀏覽 localhost:3000、產生 UI 元件、分析樣式品質，再根據視覺回饋自動更新產生提示。

結果：自動化提示精煉大幅改善元件樣式，展現 MCP servers 能解鎖複雜開發工作流程。

主要效益：MCP servers 讓 Claude 執行涉及外部系統的複雜多步驟任務，從程式編輯擴展到完整開發自動化。

### Github Integration

Claude Code GitHub 整合 = 官方整合，讓 Claude 在 GitHub Actions 內執行

設定流程：
- 執行 "/install GitHub app" 指令
- 在 GitHub 安裝 Claude Code app
- 加入 API key
- 自動產生的 pull request 會加入兩個 GitHub actions

預設 Actions：
1. Mention 支援 = 在 issue／PR 中 @Claude 指派任務
2. PR review = 新 pull request 自動程式碼審查

自訂：
- Actions 可透過 .github/workflows 目錄中的設定檔自訂
- Custom instructions = 直接傳給 Claude 的脈絡／指示
- MCP server 整合 = 讓 Claude 存取外部工具（如 Playwright 瀏覽器自動化）

權限需求：
- 必須在 actions 中明確列出 Claude Code 的所有權限
- MCP server 工具需個別列出權限（無捷徑）

使用情境範例：
- 整合 Playwright MCP server 進行瀏覽器測試
- Claude 執行前啟動開發伺服器
- Claude 可在瀏覽器造訪 app、測試功能、建立檢查清單
- 提供自動化測試與 issue 驗證

主要功能 = 以 mention 指派任務、自動 PR 審查、可自訂工作流程、MCP server 整合以擴充功能

### Introducing Hooks

Hooks = 在 Claude 執行工具之前／之後執行的指令

Pre-tool use hooks = 在工具執行前執行，可檢查並阻擋工具操作，向 Claude 傳送錯誤訊息
Post-tool use hooks = 在工具執行後執行，執行後續操作，向 Claude 提供回饋

設定 = 透過手動編輯或 /hooks 指令加入 Claude 設定檔（全域／專案／個人）

Hook 結構 = 兩個區段（pre-tool use、post-tool use），各有 matcher（指定要鎖定的工具）與要執行的 command

範例用途 = 建立檔案後自動格式化、編輯後執行測試、阻擋檔案存取、程式碼品質檢查、型別檢查

Hook 指令 = 接收工具呼叫細節，可透過阻擋或回饋機制修改 Claude 的工作流程

### Defining Hooks

**Hooks 概覽**
Hooks = 在工具呼叫執行前／後攔截並控制的機制

**Hook 類型**
Pre-tool use hook = 在工具呼叫前執行，可阻擋執行
Post-tool use hook = 在工具呼叫後執行，無法阻擋

**Hook 實作流程**
1. 選擇 hook 類型（pre 或 post）
2. 識別要監控的目標工具名稱
3. 撰寫 command 以透過 stdin 以 JSON 接收工具呼叫資料
4. 解析含 tool_name 與 input 參數的 JSON
5. 以適當的 exit code 表示意圖

**Exit Codes**
Exit 0 = 允許工具呼叫繼續
Exit 2 = 阻擋工具呼叫（僅 pre-tool use）
標準錯誤輸出 = 阻擋時傳給 Claude 的回饋訊息

**工具呼叫資料結構**
JSON 物件包含：
- tool_name（例如："read"、"grep"）
- input 參數（例如：file_path）

**常見使用情境**
透過監控可存取檔案內容的 "read" 與 "grep" 工具來阻擋檔案存取

**工具探索**
直接向 Claude 詢問可用工具名稱清單，而非背誦

---

Hooks = 透過在工具呼叫前／後執行自訂指令，控制 Claude 工具使用的機制

Pre-tool use hook = 在工具呼叫前執行，可用 exit code 2 阻擋
Post-tool use hook = 在工具呼叫後執行，無法阻擋

Hook 流程：
1. Claude 將工具呼叫資料以 JSON 經 stdin 傳給你的 command
2. Command 解析含 tool_name 與 input 參數的 JSON
3. Command 以 code 0（允許）或 2（僅 pre-hooks 可阻擋）結束
4. Exit code 2 將 stderr 輸出作為回饋傳給 Claude

工具呼叫資料格式 = 含工具名稱與 input 參數的 JSON 物件

會讀取檔案的常見工具 = "read" 工具與 "grep" 工具

Hook 使用情境範例 = 監控針對該路徑的 read／grep 工具，阻擋 Claude 讀取敏感 .env 檔

設定 = 在專案中定義 command，相關工具呼叫發生時 Claude 會自動執行

### Implementing a Hook

**自訂 Hook 實作**

Hook 目的 = 防止 Claude 讀取 .env 檔案內容

**設定**
- 位置 = .clod/settings.local.json
- Hook 類型 = pre-tool use hook（執行前阻擋）
- Matcher = "read|grep"（管線符號分隔工具名稱）
- Command = "node ./hooks/read_hook.js"

**實作細節**
- Hook 經 stdin 接收 JSON 物件，包含：session ID、工具名稱、工具 input、檔案路徑
- 邏輯：若檔案路徑包含 ".env" → 以 code 2 結束並將錯誤記錄到 stderr
- 錯誤輸出寫入 stderr 以回饋 Claude
- Exit code 2 = 阻擋操作

**關鍵需求**
- 修改 hook 後必須重新啟動 Claude
- Console.error() 透過 stderr 將回饋傳給 Claude
- Hook 適用於 read 與 grep 工具
- 檔案路徑檢查：tool_input.path 並有 fallback 處理

**測試結果**
- 成功阻擋 .env 檔案存取
- Claude 能識別被 read hook 阻擋
- 適用於 read 與 grep 操作

---

**Hook 實作流程：**

Hook = 攔截並控制 Clod 中工具使用的自訂腳本

**設定（settings.local.json）：**
- Pre-tool use hooks = 工具執行前執行
- Post-tool use hooks = 工具執行後執行
- Matcher = 指定要攔截的工具（例如："read|grep"）
- Command = 符合工具被呼叫時執行的腳本

**實作步驟：**
1. 在 settings.local.json 加入含 matcher 與 command 的 hook 設定
2. 建立 hook 腳本（例如 read_hook.js），經 stdin 接收 JSON input
3. JSON input 包含：session ID、工具名稱、工具 input、檔案路徑
4. 腳本邏輯：檢查檔案路徑是否包含 ".env"
5. 若偵測到要阻擋的檔案：console.error() 訊息 + process.exit(2)
6. Exit code 2 = 阻擋工具執行

**關鍵技術細節：**
- Hook 腳本從 stdin 以 JSON 接收工具資料
- 使用 console.error() 將回饋傳給 Clod（記錄到 stderr）
- 修改 hook 後必須重新啟動 Clod
- Hook 套用至所有指定工具（read、grep 等）
- 透過 tool_input.path 做 fallback 路徑檢查以相容

**結果：** 成功防止 Clod 讀取 .env 檔，並對被阻擋的操作提供使用者回饋。

### Useful Hooks!

**Claude Code 專案實用 Hooks**

**問題**：Claude Code 常漏掉型別錯誤並產生重複程式碼，尤其在較大專案中。

**Hook 1：TypeScript 型別檢查 Hook**
- **目的**：檔案編輯後立即捕捉型別錯誤
- **實作**：透過 post-tool-use hook，在 TypeScript 檔案變更後執行 `tsc --no-emit`
- **流程**：偵測型別錯誤 → 將錯誤回饋給 Claude → Claude 自動修復呼叫端
- **效益**：函式簽名變更時，避免呼叫端損壞
- **可調整**：適用任何有型別檢查器的語言；無型別語言可用測試代替

**Hook 2：重複程式碼防護 Hook**
- **問題**：Claude 會建立新查詢／函式而非重用既有程式碼，複雜任務尤甚
- **解法**：啟動另一個 Claude 實例審查特定目錄（例如 queries 資料夾）的變更
- **流程**：
  1. 偵測對監控目錄的編輯
  2. 透過 TypeScript SDK 啟動新 Claude 實例
  3. 將新程式碼與既有程式碼比對
  4. 若發現重複，以 code 2 結束並提供回饋
  5. 原始 Claude 收到回饋並重用既有程式碼
- **取捨**：額外時間／成本 vs 更乾淨的程式庫
- **建議**：僅監控關鍵目錄以降低開銷

**重點**：Hooks = 自動化回饋迴圈，透過額外檢查並將結果回饋給 Claude 自我修正，以捕捉 Claude Code 常見弱點（型別錯誤、程式碼重複）。

---

TypeScript 型別檢查 Hook：
- 問題：Claude 修改函式簽名但未更新呼叫端，導致型別錯誤
- 解法：TypeScript 檔案編輯後執行 `tsc --no-emit` 的 post-tool-use hook
- 流程：偵測型別錯誤 → 回饋給 Claude → Claude 自動修復呼叫端
- 適用任何有型別檢查器的語言；無型別語言可用測試代替

Query 去重 Hook：
- 問題：Claude 建立重複 SQL 查詢／函式而非重用既有程式碼，複雜任務尤甚
- 原因：聚焦任務表現良好，但包裝／複雜任務會讓 Claude 失焦
- 解法：Hook 監控查詢目錄變更 → 啟動另一 Claude 實例 → 審查重複 → 回饋給原始 Claude
- 流程：queries/ 檔案編輯 → 次要 Claude 分析既有查詢 → 回報重複 → 主要 Claude 移除重複並重用既有程式碼
- 取捨：額外時間／成本 vs 更少重複、更乾淨的程式庫
- 建議：僅套用於關鍵目錄以降低開銷

兩者皆使用 post-tool-use 模式，對 Claude 的編輯提供即時回饋與修正。

### The Claude Code SDK

Claude Code SDK = Claude Code 的程式化介面，含 CLI、TypeScript 與 Python 函式庫。包含與終端機版本相同的工具。

主要使用情境 = 整合至較大的 pipeline／工作流程，為既有流程加入智慧。

預設權限 = 唯讀（檔案、目錄、grep 操作）。寫入權限需透過 options.allowTools 陣列或 .Claude 目錄設定手動設定。

SDK 執行會顯示本機 Claude Code 與語言模型之間的原始對話，最終回應為最後一則訊息。

關鍵實作模式 = 在 query 呼叫時於 options.allowTools 指定如 "edit" 等工具以加入寫入權限。

最適合 = 既有專案內的輔助指令、腳本與 hook，而非獨立使用。

---

Claude Code SDK = 透過 CLI、TypeScript 或 Python 函式庫使用 Claude Code 的程式化介面。與終端機版本工具相同。

主要使用情境 = 整合至較大的 pipeline／工作流程，為流程加入智慧。

主要特性：
- 預設權限 = 唯讀（檔案、目錄、grep 操作）
- 寫入權限 = 須透過 query 選項或設定檔手動啟用
- 原始對話輸出 = 顯示本機 Claude Code 與語言模型之間逐則訊息交換

最佳應用 = 既有專案內的輔助指令、腳本、hook，而非獨立使用。

輸出格式 = 對話訊息，最後一則為 Claude 的最終回應。

## Translation

| 原文 / 課程說法 | 我的理解 |
|-----------------|----------|
| Language models only process text | 模型只有「腦」；讀檔、跑 terminal、開瀏覽器都要靠外面的助理代執行，再塞回對話 |
| Tool Use System | 模型與環境之間的協定：模型用固定格式「點菜」，助理上菜（執行結果），循環直到任務完成 |
| Claude Code grows through tool expansion | 核心能力固定，真正差異在你能插多少工具（MCP、GitHub、自訂 hook） |
| Context management is critical | 不是給越多越好；要像調味——CLAUDE.md、@ 檔案、# memory 都是控制「上菜份量」 |
| Plan Mode vs Thinking Mode | Plan 先廣搜再動手（廣度）；Thinking 慢慢想難題（深度）；複雜任務可併用，但要付 token |
| Escape / Double Escape / Compact / Clear | 長對話的「方向盤」：中斷、回溯、精簡、重開，避免舊脈絡把新任務帶偏 |
| Custom Commands | 把常做流程寫成 `/指令`，等於給團隊的可版控 SOP |
| MCP servers | 外掛式能力包；Playwright 讓 AI 能「看見」UI，而不只猜 DOM |
| Hooks (pre / post) | 在工具執行前後加守門員：可擋 `.env`、可跑 `tsc`、甚至叫第二個 Claude 查重複碼 |
| Claude Code SDK | 把同一套工具鏈嵌進 CI、腳本、hook；預設唯讀，寫入要明確開權限 |

## Why

| 以前覺得 | 現在覺得 |
|----------|----------|
| AI 寫程式 = 對話框產生程式碼，複製貼上 | 實用助理 = **讀檔 → 計畫 → 改檔 → 跑測試** 的迴圈；單次生成品質遠不如完整迴圈 |
| 模型越聰明，開發體驗越好 | **Tool use 品質**、脈絡管理、事後檢查（hook）同樣關鍵，有時比「會寫」更重要 |
| 把 repo 給 AI 就要整包上傳或建索引 | 可用本機工具搜尋 + 精準 @ 檔案；敏感專案要搭配 hook 擋 `.env` 等 |
| Claude Code 功能寫死 | 是平台：MCP 擴能力、Commands 固化流程、Hooks 補弱點、SDK 進 pipeline |
| 長對話越久越強 | 對話太長會雜訊變多；要會用 Esc、compact、clear，必要時用 # 寫入 memory 防再犯 |
| PR 審查只能靠人 | GitHub Actions 裡的 Claude 可自動 review，甚至用 Playwright 實際點 app 驗證 |
| 型別錯誤、重複 query 只能事後人工修 | Post-hook 跑 `tsc` 或第二實例查重，可把錯誤即時打回給 Claude 自我修正 |

## Action

- [ ] 在專案執行 `/init`，建立並提交專案層級 `CLAUDE.md`；在裡面 `@` 或引用 schema、架構說明等關鍵檔
- [ ] 用一個真實小 bug 跑完整流程：描述問題 → 觀察讀檔／改檔／跑指令 → 必要時開 Plan Mode
- [ ] 練一次脈絡控制：長對話中用 **Esc** 中斷、**Double Esc** 回溯、或 `/compact` 精簡
- [ ] 在 `.claude/commands/` 建立一個團隊會重複用的自訂指令（如 `/audit`），並用 `$arguments` 測參數
- [ ] 選一個 MCP（如 Playwright）用 `claude mcp add` 安裝；在 `settings.local.json` 設定允許後試 localhost UI 任務
- [ ] 實作 pre-hook 阻擋讀取 `.env`（`read|grep` + `exit 2`）；改完設定後重啟 Claude Code
- [ ] 若專案為 TypeScript：加 post-hook 在編輯後跑 `tsc --no-emit`，確認錯誤能回饋給 Claude
- [ ] 若有 GitHub repo：跑 `/install GitHub app`，讓新 PR 觸發自動 review（可先小 repo 試）
- [ ] 瀏覽 SDK 文件，規劃一個唯讀腳本（如自動摘要 PR diff）再視需要開 `edit` 權限

## Question

- 本機 Claude Code 的 `CLAUDE.md` 與 GitHub Actions 裡的 custom instructions 如何同步，PR review 才會和本機開發一致？
- Post-hook 跑 `tsc` 或啟動第二個 Claude 查重：在大型 monorepo 上延遲與成本可接受嗎？該監控哪些目錄？
- MCP 工具權限在 CI 要逐項列出——有沒有團隊級範本或最小權限清單可複用？
- Plan Mode 與 Thinking Mode 同時開時，什麼任務類型最划算？有無建議的 token 預算做法？
- SDK 預設唯讀：在我目前的 Flutter / 後端專案裡，第一個值得嵌入 pipeline 的 use case 是什麼？
- Cursor 與 Claude Code 的 tool use、CLAUDE.md、hook 能否共用同一套團隊規範？

## 更新紀錄

- 2026-06-01：依《學習筆記架構》建立初版（Introduction 模組）
- 2026-06-01：Input 改為課程筆記忠實中文譯文
- 2026-06-01：補齊 Insight、Translation、Why、Action、Question
