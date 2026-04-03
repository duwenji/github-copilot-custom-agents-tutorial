# Part 5-1: Subagents と Handoffs

## なぜ必要か

教材作成や大きな保守作業では、1つの agent だけで全部やろうとすると責務が広がりすぎます。

そこで使う考え方が **subagent** と **handoff** です。

---

## subagent とは

ある agent が、別の専門 agent に一部の仕事を任せる構成です。

例:
- `tutorial-orchestrator` が全体を整理する
- 文書整形は `docs-writer`
- 問題調査は `debug-helper`

---

## handoff とは

担当を切り替えるイメージです。

- 企画段階 → docs agent
- 実装確認 → debug agent
- 仕上げ → repo-maintainer agent

---

## 設計のコツ

1. 親 agent の責務は **調整役** に絞る
2. 子 agent には **明確な専門領域** を持たせる
3. 循環的な受け渡しを避ける
4. どこで最終判断するかを決める

---

## アンチパターン

- 全員が何でもやる
- handoff の条件が曖昧
- 親 agent 自身も実務を抱え込みすぎる
