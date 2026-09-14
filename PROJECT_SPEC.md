# Draw Steel 繁體中文規則站：專案規格

> 本文件是此專案的**唯一主要規格來源（canonical project specification）**。
> 新的工作對話、AI agent 或協作者在修改翻譯、GitBook 或 repository 前，應先閱讀本文件。
>
> 規格版本：0.1  
> 最後更新：2026-09-14

## 1. 專案目標

建立並長期維護《Draw Steel》的繁體中文 GitBook 規則資料庫，服務實際遊玩的玩家與 Gamemaster。

優先順序：

1. 易讀性
2. 資訊層級清楚
3. 規則與翻譯一致性
4. 快速查找與交叉連結
5. 長期可維護性
6. 視覺華麗程度

網站的資訊架構應以「玩家現在想完成什麼／想查什麼」為核心，而不是照官方 PDF 章節一比一搬運。

## 2. 專案位置

- GitHub：`boyiad2110/ds-zh-tw`
- GitHub 主要分支：`main`
- GitBook Site：`Draw Steel 中文規則站`
- Google Drive 工作區：專案擁有者提供的 Draw Steel 工作雲端
- 舊 Notion：只可作為舊譯名與資訊架構參考，不是規則資料來源

## 3. 資料權威與優先順序

### 3.1 規則正典

Google Drive `Official Rules` 資料夾中的官方規則書 **Version 1.01b** 是規則事實的最高權威。

目前工作範圍包含核心規則，以及 V1 的 Beastheart 與 Summoner；但核心規則優先。

`DrawSteelRulesReferenceV1.pdf` 已排除，不可作為此專案的資料來源。

### 3.2 翻譯正典

Google Drive `Translation` 資料夾中的 Google Sheet 是繁體中文翻譯決策的權威來源。

基本原則：

> AI／協作者提出建議，Marc 定稿。

只有標記為「定稿」的術語、句型或翻譯決策，才可視為專案標準。

### 3.3 舊 Notion

舊 Notion 可用於：

- 找出 Marc 過去使用過的譯名，作為優先候選建議
- 參考過去的資訊分類與閱讀習慣

舊 Notion不可用於：

- 判定規則內容是否正確
- 補足官方 1.01b 沒有提供的規則資訊
- 在與 1.01b 衝突時覆蓋官方資料

### 3.4 GitHub 與 GitBook

- **GitBook**：主要內容編輯與閱讀介面
- **GitHub**：Git Sync 的版本歷史、可攜式 Markdown 原始資料與大量變更時的工程介面
- **Google Sheet**：翻譯決策與一致性管理

規則內容的事實來源仍是官方 PDF；GitBook 或 GitHub 上既有的中文內容不能反過來覆蓋官方來源。

## 4. 目標讀者與內容優先級

第一優先讀者是**玩家**。

內容排序原則：

1. 貫穿整本規則的底層資料
2. 玩家常用核心規則
3. 創角與角色選項
4. 角色成長與獎勵
5. 世界與背景資料
6. Director 專用內容
7. 額外職業與延伸內容

第一批底層資料優先處理：

1. Glossary
2. Skill
3. Condition
4. Action List

第一階段應先從官方規則書前段的 Glossary 建立種子術語庫，再逐步整理 Skill、Condition 與 Action List。

## 5. 翻譯原則

### 5.1 語言

- 目標語言：台灣繁體中文（zh-TW）
- 以台灣 TRPG 玩家自然、清楚、易讀的用語為優先
- 避免不必要的中國大陸用語或機翻腔
- 不為了追求字面對應而破壞中文規則句的清晰度

### 5.2 忠實度

「原文忠實」指規則語義忠實，不要求照搬原書排版或英文語序。

可以為了閱讀性：

- 拆分段落
- 加入小標題
- 使用表格
- 使用提示框
- 改成步驟
- 建立交叉連結
- 建立索引

但不得：

- 自行增加規則
- 移除會改變結果的條件
- 偷偷簡化例外
- 用舊版本或舊 Notion 補寫官方 1.01b 沒有的規則

### 5.3 中英並列

專有規則詞第一次在適當上下文出現時，原則上採：

`中文（English）`

後續正文通常只使用已定稿的中文譯名。

英文原詞仍應保留在術語資料與搜尋／索引用途，以利核對官方來源。

### 5.4 翻譯審核粒度

- **術語與重要固定句型**：先提案，再由 Marc 定稿
- **一般段落**：不需要逐句等待核准；在既有術語與 Translation Memory 的約束下完成整頁後，再由 Marc 於 GitBook Change Request 審閱

避免把所有完整文章拆成逐句 Sheet 審核，降低行政成本。

## 6. Translation Google Sheet 規格

Translation Sheet 應使用單一主要 Spreadsheet，至少包含以下六個分頁。

### 6.1 `01 術語表`

用途：管理單字、專有名詞、規則名稱與標準譯名。

建議欄位：

- Term ID
- English
- 繁體中文
- 類型
- 狀態（提案／討論中／定稿／停用）
- 舊 Notion 譯名
- 首次來源
- 翻譯理由
- 備註
- 定稿日期
- 原文版本

規則：只有「定稿」項目可視為專案標準譯名。

### 6.2 `02 Translation Memory`

用途：管理反覆出現的規則句型、固定表達、語序與翻譯習慣，確保整本規則的中文句型一致。

建議欄位：

- TM ID
- English Source Pattern
- Approved zh-TW
- 類型
- 使用條件
- 可變欄位／placeholder
- 實際例句
- 來源
- 狀態
- 備註
- 原文版本

TM 應優先保存可重用模式，例如包含 `{target}`、`{damage}`、`{condition}` 等可變欄位的句型，而不只是單一孤立句子。

翻譯優先順位：

> 官方原文語義 > 已定稿術語 > 已定稿 Translation Memory > 一般翻譯習慣

TM 是優先翻譯模式，不是機械取代規則；語境或規則邏輯不同時不得硬套。

### 6.3 `03 待確認翻譯`

用途：只收錄真正需要 Marc 判斷的翻譯問題，例如：

- 一詞多譯
- 語氣或句型選擇
- 雙關
- 特殊規則名稱
- 新舊譯法衝突
- 現有術語或 TM 無法直接套用的情況

建議欄位：

- 原文
- 建議譯法
- 替代方案
- 上下文
- 來源
- 說明
- Marc 決定
- 狀態

### 6.4 `04 頁面進度`

用途：追蹤 GitBook 頁面的工作狀態。

建議欄位：

- GitBook 頁面
- 官方來源
- 階段
- 術語檢查
- 翻譯
- 校對
- Marc 審閱
- 發布

建議主流程：

`未開始 → 翻譯中 → 待審 → 已定稿 → 已發布`

### 6.5 `05 來源對照`

用途：建立官方 PDF 位置與 GitBook canonical page 的雙向追蹤，方便版本更新。

建議欄位：

- Source file
- Section
- 官方頁碼／範圍
- GitBook page
- 備註
- 原文版本

### 6.6 `06 決策紀錄`

用途：記錄跨頁面、跨章節的 editorial / localization 決策，例如：

- 中英首次並列政策
- 標點與數字格式
- Ability／Condition 等資料的固定排版模式
- 搜尋關鍵字政策
- 大型譯名變更與原因

## 7. Glossary 工作方式

Glossary 不先當作一篇普通文章從頭翻到尾，而應先轉成結構化的種子術語庫。

處理順序：

1. 從官方 1.01b Glossary 抽取詞條、簡短定義與 cross-reference
2. 按規則類型分類
3. 查舊 Notion 是否有候選舊譯名
4. 依高度相關的詞群，每批約 10–20 個提出譯名建議
5. Marc 定稿
6. 將定稿術語寫入 `01 術語表`
7. 翻譯定義時，將高重用句型整理進 `02 Translation Memory`
8. 再進入 Skill、Condition、Action List 的正式整理

不需要一次要求 Marc 審核整份 Glossary。

## 8. GitBook 資訊架構原則

GitBook 是查詢工具，不是官方 PDF 的鏡像。

網站應優先回答玩家的實際需求，例如：

- 我要怎麼做某件事？
- 這個 Condition 是什麼？
- 這個 Action 怎麼使用？
- 這個 Skill 的用途是什麼？
- 某項角色能力引用了哪條規則？

同一份規則應維持一個 canonical page；不同入口使用導航、索引與交叉連結指向同一頁，不複製多份內容。

仍應保留「原書章節／來源索引」，供來源核對與版本更新使用。

### 初期內容骨架

正式開始底層資料時，第一批公開內容預計圍繞：

- 首頁
- 規則資料庫
  - 術語表
  - Skill
  - Condition
  - Action List
- 關於本站
  - 資料來源與版本
  - 翻譯與授權
  - 更新紀錄

這是內容規劃，不代表在尚未建立內容前要先建立空白頁或虛構 repository 目錄。

## 9. GitBook / GitHub 工作流

### 9.1 日常內容編輯

日常主要使用 GitBook 視覺化編輯器。

建議流程：

1. 依官方 PDF 與 Translation Sheet 工作
2. 在 GitBook Change Request 編輯與預覽
3. Marc 審閱並修改
4. Merge Change Request
5. Git Sync 將內容同步到 GitHub `main`
6. GitHub 保存 Markdown 與版本歷史

### 9.2 大量變更

以下情況可改從 GitHub branch / Pull Request 操作：

- 全站術語更名
- 大量機械式格式調整
- 官方版本升級造成的大規模 diff
- 其他 GitBook 視覺編輯器不適合處理的批次工作

### 9.3 基礎設施設定

初始 repository / Git Sync 基礎設施設定可依 Marc 明確指示直接修改 `main`，不必建立 Issue 或 PR。

## 10. 授權與公開政策（專案擁有者意圖）

本站可以公開。

Marc 對自己原創的繁體中文翻譯表達、整理與其他原創內容保留相應權利；MCDM 的原始著作與智慧財產權仍屬其權利人。

目前希望採用的使用政策方向：

- **非商業遊玩**：可自由使用本站作為遊戲規則參考
- **收費團／商業主持**：若使用本站作為中文規則參考，主持者必須合法持有相應的官方原版規則產品
- **翻譯成果的商業出版或其他商業重製**：不包含在前述允許範圍，需另外取得 Marc 授權

最終公開法律文字尚未定稿；正式發布前需確認與適用的 MCDM Creator License 及其他法律要求相容。不得把本節當作替 MCDM 授權其權利的文件。

## 11. 工作階段

### Phase 0 — 基礎設施

- 建立並維護本規格文件
- 建立 Translation Google Sheet 六個分頁
- 設定 GitBook Site Git Sync
- 建立最小可用的 GitBook 結構

### Phase 1 — 底層翻譯資料

1. Glossary 種子術語庫
2. Skill
3. Condition
4. Action List

### Phase 2 — 核心玩家規則

在底層術語與 TM 足夠穩定後，再逐步處理 Tests、Combat、Negotiation、創角與角色選項等玩家核心內容。

### Phase 3 — 其他內容

依玩家需求與維護成本擴充 Director 內容、Beastheart、Summoner 等。

## 12. 未定稿事項

下列內容尚未視為永久決策：

- 個別 Draw Steel 專有名詞的繁體中文譯名
- 最終完整 GitBook sitemap
- 最終公開授權／使用條款法律文字
- 未來官方版本升級的 migration 細節

不得因為本文件使用 `Skill`、`Condition`、`Action List` 等英文工作名稱，就推定其繁中譯名已定稿。

## 13. 給未來 AI／協作者的操作規則

在開始工作前：

1. 先讀本文件
2. 需要翻譯時，再讀 Translation Google Sheet 中已定稿的術語與 TM
3. 需要規則事實時，只以指定的官方 1.01b 規則 PDF 為主要來源
4. 舊 Notion 只能作候選譯名／資訊架構參考
5. 不擅自把候選譯名升級為定稿
6. 不因為某個中文段落已存在 GitBook／GitHub 就假設它比官方 PDF 更權威
7. 發現來源衝突、版本不明或語義不確定時，明確標示問題，不自行補完
8. 優先維護一致性與可查找性，而不是模仿原書視覺版面
