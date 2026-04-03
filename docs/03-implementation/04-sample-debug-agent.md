# Part 3-4: サンプル2 - Debug Helper Agent

## 目的

エラー調査、失敗原因の切り分け、検証を支援する agent です。

---

## サンプル

参照ファイル: `.github/agents/debug-helper.agent.md`

```md
---
description: "Use this agent when investigating bugs, runtime errors, broken builds, failing tests, or root-cause analysis."
tools: [read, search, execute]
user-invocable: true
---
```

---

## この agent が向く場面

- テスト失敗の原因調査
- ビルドエラーの切り分け
- 実行時例外の確認
- 根本原因を整理したいとき

---

## 設計のポイント

1. まず再現・確認を重視する
2. 推測より証拠を優先する
3. 成功を断定する前に検証する
4. 一度に複数の思いつき修正を重ねない

---

## 学び

debug 系 agent は便利ですが、権限を広げすぎると危険です。
そのため `tools` を絞り、**verification-first** をルールとして明記します。
