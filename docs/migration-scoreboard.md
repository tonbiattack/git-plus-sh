# Migration Scoreboard

`example/git-plus` の Go コマンドと、ルートのシェル版の対応表です。

| Category | Go command | Shell command | Status |
| --- | --- | --- | --- |
| branch | `newbranch` | `git-newbranch` | `★` |
| branch | `rename-branch` | `git-rename-branch` | `★` |
| branch | `delete-local-branches` | `git-delete-local-branches` | `★` |
| branch | `recent` | `git-recent` | `★` |
| branch | `sync` | `git-sync` | `★` |
| branch | `abort` | `git-abort` | `★` |
| commit | `amend` | `git-amend` | `★` |
| commit | `squash` | `git-squash` | `★` |
| commit | `track` | `git-track` | `★` |
| commit | `undo-last-commit` | `git-undo-last-commit` | `★` |
| issue | `issue-create` | `git-issue-create` | `★` |
| issue | `issue-edit` | `git-issue-edit` | `★` |
| issue | `issue-list` | `git-issue-list` | `★` |
| issue | `issue-bulk-close` | `git-issue-bulk-close` | `★` |
| pr | `pr-browse` | `git-pr-browse` | `★` |
| pr | `pr-checkout` | `git-pr-checkout` | `★` |
| pr | `pr-create-merge` | `git-pr-create-merge` | `★` |
| pr | `pr-issue-link` | `git-pr-issue-link` | `★` |
| pr | `pr-list` | `git-pr-list` | `★` |
| pr | `pr-merge` | `git-pr-merge` | `★` |
| release | `release-notes` | `git-release-notes` | `★` |
| repo | `batch-clone` | `git-batch-clone` | `★` |
| repo | `browse` | `git-browse` | `★` |
| repo | `clone-org` | `git-clone-org` | `★` |
| repo | `create-repository` | `git-create-repository` | `★` |
| repo | `repo-others` | `git-repo-others` | `★` |
| stash | `pause` | `git-pause` | `★` |
| stash | `resume` | `git-resume` | `★` |
| stash | `stash-cleanup` | `git-stash-cleanup` | `★` |
| stash | `stash-select` | `git-stash-select` | `★` |
| stats | `step` | `git-step` | `★` |
| tag | `new-tag` | `git-new-tag` | `★` |
| tag | `reset-tag` | `git-reset-tag` | `★` |
| tag | `tag-checkout` | `git-tag-checkout` | `★` |
| tag | `tag-diff` | `git-tag-diff` | `★` |
| tag | `tag-diff-all` | `git-tag-diff-all` | `★` |
| worktree | `worktree-new` | `git-worktree-new` | `★` |
| worktree | `worktree-switch` | `git-worktree-switch` | `★` |
| worktree | `worktree-delete` | `git-worktree-delete` | `★` |

`★` はルートの Bash 実装ありを示します。
