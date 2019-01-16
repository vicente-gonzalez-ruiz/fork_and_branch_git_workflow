# The Fork and Branch Git Workflow
https://blog.scottlowe.org/2015/01/27/using-fork-branch-git-workflow/

**1. Fork the "upstream" (with URL: `<original remote repository>`) repository (do that in
   upstream's GitHub page).  A new repository (with URL: `<forked remote repository>`) in
   your GitHub account should appear.**

**2. Clone your forked repository <original remote repository>:**
   ```
   git clone <forked remote repository>
   ```
   This is necessary to contribute over a local copy, otherwise, you
   should be always connected to the Internet and use the GitHub
   facilities.

**3. At this moment, your local copy of `<forked remote repository>` is only connected to your
   remote repo `<forked remote repository>` at GitHub. You can check this with:**
   ```
   git remote -v
   ```
   In order to make easier future updates of your forked repo `<forked remote repository>` with
   possible commits to `<original remote repository>`, add a new remote named "upstream" with:
   ```
   git remote add upstream <original remote repository>
   ```
   (`<original remote repository>` can be found in the "Clone or download" button of the original ("upstream")
   `<original remote repository>` repository)

**4. Revise the list of open issues at `<original remote repository>` (not at `<forked remote repository>`, you won't be
   able to find issues at `<forked remote repository>` at this moment) and select one, for
   example, `iss<Z>`, where `<Z>` is the issue number that GitHub
   automatically generates for every new issue. With the aim of
   working in `iss<Z>`, create a new "feature" branch (in your local
   copy of `<forked remote repository>`) with:**
   ```
   git checkout -b iss<Z>
   ```
   you will be switched to new branch `iss<Z>`, something that can be
   checked with:
   ```
   git branch
   ```

**5. Perform your modifications and keep your repos, both local `<forked remote repository>` and
   remote `<forked remote repository>` updated. Basically:**

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

   3. Use:
   ```
   git commit -am "Your comments here"
   ```
   to update your local repo with your modifications.

   4. Use:
   ```
   git push
   ```
   to synchronize your local copy `<forked remote repository>` with the remote one `<forked remote repository>`.

   5. Use:
   ```
   git checkout <name of the branch you want to develop>
   ```
   to work on a different branch <branch>.

**6. Performs a:**
   ```
   git commit -am "Your comments here"
   ```
   to be sure that your local repo `<forked remote repository>` is updated.

**7. Synchronize your local repo `<forked remote repository>` with your remote repo `<forked remote repository>`
   "origin" (remember that the father repo is `<original remote repository>`, and that its name
   is "upstream"):**
   ```
   git push --set-upstream origin iss<Z>
   ```

**8. Test that your repo `<forked remote repository>` at GitHub has a new branch `iss<Z>`. Log
   into GitHub and check that (click on the "Branch: master"
   button). Notice that the rest of current branches forked from `<original remote repository>`
   will be also available, if any.**

**9. Keep your fork `<forked remote repository>` always synchronized with `<original remote repository>`:**
   ```
   git pull upstream master # Update your local branch <Z> of <forked remote repository> with master of <original remote repository>
   git push origin master   # Synchronize your local <forked remote repository> with your remote <forked remote repository>
   ```
   This is especially important just before requesting the pull-request
   (PR), because a modification at upstream master could affect your
   modifications.

**10. After a push, go to your GitHub account and select your repo `<forked remote repository>`. An area in your
    GitHub page will be created (probably backgrounded in yellow) with
    a button that says: "Compare and pull request". If every thing
    went well, GitHub will inform to you that your PR can be
    automatically merged. Write some text explaining your contribution
    and click on "Create pull request". After that, in the page of the
    parent project `<original remote repository>`, in the section "Pull request" will appear a
    new entry. The owner of the project will accept (or not) your PR.**

**The following image shows a pull request being performed, the blue haired developer (the fork proprietary)
    is asking the red haired developer (the proprietary of the original repository) permission to add the fork changes to the 	             original repository,
    the red haired developer will confirm the pull request and therefore the changes will be upload to the original repository.**

![alt text](http://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)

**11. You have done your work and you can clean your "feature" branch with:**
	```
    git checkout master             # Change to branch master
    git branch -d iss<Z>            # Delete the branch in your local <forked remote repository>
    git push origin master          # Synchronize your origin master <forked remote repository>
    git push --delete origin iss<Z> # Delete the branch from origin <forked remote repository>
	```
