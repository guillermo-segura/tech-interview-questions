# GIT

## What is Git and why is it used?

Git is a distributed version control system used for tracking changes in files and coordinating work among multiple developers. It is commonly used for managing source code during software development.

## What are the basic Git commands for initializing a repository, adding files, committing changes, and pushing to a remote repository?

Basic Git commands include:

- `git init`: Initialize a new Git repository.

- `git add`: Add files to the staging area.

- `git commit`: Record changes to the repository.

- `git push`: Push committed changes to a remote repository.

## Explain the difference between git pull and git fetch.

- `git pull` fetches changes from the remote repository and merges them into the local branch.

- `git fetch` only retrieves changes from the remote repository without merging them.

## What is a merge conflict and how do you resolve it?

A merge conflict occurs when Git is unable to automatically resolve differences between two branches during a merge operation. It requires manual intervention to resolve conflicts before the merge can be completed.

## Describe the difference between Git rebase and Git merge.

- `git rebase` integrates changes from one branch into another by reapplying commits from one branch on top of another.

- `git merge` combines the changes from two branches into a new commit.

## What is a Git branch and why would you use one?

A Git branch is a pointer to a specific commit in the repository's history. Branches allow developers to work on separate features or fixes independently and merge changes back into the main codebase when ready.

## How do you revert a commit in Git?

To revert a commit in Git, you can use the `git revert` command followed by the commit hash of the commit you want to revert. You can also use `git reset` if it’s a local commit.

## Explain what a Git repository is.

A Git repository is a storage location where Git stores the history and metadata for a project, including all files and directories, commit objects, branches, and configuration settings.

## How do you undo the last commit in Git?

To undo the last commit in Git, you can use the `git reset --soft HEAD~1` command to reset the HEAD pointer to the previous commit, keeping the changes staged for commit due to the `--soft` flag.

## Can you explain the concept of Git hooks and provide examples of when they might be useful?

Git hooks are custom scripts that Git executes at certain points during the version control process, such as before or after a commit, push, or merge. They can be used to enforce coding standards, run tests, or trigger automated deployments.

## Describe Git submodules and when you might use them.

Git submodules are repositories embedded within another repository. They allow you to include external repositories as dependencies in your project and track their versions independently.

## What is Git cherry-pick and in what situations would you use it?

Git cherry-pick is a command used to apply a specific commit from one branch to another. It's useful for selectively applying changes without merging entire branches.

## Explain the difference between Git reset, Git revert, and Git checkout.

- `git reset` is used to move the HEAD and branch pointers to a specific commit, potentially discarding changes.

- `git revert` creates a new commit that undoes the changes introduced by a specific commit.

- `git checkout` is used to switch between different branches or restore files from a specific commit.

## What is the purpose of Git reflog and when would you use it?

Git reflog records the history of HEAD movements and other changes to the repository's pointers. It's useful for recovering lost commits or branches that have been accidentally deleted.

## Can you describe the Git object model and how Git stores data internally?

The Git object model consists of four main object types: blobs (file content), trees (directory structure), commits (pointers to a snapshot of the repository), and tags (references to specific commits). Git stores these objects in a compressed form in the repository's `.git` directory.

## What are some best practices for collaborating with others using Git?

Best practices for collaborating with others using Git include:

- Using descriptive commit messages.

- Creating feature branches for new development.

- Rebasing local changes before merging.

- Regularly pulling changes from remote repositories to stay up to date.

## Describe a scenario where you would use Git rebase interactively and what benefits it provides over regular rebase.

`git rebase -i` allows you to selectively edit, reorder, or squash commits before applying them to the target branch. It provides more control over the commit history and can help maintain a clean and organized repository history.

## What are conventional commits?

Conventional Commits are a specification for structuring commit messages in a standardized format. It aims to provide a clear and consistent way to communicate about changes in a repository's history, turning commits into machine-readable messages which can be leveraged for automation, release notes generation, and semantic versioning.

### Structure

`type(scope): subject`

**Types:**

- `feat`: A new feature.

- `fix`: A bug fix.

- `docs`: Documentation changes.

- `style`: Changes that do not affect the meaning of the code (e.g., formatting, missing semi-colons).

- `refactor`: Code refactorings or restructuring that do not change its behavior.

- `test`: Adding or modifying tests.

- `chore`: Other changes that don't modify `src` or `test` files (e.g., updating build tasks, package manager configurations).

**Scope (optional):** Provides additional context about the part of the codebase that is affected by the commit.

**Subject:** Briefly describes the change in imperative tense (e.g., "Add feature" instead of "Added feature"). It should be clear and concise, typically limited to 50 characters.

Conventional Commits promote standardized and semantic commit messages, making it easier for developers to understand the purpose of changes, automate release processes, and generate accurate release notes.

[Go back](https://github.com/guillermo-segura/tech-interview-questions)
