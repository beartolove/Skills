# Skills

beartolove 的 AI Skills 集合。每個 Skill 都有獨立目錄，內含 `SKILL.md`（Claude Code、Codex 等支援 SKILL.md 格式的工具皆可使用）。

## Skill 列表

| Skill | 目錄 | 用途 | 觸發關鍵字 | 版本 |
|---|---|---|---|---|
| **supervisor-review** | [`supervisor-review/`](./supervisor-review) | 模擬資訊單位主管的審閱視角，替報告、簡報、簽案、提案、KPI 申請等提供審閱意見、預判質疑與自我思考問題 | 熊熊會怎麼說／熊熊說／熊主管／熊求救／熊救命 | 0.1.0 |

> 新增 Skill 時，請同步更新此表。

## 安裝

以下以 `supervisor-review` 為例，換成其他 Skill 時請替換名稱與目錄。

### Claude Code
```
/plugin marketplace add beartolove/Skills
/plugin install supervisor-review@beartolove-skills
```
更新：`/plugin marketplace update beartolove-skills`

### Codex
```
$skill-installer https://github.com/beartolove/Skills/tree/main/supervisor-review
```
安裝後重啟 Codex。手動安裝則將 `supervisor-review/` 資料夾複製到 `~/.codex/skills/`。

### 跨工具
```
npx skills add beartolove/Skills
```

### 手動安裝
把想用的 Skill 目錄整個複製到該工具的 skills 資料夾，例如 Claude Code 的 `~/.claude/skills/`。

> Codex 與 `npx skills` 的指令依各工具版本而定，若有出入請以該工具最新文件為準。

## 目錄結構

```
Skills/
├── README.md                    ← 本檔：Skill 列表與安裝說明
├── LICENSE
├── .claude-plugin/
│   └── marketplace.json         ← Claude Code marketplace 清單
└── <skill-name>/                ← 每個 Skill 一個獨立目錄
    ├── SKILL.md
    ├── README.md                ← 該 Skill 的使用說明
    └── references/              ← 該 Skill 的參考資料
```

## 新增 Skill 的方式
1. 在根目錄建立 `<skill-name>/`，放入 `SKILL.md`（含 `name`、`description`）與必要的 `references/`。
2. 補上該 Skill 的 `README.md`。
3. 在 `.claude-plugin/marketplace.json` 的 `plugins` 新增一筆（`source` 維持 `./`，`skills` 指向 `./<skill-name>`）。
4. 更新本檔的「Skill 列表」。
5. commit 並 push。

## 授權
MIT License。
