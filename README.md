#Homework 2 | Diego Guzman - Code Along PuralSight Notes#

---GitHub---
***Git is a version control system (VCS) designed to record changes to file(s) overtime
giving you the ability to revert or recall changes to file(s). Compare changes in files
from one version to another***

**Three Stages:**
Commited - Data in this file is safely stored in a local database.  
Modified - file has been altered since last commited version. 
Staged - Changes are marked for commit, ready to be commited.

**Three States:**
Working Directory - A single copy of one version of the project, also known as a checkout. 
.git Directory - A repository, the origin of the project's data.
Staging Area - The index. Area that sits between both directories. Used to control modifications that are ready to be committed.
	Only the files in the staging area get committed.

**Initialize A Git Repository:**
Command: Git init
Creates the .git directory containing important git files


***Basic Commands***
We have a resource on slack with a cheat sheet of the basic commands.
I will be referring a copy of the image in the repository for this.


**Files Tracked By Git:**
Committed - Unmodified changes from the last commit snapshot
Modified - Changes made to files since last commit snapshot
Staged - Changes marked to be added into the next commit snapshot

**The Stages of a Tracked File:**
Committed - Moves from the committed stage to the modified stage when we make a change to a committed or unmodified file.
Modified - When satisifed with the changes, the file gets added to the staging area ready to be committed. 
Staging Area - Takes the file modifications in this area and commits them to the repository. 
	Updates the commit snapshot after changes are committed.


**Command: git status -s OR git status --short** 
gives a more concise short status result
M = Modified, A = New file Added to stage area, ?? = New file untracked by Git

**Command: git diff**
Used to answer two questions, (1) What changes have been staged that are ready to committed
(2) What changes have been made but not yet staged?

index section refers to the file metadata
**git diff --Staged** Used to compare staged changes to last commit snapshot.

**Command: diff --git file1.txt file2.txt**
Used to compare files

minus and plus symbols represent the files.
Example:     --- file1.txt  
	     +++ file2.txt  
Chunk Header: @@ -12, 2, +12, 3 @@
	- represent old content
	+ represents new content

**Command: git commit -am "a commit message"**

-a automatically stages all changes in your working directory tracked by git, skips the git add step altogether
-m adds a commit message

**Command: git push origin master**
Used when ready to send changes to origin project, sends the changes upstream. Pushes changes to the origin 
repository which is on Github. Connecting your local repository to the Github repository and pushing the changes.
 
**Command: git log**
Git returns basic information related to the previous commits/commit history. Lists the commits from most to least recent.

**git log -1**         will show one commit and you can change it to any number to show how many you want to show.
**git log --oneline**  returns a list of commits in a single line format
**git log --stat**     returns a detailed overview of all the commits in the commit history.
**git --patch**        returns a full diff of the exact changes in each file with each commit 

**Remove file:**
**Command: git rm filename**
Removes the file and git has stopped tracking it. Doing a git status will show that the file has been deleted and 
will be removed on next commit.

git rm --cached filename, used to untrack a file from git but not remove the file from the project. 
	Doing a git status will show the file has been changed to untracked but hasn't been deleted.

**Command: git mv existingFilename desiredFilename**
Used to rename a file

***Branches:***
A branch in git is a moveable pointer to a commit made in a project. A commit needs to be made on a branch,
we have control over what branch to make that commit on.

**Command: git checkout -b newBranch**
Used to move to another branch, the -b creates a new branch and checksout to it. Pointer to commit changes to
are set to the newly created branch.

**Command: git stash**
Used after doing adding the file back in using git add . 
It saves the working directory in a work in progress state on the branch. Records a current state of the working directory
and staging area, if you want to go back to a clean directory.

**git stash list**  returns a list of work in progress changes that have been stashed along with the branch.
**git stash show** returns a detailed overview of what file was stashed and its changes.
**git stash pop** to remove a file out of the stash and return to its working directory.


**Merge:**
**Command: git merge branchName**
Merges a branch with the main branch

**Command: git reset**
allows to move commits from history back into the working or staging area. Can be used to throw changes away.
Careful using, destructive command. Good practice not to reset changes once commits have been pushed to remote origin
where collaborators could access the changes.

**git reset --soft**   moves the specific commit(s) back into the staging area
**git reset -mixed**   default reset option if something else isn't already specified,
		       moves the changes back to the working directory
**git reset --hard**   moves the changes to the trash, starts over.

**Pull:**
**Command: git clone repositoryURL**
To pull a github repository to your local computer

