# Basic Git Commands

Git is a version control system that tracks changes to files. A **repository** (or repo) is a project Git is tracking. Most day-to-day Git work follows this pattern: check your changes, stage them, commit them, and share them with a remote repository such as GitHub.

## `git status`

Shows the current branch and the state of your working directory: which files are changed, staged, or untracked.

```bash
git status
```

Run it whenever you want to check what has changed or what Git is ready to commit.

## `git init`

Creates a new Git repository in the current directory. Use it when starting to track an existing local project.

```bash
cd my-project
git init
```

This creates a `.git` directory, where Git stores the repository history and configuration.

## `git clone`

Copies an existing remote repository to your computer, including its commit history. Replace the URL with the repository you want to copy.

```bash
git clone https://github.com/username/project.git
cd project
```

## `git add`

Stages changes, selecting which changes to include in the next commit. Staging does not create a commit by itself.

```bash
git add README.md       # Stage one file
git add .               # Stage all changes in the current directory
```

Check the staged files with `git status` before committing.

## `git commit`

Records the staged changes in the repository's local history. Write a short message describing the changes.

```bash
git commit -m "Add project instructions"
```

A commit only includes staged changes. If Git asks you to configure your identity first, set your name and email with `git config` as appropriate for your setup.

## `git push`

Uploads local commits to a remote repository, such as GitHub. For a new branch, set its upstream on the first push:

```bash
git push -u origin main
```

After the upstream is set, you can usually push later commits with:

```bash
git push
```

Here, `origin` is the conventional name for the remote, and `main` is the branch name. Use the branch name your project actually uses.

## `git pull`

Downloads changes from a remote branch and integrates them into your current branch. Pull before starting work or pushing if others may have updated the branch.

```bash
git pull origin main
```

If your current branch is already connected to its upstream branch, you can usually run `git pull` without specifying the remote and branch. Git may report a merge conflict if the incoming changes overlap with your local changes; resolve the affected files, then commit the resolution if needed.

## A typical workflow

```bash
git status
git pull origin main
git add README.md
git commit -m "Update README"
git push
```

For a brand-new local project, use `git init` first and connect it to a remote before pushing. If you are starting from an existing remote project, use `git clone` instead.
