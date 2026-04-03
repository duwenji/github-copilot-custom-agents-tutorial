# Part 5-3: Orchestrator Agent の例

## 概要

`tutorial-orchestrator.agent.md` は、専門 agent を束ねる調整役の例です。

---

## 何をする agent か

- 大きな依頼を小さなステップに分ける
- 必要に応じて専門 agent に任せる
- 全体の進捗と次のアクションを整理する

---

## 向いている場面

- 教材リポジトリをまとめて整えたい
- docs と debug と maintenance が混ざる依頼
- 一度に複数の成果物を整理したい

---

## 注意点

- 小さい依頼にまで orchestration を持ち込まない
- 子 agent の責務と親 agent の責務を混ぜない
- ループ的な delegation を避ける

---

## 学び

高度な agent 設計では、**専門性の分割** と **調整役の明確化** が重要です。
