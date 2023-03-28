
# General Contributing guidelines

This is a general (short) guide on how to contribute to open-source projects. Please make sure to read the specific contributing guidelines of the project you want to contribute to!

## Index
1. [How to contribute? Step by step guide](#how-to-contribute?-step-by-step-guide)
2. [PR conventions](#pr-conventions)
3. [PR review rules](#pr-review-rules)
4. [Issue guidelines](#issue-guidelines)
5. [References](#references)

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

#### 3. Set up the origin and upstream of the your local `project`
```sh
#  Add the "upstream" to your cloned repository
git remote add upstream https://github.com/original_author/project.git

# Add the "origin" to your cloned repository
git remote add origin https://github.com/account/project.git
```

#### 4. Work in a new branch of your origin
```sh
# 1) Create a new branch (e.g. `my-new-branch` from your origin/main branch
git branch my-new-branch origin/main
git checkout my-new-branch

# 2) Make your changes to the code

# 3) Add the modified files and make a commit (e.g. you updated README.md)
git add README.md
git commit -m 'added a better description'

# 4) Push to your new-branch
git push origin my-new-branch
```

#### 5. Make a pull request on GitHub
* Go to the `my-new-branch` of your forked `project` on Github
* Click `Compare & pull request`
* Leave a comment
    * If you are solving an issue (e.g. `#17`), add `Closes #17` in the comment, the issue will automatically be closed when the pull request is merged.

#### 6. Delete branch locally and/or remotely after pull request is merged on GitHub
* Deleting your local branch from the command line: `git branch -d my-new-branch`
* Additionally if you want to delete your remote branch: `git push origin : my-new-branch`

#### 7. (in case you need it) Synchronize with updates from the upstream

Sometimes you may need to update your fork with the latest changes from the upstream. This may happen when, for example, the main branch was update since you opened your PR and contains conflicts with your changes .

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

> ⚠️ Note: these conventions varies from project to project. Please check the contributing guidelines of the project you want to contribute to.

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

## References

**Main resource**: https://github.com/python-sprints/pandas-mentoring/blob/master/contributing.md

* [GitHub forking](https://gist.github.com/Chaser324/ce0505fbed06b947d962)  
* [Git cherry-pick](https://git-scm.com/docs/git-cherry-pick)
* [Pandas contributing guides](https://pandas.pydata.org/pandas-docs/stable/development/contributing.html)
* To read more tips on how to open issues, PRs and do code reviews, read the things we have been learning throughout the mentoring program [here](https://github.com/python-sprints/pandas-mentoring/blob/master/LEARNING_POINTS.md).