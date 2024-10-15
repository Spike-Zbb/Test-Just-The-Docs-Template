---
layout: default
title: Revert
parent: Undoing in Git
nav_order: 3
---

# Undoing with git revert
The git revert command is one of the safest ways to undo changes in Git. Unlike git reset, which can modify the commit history by moving the branch pointer, git revert creates a new commit that undoes the changes introduced by a previous commit. This makes git revert ideal for undoing changes in a public or shared branch because it preserves the commit history, ensuring that nothing is lost or rewritten.

## Key Use
Safely Undoing a Commit
When you realize that a commit introduced unwanted changes or broke something, git revert allows you to undo that commit by creating a new commit that negates the original one. This effectively reverts the changes without altering the existing commit history.

## Example

git revert <commit>

This command creates a new commit that undoes the changes introduced by the specified <commit>. The original commit remains in the history, but the new commit "reverses" its effects.

## Scenario
Imagine you made a commit (say, abc123) that introduced a bug. Instead of deleting that commit or rewriting history, you can run:

git revert abc123

Git will create a new commit that introduces changes that exactly reverse what was done in commit abc123. This way, the original commit still exists, but its changes are effectively undone by the new revert commit.

## Reverting Multiple Commits
You can also revert multiple commits at once by specifying a range of commits or using the --no-commit option to stage multiple reverts before committing.
Reverting multiple commits in a row:

git revert HEAD~3..HEAD

This reverts the last three commits, from HEAD~3 to HEAD, and creates individual revert commits for each one.

## Important Notes

### Non-destructive
git revert is a non-destructive command because it doesn’t remove any commits or rewrite history. Instead, it adds a new commit that undoes the changes made by a previous commit.

### Preferred in shared branches
Since git revert doesn’t alter the commit history, it is the preferred method for undoing changes in branches that are shared with others (such as the main branch in a collaborative project). It avoids issues that arise from rewriting history, such as breaking other developers' work.

## Why Use git revert Over git reset

### Safe in shared branches
Unlike git reset, which rewrites commit history, git revert adds a new commit that clearly documents the undoing of changes, making it safe for shared branches like main or master.

### Keeps a clean history
By preserving the original commit and simply adding a new commit that undoes it, git revert maintains a clear and traceable commit history. This is especially useful when you want to document both the original change and its reversal.

In summary, git revert is the safest and cleanest way to undo changes in Git, especially in shared or public branches. It creates a new commit that undoes a specific commit without altering the commit history, ensuring that the undoing process is fully transparent and traceable. It is ideal for reversing changes when working in a collaborative environment where rewriting history is discouraged.
---