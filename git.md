## Commit
A commit in a git repository records a snapshot of all the (tracked) files in your directory

Git also maintains a history of which commits were made when. That's why most commits have ancestor commits above them -- we designate this with arrows in our visualization. Maintaining history is great for everyone working on the project

## Git Branches
Branches are simply pointers to a specific commit
```
#create branch
git branch branch_name


#switches branch

## old version but still works
Git checkout branch_name

## new version that does extra things depending on arguments
Git switch branch_name


# create new branch and switch to it
git checkout -b [yourbranchname]
```

## Merging
```
git merge branch_name_to_merge_with_current_branch
```

## Git Rebasing
its similar to merge but instead of branches, it makes them linear
```
git rebase main
```
## Head
HEAD is the symbolic name for the currently checked out commit -- it's essentially what commit you're working on top of.

HEAD always points to the most recent commit

Normally HEAD points to a branch name (like bugFix)

## Detaching Head
Detaching HEAD just means attaching it to a commit instead of a branch
```
# main here is a branch name
# C1 here is a commit
HEAD -> main -> C1

git checkout C1

HEAD -> C1

```
## Relative Ref
^ will make the HEAD go to the parent of the current commit
```
git checkout bugFix^
```
~ will make the HEAD go to the nth parent of the current commit

## branching forcing
-f

moves {source} to {target}

this moves the main branch to 3 parents behind HEAD
```
git branch -f main HEAD~3
```