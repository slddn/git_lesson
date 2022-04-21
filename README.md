
# Git Notes: form LiveLessons

## For Local Work
- `git init` :--- initialize current folder as a git repository
- `git clone <URL>` :--- brings the git repo from <URL> to current folder
- `git status` :--- shows the status of the repository
- `git add <FILE>` :--- adds <FILE> to the staging area
- `git commit` :--- opens the text editor for commit message, and commit
   - `git commit -m <"MESSAGE">` :--- writes <"MESSAGE"> as a commit
- `git log` :--- shows the history of the commits
   - `git log --oneline` :--- shows the condensed view of the history
- `git diff` :--- compare current uncommitted state with last known git state
   - `git diff --staged` :--- between the staging area and the last known state
- `git diff HEAD~<NUMBER>` :--- HEAD to commit <NUMBER> relative ago
- `git diff <HASH>` :--- HEAD to the commit in <HASH>
- `git restore --source <HASH OR HEAD~>` :--- restore file to <HASH OR HEAD~>
   - `git checkout <HASH OR HEAD~> <FILE>` :--- restore file to <HASH OR HEAD~>
      - `git checkout <HASH OR HEAD~>` :--- no file; detached state
      - `git checkout main` :--- back to main
      - `git switch main` :--- back to main

## Working With Remotes
-`git remote add <NAME> <URL>` :--- adds the URL as a remote with the name <NAME>
 	<NAME>, by convention, is called 'origin'
- `git remote rm <NAME>` :--- removes the remote called <NAME>
- `git remote -v` :--- view a list of the remotes for the repo
- `git push <WHERE> <WHAT>` :--- pushes, to <WHERE>, the <WHAT> branch
   - git push origin main

## Branches
- `git branch <NAME>` :--- create branch <NAME> at HEAD
- `git switch <NAME>` :--- move to the branch <NAME>
   - `git checkout <NAME>` :--- old version
- `git switch -c <NAME>` :--- create and move to the branch <NAME>
   - `git checkout -b <NAME>` :--- old version
- `git merge <BRANCH>` :--- merge <BRANCH> into the current branch 
- `git rebase` :--- command to change the history of a commit
	Commits from `git merge` can be automatically combined if no conflicts
- `git rebase <BRANCH>` :--- changes from <BRANCH> into current branch; the branch being rebased	
   - `git status` :--- is your friend during rebase; ie, how to proceed
   - `git add <FILE>` :--- to mark conflict resolution
   - `git rebase --continue` :--- move to the next commit in rebase process
   - `git rebase --abort` :--- undo the whole git rebase step
- `git rebase -i <COMMIT> HEAD~` :--- or <HASH> of commit to go into interactive rebase
	Multiple commit changes can be made here; ie, 'squash'/'s'
   - `git rebase -i <HASH>^` :--- use ^ to include the commit in interactive rebase
- `git stash` or `git commit` :--- to save one`s work before moving between branches
   - `stash` :--- is temporary
   - `git stash list` :--- show the stashed commits
   - `git stash apply` :--- apply the last stashed commit
   - `git stash clear` :--- clean up the stashes

- A merge on the remote is called a "pull request" or a "merge request"
   - `git push <WHERE> <WHAT>`
   - To update a PR, we make the branch locally and re-'push'

- A merge conflict can happen after a PR is issued.
- `git fetch` :--- updates the git log without making any changes to the files
   - `git fetch --prune` :--- updates the log and also removes deleted remote branches

- `git push -f <where> <what>` :--- force push the branch <what> to the remote <whare>
   - `git push --force-with-lease <where> <what>` :--- more mindful of collaborators

## Collaborators
- Add collaborators from within the repository Settings.
- Collaborators will then use `git clone <URL>` to copy the repo onto their computers.
- If a collaborator is not the first to sync, he will have to sync the history.
- Each person's branch changes are independent of all others.
- From the MacBook Pro
