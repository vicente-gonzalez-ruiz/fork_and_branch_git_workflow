# fork_and_branch_git_workflow
https://blog.scottlowe.org/2015/01/27/using-fork-branch-git-workflow/

1. Fork the "upstream" (with URL: `<X>`) repository (do that in
   upstream's GitHub page).  A new repository (with URL: `<Y>`) in
   your GitHub account should appear.

2. Clone your forked repository <X>:
   ```
   git clone <Y>
   ```
   This is necessary to contribute over a local copy, otherwise, you
   should be always connected to the Internet and use the GitHub
   facilities.

3. At this moment, your local copy of `<Y>` is only connected to your
   remote repo `<Y>` at GitHub. You can check this with:
   ```
   git remote -v
   ```
   In order to make easuer future updates of your forked repo `<Y>` with
   possible commits to `<X>`, add a new remote named "upstream" with:
   ```
   git remote add upstream <X>
   ```
   (`<X>` can be found in the "Clone or download" button of the original
   `<X>` repository)

4. Revise the list of open issues at `<X>` (not at `<Y>`, you won't be
   able to find issues at `<Y>` at this moment) and select one, for
   example, `iss<Z>`, where `<Z>` is the issue number that GitHub
   automatically generates for every new branch. With the aim of
   working in `iss<Z>`, create a new "feature" branch (in your local
   copy of `<Y>`) with:
   ```
   git checkout -b `iss<Z>`
   ```
   you will be switched to new bran `iss<Z>`, something that can be
   checked with:
   ```
   git branch
   ```
   
5. Perform your modifications and keep your repos, both local `<Y>` and
   remote `<Y>` updated. Basically:
   
   1. Use:
   ```
   git add <new_file>
   ```
   to add a new file to the repo.

	2. Use:
	```
    git rm <undesired_file>
	```
	to delete a undesired file from the repo.
	
	3 Use:
	```
    git commit -am "Your comments here"
	```
	to update your local repo with your modifications.

	4. Use:
	```
    git push
	```
	to synchronize your local copy `<Y>` with the remote one `<Y>`.

	5. Use:
	```
    git ckecout <branch>
	```
	to work on a different branch <branch>.

6. Performs a:
   ```
   git commit -am "Your comments here"
   ```
   to be sure that your local repo `<Y>` is updated.

7. Synchronize your local repo `<Y>` with your remote repo `<Y>`
   "origin" (remember that the father repo is `<X>` and it has the
   name "upstream"):
   ```
   git push --set-upstream origin iss<Z>
   ```
   
8. Test that your repo `<Y>` at GitHub has a new branch `iss<Z>`. Log
   into GitHub and check that (click on the "Branch: master"
   button). Notice that the rest of current branches forked from `<X>`
   will be also available.

9. Keep your fork `<Y>` always synchronized with `<X>`:
   ```
   git pull upstream master # Update your local <Y>
   git push origin master   # Synchronize with your remote <Y>
   ```
   this is specially important just before requesting the pull-request
   (PR), because a modification at upstream master could affect your
   modifications.

10. Go to your GitHub account and select your repo `<Y>`. A area in your
    GitHub page will be created (probably backgrounded in yellow) with
    a button that says: "Compare and pull request". If every thing
    went well, GitHub will inform to you that your PR can be
    automatically merged. Write something explaining your contribution
    and click on "Create pull request". After that, in the page of the
    parent project `<X>`, in the section "Pull request" will appear a
    new entry. The owner of the project will accept or not your PR.

11. You have done your work and you can clean your branch with:
	```
    git checkout master             # Change to branch master
    git branch -d iss<Z>            # Delete the branch in your local <Y>
    git push origin master          # Synchronize your origin master <Y>
    git push --delete origin iss<Z> # Delete the branch from origin <Y>
	```
