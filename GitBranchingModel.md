# Intro
Read this before you start any coding: [A successful branching model](http://nvie.com/posts/a-successful-git-branching-model/)

# Merging dev to/from feature branches
The DEV branch is merged to the feature branches so they are kept up to date as often as possible.

Also the Feature branches are merged to Dev when code is ready to be staged and released.

***IMPORTANT***: don't forget to do a `git pull` before you start any work. An update may exist.

# Steps for a feature branch

Make sure to sure to be on the dev branch first

`git checkout dev`

To create the feature branch from the dev branch, please follow the work flow below:

`git checkout -b {feature_milestone} dev` (create a branch from the branch `dev`)
Ex: for the milestone "Home page", the command will be `git checkout -b f_home_page dev`

Otherwise, run the following:

`git push --set-upstream origin {feature_milestone}`

If you are just retrieving the existing branch, you need to do this:

`git checkout -t origin/{feature_milestone}`
 
After that, just do git push and you are good.

Do your coding and when you are done, follow the usual git commit flow:

`git add -A`
`git commit -m "#{issue_id}" -m "- Comment #1" -m "- Comment #2" -m ...`
NB: the "-" preceding each comment creates a line break to view them more clearly afterwards.

`git push` (login required).

If you are working with someone else on that task or milestone, make sure to:

`git pull` (retrieve updates if any)

# Steps to merge the feature branch to dev branch or any other feature or bug branch
## Using Pull Request (or PR)
***This is the preferred method***
- Create a pull request: click "New pull request" on the home page of the repository: https://github.com/Puzzlout/{repository_name}
- Select the source branch (or "compare")
- Select the target branch (or "base")
- Select the milestone
- Select the assignee
- Click create button
- Wait that the build is successful. If not, you will need to fix the issue(s).
- Notify the PR reviewer and tell him if the branch can be deleted or not (See Section "Steps to delete a branch" below)
- The PR reviewer will complete the PR 

## In command line 
***You may need this to fix conflicts when merging the dev to the feature branch.***
`git checkout {target_branch_name}`
`git merge --no-ff {source_branch_name}`
`git push origin {target_branch_name}`

# Steps to delete a branch
Read this [source] (http://makandracards.com/makandra/621-git-delete-a-branch-local-or-remote)

`git branch -d {ranch_name}` (deletes the local branch)

`git push origin --delete {target_branch_name}` (deletes the remote branch in git version 1.7)

***NB:*** Also, after completing a PR, you can delete the branch if the associated milestone is completed.
