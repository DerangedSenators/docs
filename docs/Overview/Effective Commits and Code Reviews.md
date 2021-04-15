# Effective Commits and Code Reviews
This document will detail how to make the best commits and how to effectively review your peer's work

# Commits
A commit is a term used for saving a change to a file or a set of files. There are several components to a commit.
1. The changes you have made to the files (additions and deletions)
2. A commit hash: A hash of the commit used to identify the commit
3. A commit message and summary(optional): The Commit message is a short (50 characters max) statement of the changes made in the commit and you can include a summary if you think that a wider explanation is neccessary. Please read the following for more information [Comment Convention](https://github.com/ktaranov/naming-convention/blob/master/Git%20Comment%20Convention.md) 

When commiting, make sure that each commit as consise as possible and DO NOT add more files than neccessary to each commit. This will cause a lot of headaches should you need to revert a small change in an unneccesarily large commit and it may also result in merge conflicts

## How to commit

1. Once you have saved your changes, open your git client or terminal and stage the changes using ``` git add <filename(s) or * for all changes> ```
2. Commit all stage files using ``` git commit -m "MESSAGE HERE" ```
3. Push the changes to your github repository using ``` git push ```
Your files are now uploaded to github and are ready for peer review to be accepted into the main repository

## Creating a Pull Request
Once you have uploaded your changes to Github, and the source is ready to be merged into the main repository (It could take many commits to reach this stage), Go ahead and open a pull request. Here you will have to add a title and a summary of the changes you have made. You must also add a reviewer (or multiple). This should be someone who knows the task and is able to provide a thorough review. You will also need to assign yourself and whoever worked with you on those commits to the pull request. Feel free to also include tags to make it easier to understand. Once you have filled out the form, you are ready to open the pull request

**Once you open a pull request, All changes that you make on that branch is tracked by the pull request so if you want to work on a different task, be sure to checkout a different branch**

# Code Review
Code review is a step of development when a peer goes through your changes before it is admitted into the main repository to keep the code as bug free and clean as possible. Effective code review is crucial for faster collaborative development.

## Reviewing Code
When reviewing code, ensure that you fully understand the changes that have been made and if applicable, be sure to test those changes for bugs. Feel free to use the comments section to find out more and to provide feedback. Reviewers are able to accept, deny and request improvement on changes. Be sure to make full use of this to maintain the repository as best as possible
If you are having your change reviewed, be sure to be active on the pull request page so that patches, if required can be submitted as fast as possible to spend as less time as you can on the code review phase.

# Updating Source
As time goes on, others on the team will merge their changes into the main repository leaving yours behind. To ensure that your fork is up to date, you can do the following:
```
# Add the remote, call it "upstream":

git remote add upstream https://github.com/whoever/whatever.git # This should be a link to the main repository

# Fetch all the branches of that remote into remote-tracking branches,
# such as upstream/main:

git fetch upstream

# Make sure that you're on your main branch:

git checkout main

# Rewrite your main branch so that any commits of yours that
# aren't already in upstream/main are replayed on top of that
# other branch:

git rebase upstream/main or git merge upstream/main if you don't want to rewrite history on your branch
```
Once  you have rebased locally, It is recommended to push the changes back onto your remote on Github. You can do that with:
``` git push -f origin main ```
You only need to use the `-f` flag the first time after a rebase

[Github Documentation for updating a Fork](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/syncing-a-fork)

