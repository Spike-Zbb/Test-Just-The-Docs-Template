---
layout: default
title: Reset
parent: Undoing in Git
nav_order: 2
---

# Undoing with git reset
The git reset command is one of the most powerful tools in Git for undoing changes. It allows you to reset your current branch to a specific state, undoing commits, un-staging changes, or even discarding modifications in your working directory, depending on how you use it.

## Key Use
Undoing Staged Changes
When you've staged changes (using git add), but realize you don't want them staged anymore, git reset can be used to unstage those files while keeping the modifications intact in your working directory.

## Example

git reset <file>

This command removes <file> from the staging area but keeps your changes in the working directory, allowing you to continue editing or discard the changes later. It simply "unstages" the file.

## Scenario
Suppose you've edited several files and accidentally staged one of them using git add, but you realize the changes are not ready to be committed. You can run:

git reset example.txt

This will unstage example.txt, moving it back to an untracked state, but the changes you made to the file will still be there.

## Resetting Commits
git reset can also undo commits, allowing you to move your branch pointer back in time. This can be particularly useful if you've committed something by mistake or need to revise your recent work. There are three main modes of git reset:

### --soft
Moves the commit pointer back but keeps all changes staged.

git reset --soft <commit>

Use Case: You realize that the last commit needs more changes or adjustments, and you want to "un-commit" it but keep all the changes staged for a new commit.

### --mixed (default)
Moves the commit pointer back and unstages changes, leaving the modifications in your working directory.

git reset --mixed <commit>

Use Case: You've committed changes that shouldn't have been committed, and you want to modify or completely unstage them, but keep the changes locally to revise them.

### --hard
Moves the commit pointer back and discards all changes in the working directory and staging area. This is the most destructive option, and should be used with caution.

git reset --hard <commit>

Use Case: You want to completely erase all local changes and go back to a specific commit, as though the intervening work never happened. Warning: This command deletes all local changes and commits after the specified commit and cannot be undone!

## Important Notes
### git reset is powerful but can be dangerous
Depending on the mode (soft, mixed, or hard), git reset can be used to revise your commit history, unstage changes, or even erase local modifications. Always double-check your command and make sure you understand the consequences, especially when using --hard.

### Safer alternative
If you're unsure about using git reset --hard, you might want to consider git revert or git checkout, which offer safer ways to undo changes without losing any data permanently.

git reset offers a wide range of ways to undo work, from unstaging changes to rolling back entire commits. However, it's important to use it carefully, particularly with the --hard option. If you're only undoing staged changes, git reset with no additional options (or using --mixed) is the safest approach.
---