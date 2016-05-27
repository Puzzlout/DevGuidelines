
# How to use Git

## Pushing update to repository
Always push the updates on the target feature branch according to your task and notify the person who assign the task to you (using @mention) when you do.
Provide the details of the updates and a detailed test plan or list unit tests you wrote to validate the development.

Here are soome helpers to push updates:

## Git helpers
To setup the application, you need to do:
- `git clone https://github.com/Puzzlout/{the_repository_name}.git`
- `cd {the_repository_name}`
- `git checkout {branch_name}` (select the branch to work on)
- `git branch`

On the last command, you should see:

`{branch_name}*` (with a * suffixing)

By the following command, you should see that you have the latest code:
- `git status`

Before doing any work, make sure to do:
- `git pull` (to retrieve the possible updates)

Sometimes, it'll ask to add a commit after merge and will open the VM Editor in Terminal. To exit it, just do:
- key ESC
- `:wq` then Enter.

To push updates, use the following in order:

- `git status`
- `git add -A` 
- `git status `

**PLEASE USE THE NAMING OF THE COMMIT AS FOLLOWS:**
- `git commit -m "***#{IssueId}***" -m "***Some additional message if you need"***` (be as explicit as possible, the last part is not mandatory but appreciated if you do several commits in a single task).
- `git reset --soft HEAD~1`(if you need to modify the last commit message and add something you forgot. This uncommit the last commit). Then, you need to repeat the commands from `git add -A`)
- `git push` (login required) 

***IMPORTANT:*** Verify that the build is passing on https://travis-ci.org/Puzzlout/{the_repository_name}. 
If not, fix the code so it passes then adapt the second commit message like the following:
- `git commit -m "***#{IssueId}***" -m "***fix to build {build_id}"***`

*NB: Read this first: http://semver.org/
Every push you do in a day (recommended to push your working code at least once a day to avoid conflicts), please increment the PATCH number (last digit in version number). We then discuss when to increment the Version, Minor and Major values.

Setting your branch to exactly match the remote branch can be done in two steps:

- `git fetch origin`
- `git reset --hard origin/[Branch name]`

If you want to save your current branch's state before doing this (just in case), you can do:

- `git commit -a -m "Saving my work, just in case"`
- `git branch my-saved-work`

See here for more info: http://stackoverflow.com/questions/1628088/how-to-reset-my-local-repository-to-be-just-like-the-remote-repository-head

## Retrieve branch
If you want to work on a branch someone made, you need to run the following commands:

- `git fetch -all`
- `git checkout -b {branch_name} origin/{branch_name}` (created by someone else)

It will create a new {branch_name} locally that can push update to the origin/{branch_name}.

[Follow this procedure](https://github.com/FWAJL/FieldWorkManager/wiki/3.Git-branching-model).
