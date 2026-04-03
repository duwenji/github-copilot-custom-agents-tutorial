# Part 0-4: Customization Map

## まず全体像をつかむ

GitHub Copilot のカスタマイズ要素は、似て見えても役割が異なります。

| 要素 | 役割 | 向く場面 |
|------|------|----------|
| `copilot-instructions.md` | リポジトリ全体の共通ルール | いつも守ってほしい方針 |
| `*.prompt.md` | 単発の定型依頼 | その都度使うテンプレート |
| `SKILL.md` | 再利用可能な手順 | ビルド、生成、検証など |
| `*.agent.md` | 役割を持つ専用 agent | docs担当、debug担当など |
| `MCP` | 外部システムやツール接続 | API、DB、社内情報参照 |

---

## 関係イメージ

```text
Repository rules
  └─ copilot-instructions.md

Reusable task templates
  ├─ prompts
  └─ skills

Role-based assistants
  └─ custom agents

External capabilities
  └─ MCP
```

---

## 覚え方

- **全体ルール** → `instructions`
- **単発テンプレ** → `prompt`
- **手順の再利用** → `skill`
- **役割の分離** → `agent`
- **外部接続** → `MCP`

この 5 つを分けて考えると、設計が整理しやすくなります。
