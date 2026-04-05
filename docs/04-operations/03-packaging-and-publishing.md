# Part 4-3: Packaging と公開準備

## この教材リポジトリの方針

このリポジトリでは、以下の形で再利用しやすくすることを想定しています。

- Markdown ベースの教材として読む
- eBook としてビルドする
- GitHub Pages で公開する

---

## 用意したファイル

- `.github/skills-config/ebook-build/`
- `.github/workflows/validate.yml`
- `.github/workflows/pages.yml`
- `package.json`

これにより、教材の build と公開導線をシンプルに保てます。

---

## 基本コマンド

```powershell
git submodule update --init --recursive
npm install
npm run ebook:build
```

> 実行前に、共有スキル群 (`shared-copilot-skills`) を **submodule として初期化**しておくのが推奨です。

---

## 公開前の確認

- 章番号がそろっているか
- README のリンク切れがないか
- `.agent.md` サンプルの説明文が具体的か
- eBook / cover 出力先が `.gitignore` 対象になっているか

---

## GitHub Pages 公開

この教材では `docs/` を GitHub Pages で公開できるようにしています。

- workflow: `.github/workflows/pages.yml`
- site entry: `docs/index.md`
- Jekyll config: `docs/_config.yml`

想定 URL:

```text
https://duwenji.github.io/github-copilot-custom-agents-tutorial/
```

---

## 小さく公開するコツ

最初から完成版を目指すより、
**初版 → フィードバック → 改善版** の流れで公開するほうが安定します。
