# Part 2-3: どれを選ぶべきか

## シンプルな判断フロー

```text
共通ルールを書きたい？
  └─ はい → `copilot-instructions.md`

単発テンプレを残したい？
  └─ はい → `prompt`

役割を持つ専用アシスタントがほしい？
  └─ はい → `Custom Agent`

標準手順を再利用したい？
  └─ はい → `Skill`

外部システムやAPIに触れたい？
  └─ はい → `MCP`
```

---

## よくある組み合わせ

### パターン1: 小さく始める
- `copilot-instructions.md`
- `docs-writer.agent.md`

### パターン2: 手順も共有する
- `copilot-instructions.md`
- `debug-helper.agent.md`
- `SKILL.md`

### パターン3: 実務連携まで広げる
- `copilot-instructions.md`
- `repo-maintainer.agent.md`
- `MCP`

---

## おすすめの始め方

初学者なら次の順が安全です。

1. `copilot-instructions.md`
2. 小さな `Custom Agent`
3. 必要なら `Skill`
4. 最後に `MCP`
