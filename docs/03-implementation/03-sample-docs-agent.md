# Part 3-3: サンプル1 - Docs Writer Agent

## 目的

Markdown や README の改善を専門にする最小構成の agent です。

---

## サンプル

参照ファイル: `.github/agents/docs-writer.agent.md`

```md
---
description: "Use this agent when updating README files, markdown documentation, guides, tutorials, or learning content."
tools: [read, edit, search]
user-invocable: true
---
```

---

## この agent が向く場面

- README の見出し整理
- 教材の文体統一
- Markdown の流れ改善
- 初学者向けのわかりやすい表現への修正

---

## 設計のポイント

1. `read`, `edit`, `search` だけに限定
2. コード変更は原則しない
3. 説明は短く、学習しやすさを優先

---

## 学び

このサンプルは、**1 role に絞る**ことの重要性を示しています。
最初の custom agent は、このくらい小さく始めるのが適切です。
