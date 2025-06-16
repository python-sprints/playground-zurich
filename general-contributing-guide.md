
# General Contributing guidelines

This is a general (short) guide on how to contribute to open-source projects. Please make sure to **read the specific contributing guidelines of the project** you want to contribute to!

## Index
1. [How to contribute? Step by step guide](#how-to-contribute-step-by-step-guide)
2. [PR conventions](#pr-conventions)
3. [PR review rules](#pr-review-rules)
4. [Issue guidelines](#issue-guidelines)
5. [Common best practices](#common-best-practices)
6. [References](#references)

## How to contribute? Step by step guide

### Glossary
- **Upstream**: the repository from the `original_author`
- **Origin**: the forked repository under your `account`

### Steps

#### 1. Fork a `project` with your GitHub `account`

#### 2. Clone the `project` to your local environment

```sh
git clone https://github.com/account/project.git
cd project
```

#### 3. Set up the upstream remote for your local project

```sh
# Add the "upstream" to your cloned repository
# Note: "origin" is already set when you clone your fork
git remote add upstream https://github.com/<original_author>/<project>.git

# Verify your remotes are set up correctly
git remote -v
```

#### 4. Work in a new branch of your origin

```sh
# 1) Create and switch to a new branch (e.g. `my-new-branch`) from your origin/main branch
git branch my-new-branch origin/main
git checkout my-new-branch

# 2) Make your changes to the code

# 3) Add the modified files and make a commit (e.g. you updated README.md)
git add README.md
git commit -m "Add better description to README"

# 4) Push to your new branch
git push origin my-new-branch
```

#### 5. Make a pull request on GitHub

* Go to the `my-new-branch` of your forked `project` on Github
* Click `Compare & pull request`
* Leave a comment
    * If you are solving an issue (e.g. `#17`), add `Closes #17` in the comment, the issue will automatically be closed when the pull request is merged.

#### 6. Delete branch locally and/or remotely after pull request is merged on GitHub

* Deleting your local branch from the command line: `git branch -d my-new-branch`
* Additionally if you want to delete your remote branch: `git push origin :my-new-branch`

#### 7. (when needed) Synchronize with updates from the upstream

You may need to update your fork with the latest changes from the upstream in these scenarios:
- The main branch was updated since you created your PR and there are conflicts
- You want to incorporate recent changes before starting new work
- Your PR needs to be rebased on the latest main branch

```sh
# 1) Go to the "my-new-branch" branch of your fork ("origin")
git checkout my-new-branch

# 2) Fetch the commits from the "upstream"
git fetch upstream

# 3) Merge the changes from the "main" branch of the "upstream" into your the "my-new-branch" branch of your "origin"
git merge upstream/main

# 4) Resolve merge conflicts if any and commit your merge
git commit -m "Merged from upstream"

# 5) Push the changes to your fork ("origin")
git push
```

## PR conventions

> ⚠️ Note: these conventions vary from project to project. Please check the contributing guidelines of the project you want to contribute to.

When submitting a PR, please add one of the following prefixes depending on the topic you are addressing:

    [ENH]: Enhancement, new functionality
    [BUG]: Bug fix
    [DOC]: Additions/updates to documentation
    [TST]: Additions/updates to tests
    [BLD]: Updates to the build process/scripts
    [PERF]: Performance improvement
    [CLN]: Code cleanup

In addition:
- Please reference the relevant GitHub issues in your commit message using GH1234 or #1234.
- Include a subject line with < 80 chars.
- Optionally, include a commit message body, leaving one blank line with the subject line.

## PR review rules

Projects require the input from one or more reviewers to merge a pull request. For example, one reviewer approves the merge and the other reviewer merges the pull request.

## Issue guidelines

### New issue

Discovering an issue is great, here's what you need to do when you discover an issue:
* Search if the issue has already been created.
* If yes and open refer to existing issue.
* If yes and closed reopen issue with descriptive comment.
* If no, create the issue.

### Existing issue

* Read comments.
* Find out if anyone is working on it, if no, offer to do it. If yes, see if you can be of help.

### Reporting bugs

* Give information about the version and the operating system you are running.
* Show the steps to reproduce bug.
* Add error logs.

## Common best practices

### Writing good commits

- **Use descriptive commit messages**: Write clear, concise messages that explain what and why, not just what
- **Keep commits atomic**: Each commit should represent a single logical change
- **Use imperative mood**: Start commit messages with verbs like "Add", "Fix", "Update", "Remove"
- **Reference issues**: Include issue numbers when relevant (e.g., "Fix login bug (#42)")

### Before submitting a PR

- **Test your changes**: Run the project's test suite locally
- **Check code style**: Follow the project's coding conventions and linting rules
- **Update documentation**: Add or update docs if your changes affect user-facing functionality
- **Keep PRs focused**: One PR should address one feature/bug - avoid mixing unrelated changes

### During the review process

- **Ask for clarification**: If feedback is unclear, don't hesitate to ask questions
- **Make requested changes**: Address all review comments before requesting re-review
- **Use draft PRs**: Mark PRs as draft if they're work-in-progress to get early feedback

## References

**Main resource**: https://github.com/python-sprints/pandas-mentoring/blob/master/contributing.md

* [GitHub forking](https://gist.github.com/Chaser324/ce0505fbed06b947d962)  
* [Git cherry-pick](https://git-scm.com/docs/git-cherry-pick)
* [Pandas contributing guides](https://pandas.pydata.org/pandas-docs/stable/development/contributing.html)
* To read more tips on how to open issues, PRs and do code reviews, read the things we have been learning throughout the mentoring program [here](https://github.com/python-sprints/pandas-mentoring/blob/master/LEARNING_POINTS.md).
