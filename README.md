#
# Git Notes: form LiveLessons
## For Local Work
 'git init' :--- initialize current folder as a git repository
 'git clone <URL>' :--- brings the git repo from <URL> to current folder
 'git status' :--- shows the status of the repository
 'git add <FILE>' :--- adds <FILE> to the staging area
 'git commit' :--- opens the text editor for commit message, and commit
 	'git commit -m <"MESSAGE"> :--- writes <"MESSAGE"> as a commit
 'git log' :--- shows the history of the commits
	'git log --oneline' :--- shows the condensed view of the history
 'git diff': compare current unc ommited state with last known git state
	'git diff --staged' :--- between thge staging area and the last known state
 'git diff HEAD~<NUMBER>' :--- HEAD to commit <NUMBER> relative ago
 'git diff <HASH>' :--- HEAD to the commit in <HASH>
 'git restore --source <HASH OR HEAD~>' :--- restore file to <HASH OR HEAD~>
	'git checkout <HASH OR HEAD~> <FILE>' :--- restore file to <HASH OR HEAD~>
 		'git checkout <HASH OR HEAD~>' :--- no file; detached state
		'git checkour main' :--- back to main
 		'git switch main' :--- back to main

## Working With Remotes
 'git remote add <NAME> <URL>' :--- adds the URL as a remote with the name <NAME>
 	<NAME>, by convention, is called 'origin'
 'git remote rm <NAME>' :--- removes the remote called <NAME>
 'git remote - v' :--- shows the remotes for the repo
 'git push <WHERE> <WHAT>' :--- pushes the <WHAT> branch to <WHERE>
	git push origin main

## Branches
 'git branch <NAME>' :--- create branch <NAME> at HEAD
 'git switch <NAME>' :--- move to the branch <NAME>
	'git checkout <NAME>' :--- old version
 'git switch -c <NAME>' :--- create and move to the branch <NAME>
	'git checkout -b <NAME>' :--- old version
 'git merge <BRANCH>' :--- merge <BRANCH> into the current branch 
 'git rebase' :--- cammand to change the history of a commit
	Commits from 'git merge' can be automatically combined if no conflicts
 'git rebase <BRANCH>' :--- changes from <BRANCH> into current branch; the branch being rebased	
	'git status' :--- is your friend during rebase; ie, how to proceed
 	'git add <FILE>' :--- to mark conflict resolution
	'git rebase --continue' :--- move to the next commit in rebase process
	'git rebase --abort' :--- undo the whole git rebase step
 'git rebase -i <COMMIT> HEAD~ or <HASH> of commit to go into iteractive rebase
	multiple commit changes can be made here; ie, 'squash'/'s'
	'git rebase -i <HASH>^' :--- use ^ to include the comity in intractive rebase
 


