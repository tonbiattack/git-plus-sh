# git-plus-sh

`example/git-plus` 配下の Go 実装を Bash ベースの `git-*` コマンドへ移植したリポジトリです。

各コマンドはルートの [git-plus](/C:/apps/git-plus-sh/git-plus) に集約され、`git-newbranch` や `git-pr-merge` などの薄いラッパーから呼び出します。`git` は `PATH` 上の `git-*` をサブコマンドとして解決するため、`git newbranch` の形式で利用できます。

## 使い方

Git Bash / WSL / macOS / Linux など、Bash が使える環境を前提にしています。

```bash
chmod +x git-plus git-*
export PATH="$PATH:/c/apps/git-plus-sh"
```

動作確認:

```bash
git newbranch -h
git sync -h
git pr-merge -h
```

直接ディスパッチャを叩くこともできます。

```bash
./git-plus newbranch feature/demo
./git-plus tag-checkout --latest
```

## 移植済みコマンド

Go 版 `example/git-plus` から移植したコマンドは次の 39 個です。

- Branch: `git-newbranch`, `git-rename-branch`, `git-delete-local-branches`, `git-recent`, `git-sync`, `git-abort`
- Commit: `git-amend`, `git-squash`, `git-track`, `git-undo-last-commit`
- Issue: `git-issue-create`, `git-issue-edit`, `git-issue-list`, `git-issue-bulk-close`
- PR: `git-pr-browse`, `git-pr-checkout`, `git-pr-create-merge`, `git-pr-issue-link`, `git-pr-list`, `git-pr-merge`
- Release: `git-release-notes`
- Repo: `git-batch-clone`, `git-browse`, `git-clone-org`, `git-create-repository`, `git-repo-others`
- Stash: `git-pause`, `git-resume`, `git-stash-cleanup`, `git-stash-select`
- Stats: `git-step`
- Tag: `git-new-tag`, `git-reset-tag`, `git-tag-checkout`, `git-tag-diff`, `git-tag-diff-all`
- Worktree: `git-worktree-new`, `git-worktree-switch`, `git-worktree-delete`

移植状況の星取表は [docs/migration-scoreboard.md](/C:/apps/git-plus-sh/docs/migration-scoreboard.md) にまとめています。

## 前提ツール

一部コマンドは追加ツールを必要とします。

- `git`: 全コマンドで必須
- `gh`: `pr-*`, `issue-*`, `release-notes`, `create-repository`, `clone-org`, `browse`, `repo-others`, `new-tag --release`
- `code`: `create-repository`, `worktree-*` の VSCode 起動

## 実装メモ

- 共通ロジックは [git-plus](/C:/apps/git-plus-sh/git-plus) に集約しています。
- `git pause` / `git resume` の状態は `~/.git-plus/pause-state` に保存します。
- `git step` は Go 実装と同じくテキストと CSV を自動出力します。
- 既存の旧シェルスクリプト (`git-create-branch` など) は互換のためそのまま残しています。
