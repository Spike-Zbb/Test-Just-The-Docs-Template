---
layout: default
title: Checkout
parent: Undoing in Git
nav_order: 1
---

# Undoing with git checkout

The git checkout command is a versatile tool in Git, often used for switching between branches or restoring files to a previous state. When it comes to undoing changes, git checkout can help you discard modifications in the working directory that haven't been staged yet.

## Key Use
Undoing Changes in a Specific File
If you've made changes to a file and haven't yet staged those changes, git checkout allows you to revert that file back to its last committed state. This effectively discards all local modifications in that file.

## Example

git checkout -- <file>

This command resets <file> to match the version in your most recent commit. Any changes you've made to the file in your working directory will be lost, meaning this action is destructive and cannot be undone.

## Scenario
Imagine you've been working on example.txt and made some changes, but now you realize you want to discard those changes and go back to the last committed version of the file. You can use:

git checkout -- example.txt

Now, example.txt will look exactly as it did in the last commit, and any modifications will be undone.

## Important Notes

### Not for staged changes:
git checkout only undoes changes in files that have not been staged (git add). If changes have already been staged, you will need to use git reset or git restore to unstage them.


### Branch safety
This command is safe to use if you only want to undo changes in specific files. It will not affect the state of your branches or commit history.

## Replacing git checkout with git restore
As of newer versions of Git, the functionality of git checkout related to undoing changes has been split into the git restore command. While git checkout still works for undoing file changes, it's recommended to use git restore for this specific purpose:

git restore <file>
git 
However, git checkout remains a powerful tool for undoing changes in specific files when you're not using the newer git restore.
---