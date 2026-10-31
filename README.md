# Skills

beartolove 的 AI Skills 集合。每個 Skill 都有獨立目錄，內含 `SKILL.md`（Claude、ChatGPT、Codex 等支援 SKILL.md 格式的工具皆可使用）。

## Skill 列表

| Skill | 目錄 | 用途 | 觸發關鍵字 | 版本 |
|---|---|---|---|---|
| **bear-say** | [`bear-say/`](./bear-say) | 模擬資訊單位主管的審閱視角，替報告、簡報、簽案、提案、KPI 申請等提供審閱意見、預判質疑與自我思考問題 | 熊熊會怎麼說／熊熊說／熊主管／熊求救／熊救命 | 0.1.0 |
| **bear-audit** | [`bear-audit/`](./bear-audit) | 用資訊單位主管的決策思維（目的→時效→權責→先管理後技術→可決策）審查報告、提案、KPI、進度回報或待決情境 | 熊主管看看／請問熊主管／熊會怎麼說 | 0.1.0 |

> 新增 Skill 時，請同步更新此表。

## 安裝

以下以 `bear-audit` 為例，換成其他 Skill 時請替換名稱。

### Claude 網頁版／桌面版（claude.ai，Pro、Max、Team、Enterprise）
用 GitHub 網址直接加入：
1. 左側欄 **Customize** → **Plugins** 分頁。
2. **Add** → **Add marketplace** → **Add from a repository**。
3. 輸入 `beartolove/Skills`（或 `https://github.com/beartolove/Skills`）。
4. 在清單中找到 **bear-audit**，按安裝並啟用。

> 若組織限制可加入的 marketplace，請洽組織管理員。

### Claude Code
```
/plugin marketplace add beartolove/Skills
/plugin install bear-audit@beartolove-skills
```
更新：`/plugin marketplace update beartolove-skills`

### ChatGPT 網頁版
ChatGPT 目前以上傳 zip 安裝 Skill（Business、Enterprise、Edu 等工作區提供 Skills 功能）：
1. 到本 repo 的 [Releases](https://github.com/beartolove/Skills/releases) 下載 `bear-audit.zip`。
2. ChatGPT 左側欄 **Plugins** → **Skills** → **Create** → **Upload from your computer** → 選 `bear-audit.zip`。

沒有 Skills 功能的個人帳號：建立一個 GPT 或專案，把 `bear-audit/SKILL.md` 內容貼進「指令」，`references/` 內檔案上傳到「知識」。

### Codex
```
$skill-installer https://github.com/beartolove/Skills/tree/main/bear-audit
```
安裝後重啟 Codex。

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
│   └── marketplace.json         ← Claude marketplace 清單（Claude Code 與 claude.ai 共用）
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
5. commit 並 push；需要給 ChatGPT 用的話，在 Releases 附上該 Skill 的 zip。

## 授權
MIT License。
