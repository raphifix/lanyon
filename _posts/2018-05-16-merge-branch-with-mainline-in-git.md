---
published: false
---
I was finishing up work on a feature addition to an internal R package and was ready to merge to branch into the mainline. I submitted my pull request to my manager, who approved it. Now for the nerve-wracking part: actually merging the branch!

It was less painful than I anticipated.

1. First, I had to switch back to the master from the commandline: `git checkout master`
2. Then, I merged the branch: `git merge branch_name`

I panicked because I tried to use `git push` and got the following error: `failed to push some refs...` Git reminded me that I was forgetting a step; I had to commit the merge.

3. I did so with `git commit -m 'commit message'`
4. Then I was able to push to the remote: `git push origin master`.