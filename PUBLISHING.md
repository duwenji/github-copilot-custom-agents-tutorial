# PUBLISHING

## Release checklist overview
1. `npm install` を実行して依存関係を揃える
2. `npm run quiz:validate` を実行する
3. `npm run ebook:build` を実行し、`ebook-output/` の以下を確認する
   - `github-copilot-custom-agents-tutorial.epub`
   - `github-copilot-custom-agents-tutorial.pdf`
   - `github-copilot-custom-agents-tutorial-kdp-registration.md`
4. GitHub Pages の表示・リンク導線・KDP 登録情報を確認する
5. リリースノートと `CHANGELOG.md` を更新する
