### upload changes of your own repo from vs code to github

1. **clone** the repo from GitHub to local within vscode
2. make some changes about the cloned repo
3. Activate **terminal**

4. In terminal( see more down below)

`git status`

this allows you to check which changes you have made

you may see something like this:

```On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        description.c

nothing added to commit but untracked files present (use "git add" to track)
```

if your change is editing an existing file, please use `cmd+s` to save your change within the file before rushing into the next step.

Next:

`git add .`^1^

[^1]:`.`means every single file in the present repo, including the original ones that you clone from GitHub, and the new files if you have created one of those.

or

`git add new.md` (depending on in which file you have made your changes)

(after this, you can check git status again, which may show:)

```On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   description.c
```

Then:

`git commit -m "add a new flie"`

you may see:

```[main 4f7efce] a new c file added
[main 4f7efce] a new c file added
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 description.c
```

Now the change is committed, you are ready to push the commit to github

if you check the git status, you  may see:

```
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

Now:

`git push origin main`

now you see:

```
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 244 bytes | 244.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/G-Kent-kk/AdvancedGithubFeaturesDemo.git
   6c8abaf..4f7efce  main -> main
```

Now refresh your github repo page, you can see the changes in live!



### some notes that worth extra attention

#### please strictly follow the order of the given steps.

---

#### Don't forget about saving your changes before `git add` command

---

#### the differences between git add and git commit:

- the former means that you save your changes in a buffer, that is:

  **add your modified files to the queue *to <u>be committed</u> later*.**

- the latter means that you commit those changes in the buffer or the waiting queue. **Anthing that is outside of the buffer has no chance of being committed.** So make sure that the  `git add` command cover all the changes you make.



## Above we have mastered committing changes locally and synchronize with github. 

## Creating commits on the github website, on the other hand, is very easy.



### when creating, editing and uploading a repository locally 

Instead of cloning a repo from GitHub and make changes on top of that, we need to use the `git init` in the directory of the new folder we created. The automatically created `.git ` file is the sign of successfully creating a git repo to be uploaded.

After adding and editing files to the git folder (after `git add` and  `git commit`), we are in the stage of putting it on live.

But when you use the `git push`, you may find errors like below:

```
gyc@hcks-MacBook-Pro new % git push origin main
error: src refspec main does not match any
error: failed to push some refs to 'origin'
```

now we need to connect this local git folder the a repo remote on github

1. create a new repo on github
2. Use the `git remote add origin` command+ address to link to your new repo on github













