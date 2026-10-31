# bear-skills｜熊熊會怎麼說

模擬資訊單位主管的審閱視角：在你送出報告、簡報、簽案、提案、KPI 申請之前，先用主管的思維檢查一輪，取得修改建議、預判質疑與自我思考問題。

> **這是 AI 模擬，不代表任何主管本人的核定意見。** 內容依特定主管的決策偏好歸納，不同組織請自行調整。

## 使用方式

安裝後，在對話中輸入關鍵字並貼上內容：

```
熊熊會怎麼說？（貼上你的簡報大綱／提案／進度回報）
或簡稱：熊熊說／熊主管／熊求救／熊救命：（貼上內容）
```

建議一併提供：給誰看、何時要交、你自己的初步判斷。

你會得到：結論 → 做得好的地方 → 主要問題與改法 → 預判質疑與擬答 → 缺漏資訊 → 留給你思考的問題 → 下一步。每個判斷都標註依據層級：【主管確認】【文件記載】【AI推論】【待確認】。

## 安裝

把下面的 `<OWNER>` 換成本 repo 的 GitHub 帳號。

### Claude Code
```
/plugin marketplace add <OWNER>/bear-skills
/plugin install supervisor-review@bear-skills
```
更新：`/plugin marketplace update bear-skills`

### Codex
在 Codex 對話中使用內建 skill installer：
```
$skill-installer https://github.com/<OWNER>/bear-skills/tree/main/plugins/supervisor-review/skills/supervisor-review
```
安裝後重啟 Codex。手動安裝則是把 `plugins/supervisor-review/skills/supervisor-review` 資料夾複製到 `~/.codex/skills/`。

### 其他（跨工具）
```
npx skills add <OWNER>/bear-skills
```

### 手動安裝（任何支援 SKILL.md 的工具）
將 `plugins/supervisor-review/skills/supervisor-review/` 整個資料夾放入該工具的 skills 目錄，例如 Claude Code 的 `~/.claude/skills/`。

## 內容結構

```
plugins/supervisor-review/skills/supervisor-review/
├── SKILL.md                      流程與界線
└── references/
    ├── core-principles.md        核心判斷原則
    ├── review-lenses.md          8 種情境審閱檢核
    ├── case-library.md           匿名化案例
    ├── output-template.md        回覆格式
    └── calibration-notes.md      限制與待校準事項
```

## 限制
- 資料涵蓋有限，未討論過的領域，Skill 會明說是 AI 推論。
- 數字（如正確率門檻、天數）皆為情境舉例，不是固定標準。
- 不替業務單位撰寫其 KPI、SOP 或藍圖，只提供拆題方法與檢核問題。

## 授權
MIT License。
