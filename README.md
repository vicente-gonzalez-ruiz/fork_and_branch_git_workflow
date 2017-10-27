# fork_and_branch_git_workflow
https://blog.scottlowe.org/2015/01/27/using-fork-branch-git-workflow/

1. Fork the "upstream" (with URL: <X>) repository (do that in upstream's GitHub page).
   A new repository (with URL: <Y>) in your GitHub account should appear.

2. Clone your forked repository <X>:

    git clone <Y>

   This is necessary to contribute over a local copy, otherwise, you should be always
   connected to the Internet and use the GitHub facilities.

3. At this moment, your local copy of <X> is only connected to your remote
   repo <X> at GitHub. You can check this with:

    git remote -v

   In order to make easuer future updates of your forked repo <Y> with possible
   commits to <X>, add a new remote named "upstream" with:

    git remote add upstream <X>

   (<X> can be found in the "Clone or download" button of the original <X> repository)

4. Revise the list of open issues at <X> (not at <Y>, you won't be able to find
   issues at <Y> at this moment) and select one, for example, iss<Z>, where <Z> is
   the issue number that GitHub automatically generates for every new branch. With
   the aim of working in iss<Z>, create a new "feature" branch (in your local copy
   of <Y>) with:

   git checkout -b iss<Z>

   you will be switched to new bran iss<Z>, something that can be checked with:

    git branch

5. Perform your modifications and keep your repos, both local <Y> and
   remote <Y> updated. Basically:
   
   1. Use:
   
   git add <new_file>
   
   
