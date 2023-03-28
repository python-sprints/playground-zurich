
# Contributing

Contribute to this repository by adding your name to the list of participants of the event you are attending.

## 1. Fork the `playground-zurich` with your GitHub `account`

![fork](./media/fork.png)

## 2. Clone the repo to your local environment
```sh
git clone https://github.com/python-sprints/playground-zurich.git
cd playground-zurich
```

#### 3. Set up the origin and upstream of the your local `project`
```sh
#  Add the "upstream" to your cloned repository
git remote add upstream https://github.com/python-sprints/playground-zurich.git

# Add the "origin" to your cloned repository
git remote add origin https://github.com/account/playground-zurich.git
```

#### 4. Work in a new branch of your origin
```sh
# 1) Create a new branch (e.g. `add-my-name` from your origin/main branch
git branch add-my-name origin/main
git checkout add-my-name

# 2) Add your name to the list of participants of the event you are attending

# 3) Add the modified files and make a commit (e.g. you changed events/2023-03-28.md)
git add events/2023-03-28.md
git commit -m 'added my name'

# 4) Push to your branch
git push origin add-my-name
```

#### 5. Make a pull request on GitHub
* Go to the `add-my-name` of your forked `project` on Github
* Click `Compare & pull request`
* Leave a comment

See a [**PR example** here](https://github.com/python-sprints/playground-zurich/pull/2)!

#### 6. Delete branch locally and/or remotely after pull request is merged on GitHub
* Deleting your local branch from the command line: `git branch -d add-my-name`
* Additionally if you want to delete your remote branch: `git push origin : add-my-name`

#### 7. (in case you need it) Synchronize with updates from the upstream

Sometimes you may need to update your fork with the latest changes from the upstream. This may happen when, for example, the main branch was update since you opened your PR and contains conflicts with your changes.

```sh
# 1) Go to the "my-new-branch" branch of your fork ("origin")
git checkout add-my-name

# 2) Fetch the commits from the "upstream"
git fetch upstream

# 3) Merge the changes from the "main" branch of the "upstream" into your the "my-new-branch" branch of your "origin"
git merge upstream/main

# 4) Resolve merge conflicts if any and commit your merge
git commit -m "Merged from upstream"

# 5) Push the changes to your fork ("origin")
git push
```

## PR review rules

Projects require the approval from one reviewers to merge the pull request.

## Issue guidelines

### New issue
Any issue in the documentation? Here's what you need to do when you want to create a new issue:
* Search if the issue has already been created.
* If yes and open refer to existing issue.
* If yes and closed reopen issue with descriptive comment.
* If no, create the issue. :)

### Existing issue
* Read comments.
* Find out if anyone is working on it, if no, offer to do it. If yes, see if you can be of help.

## References

**Main resource**: https://github.com/python-sprints/pandas-mentoring/blob/master/contributing.md
