Tips of branches are enclosed in parenthesis.
Newer commits appear higher.

Before rebase:

Branch `topicA` had 3 commits on top of initial commit: #4, cherrypicked and #6.

    * d87c01c	 (topicA) 6 update class2
    * 6c5c3b0	 2 cherry pick                  <---- cherrypicked commit e12dc38
    * eeca5b8	 4 add class2
    | * 95a7e8f	 (master) 3 more code
    | * e12dc38	 2 cherry pick
    | * d4766e9	 1add some code
    |/  
    * e9e0337	 add test.java

After rebase:

`topicA` has only 2 commits on top of `master`: #4 and #6, commit 6c5c3b0 is no
longer in log:

    * afb62fe	 (topicA) 6 update class2
    * aebc75d	 4 add class2
    * 95a7e8f	 (master) 3 more code
    * e12dc38	 2 cherry pick
    * d4766e9	 1add some code
    * e9e0337	 add test.java

Explanation : while rebasing, git detected that 6c5c3b0 is the same as e12dc38, so 6c5c3b0
does not appear in branch `topicA`.

https://github.com/rybak/git-cherry-pick-test/network --- shows graph
similar to `pretty-git-log`, might be helpful.

Branch `oldTopicA` was created only to preserve commits on github.
It shows the state of `topicA` before rebase.

Links to commits :

* [`afb62fe`](https://github.com/rybak/git-cherry-pick-test/commit/afb62fe)
* [`6c5c3b0`](https://github.com/rybak/git-cherry-pick-test/commit/6c5c3b0)
* [`aebc75d`](https://github.com/rybak/git-cherry-pick-test/commit/aebc75d)
* [`95a7e8f`](https://github.com/rybak/git-cherry-pick-test/commit/95a7e8f)
* [`e12dc38`](https://github.com/rybak/git-cherry-pick-test/commit/e12dc38)
* [`d4766e9`](https://github.com/rybak/git-cherry-pick-test/commit/d4766e9)
* [`e9e0337`](https://github.com/rybak/git-cherry-pick-test/commit/e9e0337b84a60e56bc0d9a0a5d6fb21f59451f49)
