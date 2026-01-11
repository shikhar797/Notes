![[Pasted image 20251220100915.png]]

## What exactly is a distributed version control system?

[](https://about.gitlab.com/topics/version-control/benefits-distributed-version-control-system/#what-exactly-is-a-distributed-version-control-system)

A distributed [version control system](https://about.gitlab.com/topics/version-control/) (DVCS) brings a local copy of the complete repository to every team member’s computer, so they can commit, branch, and merge locally. The server doesn’t have to store a physical file for each branch — it just needs the differences between each commit.

Distributed source code management systems, such as Git, Mercurial, and Bazaar, mirror the repository and its entire history as a local copy on individual hard drives.

[Distributed version control systems](https://about.gitlab.com/blog/distributed-version-control/) help software development teams create strong workflows and hierarchies, with each developer pushing code changes to their own repository and maintainers setting a [code review process](https://about.gitlab.com/topics/version-control/what-is-code-review/) to ensure only quality code merges into the main repository.

A DVCS can be puzzling, especially if a team member is accustomed to [centralized source code systems](https://about.gitlab.com/topics/version-control/what-is-centralized-version-control-system/), because a contributor can no longer rely on a server to resolve conflicts when merging and has to resolve them locally, which can result in confusing merge commits. However, despite the initial discomfort, a distributed source control system can ensure stable code development when multiple developers contribute to software development projects.


![[Pasted image 20251220101618.png]]


# BASIC INITIALIZATION GIT COMMAND

![[Pasted image 20251220101910.png]]


git commands to see name or username

1. git config user.name
2. 2.git config user.email


![[Pasted image 20251220103423.png]]


demo.txt -> unstaging area -> git add demo.txt ->staging area ->git commit   there are git log


# Workflow 
![[Pasted image 20251220110812.png]]


## What is Master Branch?

![[Pasted image 20251220111117.png]]

## What is Head ?

![[Pasted image 20251220111716.png]]



## What is Branching ?

![[Pasted image 20251220112253.png]]

#### Branching Command

![[Pasted image 20251220112726.png]]


#### Deleting and renaming the branches 

![[Pasted image 20251222114355.png]]

## Note:- if you on that branch then you cannot delete that branch 



![[Pasted image 20251222115234.png]]




## 1. Fast-Forward Merge

This is the simplest type of merge. It happens when the branch you are merging into (e.g., `main`) **has not changed** since you created your new branch.

Because there are no conflicting changes, Git simply "moves the pointer" forward to the latest commit on your new branch.

- **The Result:** A perfectly straight line of history.

- **When it happens:** When your new branch is the only thing that has progressed.



## 2. Three-Way Merge (Recursive)

This is what happens in a "real world" scenario where multiple people are working. If you created a feature branch, but in the meantime, someone else added new commits to the `main` branch, the history has **diverged**.

To join them, Git looks at three things:

1. The **Common Ancestor** (where the branches first split).

2. The latest commit on **Branch A**.

3. The latest commit on **Branch B**.


- **The Result:** Git creates a new **"Merge Commit"** that has two "parents." This commit ties the two histories together.

- **When it happens:** When both the source and target branches have moved forward independently.


## What about Merge Conflicts?

A merge conflict occurs during a Three-Way Merge if you and another person edited the **exact same line** of the same file. Git gets confused and doesn't know which version to keep.

- **How to fix it:** Git will pause the merge and mark the file. You have to open the file, manually choose which code stays, save it, and then finish the commit.




# What is Git Stash ?

The git stash command is a powerful feature that allows you to temporarily save your uncommitted changes (both staged and unstaged modified tracked files) and revert your working directory to a clean state. This is particularly useful when you need to switch branches, pull updates, or address an urgent bug fix without committing half-finished work. 
The stashed changes are stored locally in a stack and do not affect your project's commit history or remote repository. You can re-apply them later on the same or a different branch when you are ready

![[Pasted image 20251222124313.png]]

![[Pasted image 20251222142919.png]]

![[Pasted image 20251222144221.png]]



# Revisiting version in Git

![[Pasted image 20251222145531.png]]



![[Pasted image 20251222145800.png]]


![[Pasted image 20251222152625.png]]

![[Pasted image 20251222152653.png]]

![[Pasted image 20251222152808.png]]

