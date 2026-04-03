# Part 2-2: Skills / MCP との違い

## ざっくり整理

- **Skill**: 作業手順をまとめる
- **Custom Agent**: 役割と振る舞いを持たせる
- **MCP**: 外部ツールやデータにアクセスする仕組み

---

## 比較表

| 観点 | Custom Agent | Skill | MCP |
|------|--------------|-------|-----|
| 主目的 | 役割の定義 | 手順の再利用 | 能力や外部接続の提供 |
| 置き場所 | `.github/agents/` | `.github/skills/` | MCP server / config |
| 中心要素 | persona, constraints, tools | procedure, docs, assets | tools, resources, external systems |
| 向く例 | docs担当、debug担当 | build手順、生成フロー | DB検索、API操作、社内情報参照 |

---

## 組み合わせもできる

実務では、これらは競合ではなく**補完関係**です。

例:
- Agent が役割を担当する
- Skill が標準手順を提供する
- MCP が外部情報やツール実行を支える

---

## 判断基準

1. 役割を分けたい → `Custom Agent`
2. 毎回同じ手順を再利用したい → `Skill`
3. 外部システムに触れたい → `MCP`
