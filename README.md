# Git and GitHub Guide

## Table of Contents

1. [Introduction](#introduction)
2. [Installing Git](#installing-git)
3. [Basic Git Concepts](#basic-git-concepts)
    - [Repositories](#repositories)
    - [Staging Area](#staging-area)
    - [Commits](#commits)
    - [Branches](#branches)
4. [Essential Git Commands](#essential-git-commands)
    - [`git init`](#git-init)
    - [`git clone`](#git-clone)
    - [`git add`](#git-add)
    - [`git commit`](#git-commit)
    - [`git push`](#git-push)
    - [`git fetch`](#git-fetch)
    - [`git pull`](#git-pull)
    - [`git branch`](#git-branch)
    - [`git checkout`](#git-checkout)
    - [`git merge`](#git-merge)
    - [`git status`](#git-status)
    - [`git log`](#git-log)
5. [Git Branching](#git-branching)
    - [Importance of Branch Protection](#Importance-of-Branch-Protection)
    - [Creating Branches](#creating-branches)
    - [Switching Branches](#switching-branches)
    - [Merging Branches](#merging-branches)
6. [Pull Requests and Issue](#Pull-Requests-and-Issue)
    - 
7. [Working with Git in Visual Studio Code (VS Code)](#working-with-git-in-visual-studio-code-vs-code)
    - [Cloning a Repository in VS Code](#cloning-a-repository-in-vs-code)
    - [Making Changes and Committing](#making-changes-and-committing)
    - [Pushing Changes](#pushing-changes)
    - [Pulling Changes](#pulling-changes)
    - [Branch Management in VS Code](#branch-management-in-vs-code)
8. [Best Practices](#best-practices)

## Introduction

Git is a powerful version control system that tracks changes to your files, enabling collaboration and history tracking. GitHub is a cloud-based platform that hosts Git repositories, facilitating collaboration among developers.

## Installing Git

Before using Git, you need to install it on your computer.

- **Windows:** Download Git from [git-scm.com](https://git-scm.com/) and follow the installation instructions.
- **macOS:** Install Git using Homebrew:
  ```bash
  brew install git
  ```
- **Linux:** Our server already has git.
## Basic Git Concepts
### Repositories
A repository (or "repo") is a directory that contains your project files and the complete history of changes made to those files.

### Staging Area
The staging area is where you prepare files before committing them. You add changes to the staging area using git add.

### Commits
A commit is a snapshot of your repository at a specific point in time. Commits include a message describing the changes.

### Branches
Branches allow you to develop features or fixes in isolation from the main codebase. The default branch is usually main or master.

## Essential Git Commands
### git init
Initializes a new Git repository in your current directory.
```bash
git init
```
### git clone
Clones an existing Git repository from a remote location (like GitHub) to your local machine.
```bash
git clone <repository-url>
```
### git add
Adds changes from the working directory to the staging area.
```bash
git add <file>
# Or add all changes
git add .
```
### git commit
Commits the staged changes with a descriptive message.

```bash
git commit -m "Your commit message"
```
### git push
Pushes your local commits to a remote repository (e.g., GitHub).
```bash
git push origin <branch-name>
```
### git fetch
Fetches changes from a remote repository without merging them into your working directory.
```bash
git fetch
```
### git pull
Fetches changes from a remote repository and merges them into your current branch.
```bash
git pull origin <branch-name>
```
### git branch
Lists all branches in your repository, or creates a new branch.
```bash
# List branches
git branch

# Create a new branch
git branch <new-branch-name>
```
### git checkout
Switches to a different branch.
```bash
git checkout <branch-name>
```
### git merge
Merges changes from one branch into your current branch.
```bash
git merge <branch-name>
```
### git status
Shows the status of changes as untracked, modified, or staged.
```bash
git status
```
### git log
Shows the commit history for the repository.
```bash
git log
```
## Git Branching
### Importance of Branch Protection
Branch protection is a critical feature that helps maintain the stability and integrity of your main codebase. By protecting branches like `main`, you can ensure that:        
- Code is Reviewed: All changes are reviewed by at least one other developer before being merged, reducing the chance of introducing bugs.
- Tests are Passed: Automated tests are run, and must pass before code is merged, ensuring that new changes don’t break existing functionality.
- Commit History is Clean: By enforcing practices like “Squash and Merge,” you can keep your commit history clean and easy to navigate.
### Creating Branches
Create a new branch to develop a feature or fix a bug without affecting the main branch.
```bash
git branch <branch-name>
```
### Switching Branches
Switch to the branch you want to work on.
```bash
git checkout <branch-name>
```
### Merging Branches
When your feature or fix is complete, merge the branch back into main or develop.
```bash
git checkout main
git merge <branch-name>
```
## Pull Requests and Issue
### Working with Pull Requests
Pull requests (PRs) are a key part of a collaborative Git workflow. They allow developers to propose changes to the codebase, which can then be reviewed and discussed before being merged.
- Creating a Pull Request:
1. Push your feature branch to the remote repository.
2. Go to your repository on GitHub, and you’ll see an option to create a pull request from your branch.
3. Provide a clear title and description for your pull request, explaining what changes you’ve made and why.
- Reviewing a Pull Request:
1. Other team members can review the code, leave comments, and suggest changes.
2. The pull request should only be merged after it has been reviewed and approved.
3. Merge the PR using the appropriate method (e.g., "Squash and Merge") to keep the commit history clean.
- Closing a Pull Request
If a pull request is no longer needed, it can be closed without merging. This is useful if the changes are no longer relevant or if they’ve been superseded by other work.
### GitHub Issues
- Creating Issues
1. Go to the "Issues" tab in your repository.
2. Click on "New Issue."
3. Provide a descriptive title and a detailed explanation of the issue.
4. Assign the issue to a team member, add labels, and set milestones as needed.
- Managing Issues
1. Assigning Issues: Issues can be assigned to specific team members, making it clear who is responsible for addressing them.
2. Labels and Milestones: Use labels to categorize issues (e.g., bug, enhancement) and milestones to group issues that should be completed by a certain date.
3. Linking to Pull Requests: When you open a pull request that addresses an issue, you can link the two. GitHub will automatically close the issue when the pull request is merged.
## Working with Git in Visual Studio Code (VS Code)
### Cloning a Repository in VS Code
1. Open VS Code.
2. Use Ctrl+Shift+P to open the command palette.
3. Type Git: Clone and select it.
4. Enter the repository URL and choose a local directory.
### Making Changes and Committing
1. Make changes to your files in VS Code.
2. Go to the Source Control view by clicking the Git icon in the Activity Bar.
3. Stage your changes by clicking the + icon next to the files.
4. Enter a commit message and click the checkmark icon to commit.
### Pushing Changes
1. After committing, click the ... menu in the Source Control view.
2. Select Push to push your changes to the remote repository.
### Pulling Changes
1. To update your local branch with remote changes, click the ... menu in the Source Control view.
2. Select Pull to fetch and merge changes.
### Branch Management in VS Code
1. To create or switch branches, click on the branch name in the lower-left corner.
2. Select Create new branch or choose an existing branch.
## Best Practices
Commit Often: Commit your changes frequently with clear and concise messages.
Use Branches: Always use branches for new features or fixes.
Pull Before You Push: Always pull the latest changes from the remote repository before pushing your changes.
Review Before Merging: Use pull requests and code reviews to ensure quality before merging.
