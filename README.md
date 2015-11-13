`pretty-git-log` output with comments (before adding `README.md`)

tips of branches are enclosed in parenthesis:

    * afb62fe	 (topicA) 6 update class2  \
    * aebc75d	 4 add class2              /---- two commits rebased via `git rebase master`
    * 95a7e8f	 (master) 3 more code
    * e12dc38	 2 cherry pick
    * d4766e9	 1add some code
    | * d87c01c	 (oldTopicA) 6 update class2    <---- copy of branch topicA after commit '#6'
    | * 6c5c3b0	 2 cherry pick                  <---- cherrypicked commit e12dc38
    | * eeca5b8	 4 add class2
    |/  
    * e9e0337	 add test.java                  <---- initial commit for repo

Branch `oldTopicA` was created to demonstrate what was done by rebase. It
shows the state of `topicA` before rebase.

Branch `topicA` had 3 commits on top of initial commit: #4, cherrypicked and #6.

After rebase `topicA` has only 2 commits: #4 and #6.

Here is why : while rebasing, git detected that 6c5c3b0 is the same as e12dc38, so 6c5c3b0
does not appear in branch `topicA`.

https://github.com/rybak/git-cherry-pick-test/network --- shows graph
similar to `pretty-git-log`, might be helpful.
