`pretty-git-log` output with comments

tips of branches are enclosed in parenthesis

    * afb62fe	 (topicA) 6 update class2  \
    * aebc75d	 4 add class2              |
    * 95a7e8f	 (master) 3 more code      |>---- rebased via `git rebase master`
    * e12dc38	 2 cherry pick             |
    * d4766e9	 1add some code            /
    | * d87c01c	 (copyOfTopicA) 6 update class2   <---- copy of branch topicA after cherry-pick and commit '#6'
    | * 6c5c3b0	 2 cherry pick                    <---- this was cherry picked from commit e12dc38 on branch master # consider this commit #5
    | * eeca5b8	 4 add class2
    |/  
    * e9e0337	 add test.java                    <---- initial commit for repo

Branch `copyOfTopicA` was created to demonstrate what was done by rebase. It
is not involved in other manipulations with repo.

Notice that there is no commit between commit #4 and commit #6 in branch
`topicA`.

Here is why : While rebasing, git detected that 6c5c3b0 is the same as e12dc38, so 6c5c3b0
does not appear in branch `topicA`.
