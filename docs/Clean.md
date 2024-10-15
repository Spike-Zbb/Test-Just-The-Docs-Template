---
layout: default
title: Clean
parent: Undoing in Git
nav_order: 4
---

# Undoing with git clean
The git clean command is used to remove untracked files from your working directory. These are files not being tracked by Git and haven’t been added to any commit.

## Key Use
Removing Untracked Files
git clean removes untracked files and directories, helping you clean up your workspace after builds or experiments.

## Example

git clean -f

This command will forcefully (-f) remove all untracked files from your working directory. Once removed, these files are gone and cannot be recovered through Git.

## Scenario
You’ve just completed a large build, and your working directory is full of generated files that were not added to version control. You don’t want these files cluttering up your workspace anymore, so you can run:

git clean -f

This will delete all untracked files, cleaning up your workspace.

## Preview Before Deleting (Undo Safely)
Since git clean is a destructive operation, it’s always a good idea to preview which files will be deleted before actually removing them. You can do this using the -n (dry-run) option.

git clean -n

This command will list the untracked files that would be deleted by git clean -f, but it won’t actually remove them. This allows you to safely review what will be undone before committing to the changes.

## Important Notes
### Only affects untracked files
git clean only operates on untracked files—files that haven't been staged or committed. If you want to undo changes to tracked files, you'll need to use other Git commands like git checkout or git reset.

### Irreversible
Once you run git clean -f, the files are permanently deleted from your working directory. They can’t be recovered through Git, so use this command with caution.

## When to Use git clean to Undo Changes
### After mistakenly creating untracked files
If you’ve created files that don’t belong in the repository and you want to quickly undo their existence, git clean is the go-to command.
However, git checkout remains a powerful tool for undoing changes in specific files when you're not using the newer git restore.

### After working with temporary files
Often during development, temporary files are generated that are not meant to be tracked. git clean can undo these changes by removing them and cleaning up the workspace.

In summary, git clean is an effective way to undo untracked changes by removing files and directories that haven't been added to version control. It’s particularly useful for cleaning up temporary or unnecessary files, but it’s important to use with caution, as it permanently deletes files from your working directory.
---