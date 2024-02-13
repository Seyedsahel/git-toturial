# Git for Beginners 

## intro

Changing a file -> stage -> commit

- An explanation for the git feature you asked

```sh 
git help 'feature name'
```

- Show status in the moment

```sh
git status 
``` 

-  untrackted file(U) : The file that Git does not track
-  modified file (M) : Changed file according to git
-  start with git repository in a dir

1- first command to start with git repository in a dir
```sh
git init
```

2-moving changes to stage 

for all

```sh
git add .
```

```sh
git add –A
```

for one file

```sh 
git add 'file name to track'
```  

3-commit the changes 

```sh
git commit -m "message"
```

4- 3 command on github page : for start with git hub too
- every commit (change a file in an available repo ***modified(M)*** ) 

```sh
git add .
```

```sh
 git commit -m "message"
```

```sh
git push 
``` 

- showing commit properties

```sh
git show 'commit path'
```

- Show your recent activity. one commit is tagged with ~head(last commit)

```sh
git log
 ```
 - show the changes of last commit(head) line by line 
```sh
git diff HEAD 
```

- show the changes in staged files
```sh
git diff --staged 
```
- unstaged a file
```sh
git reset 'filename'
 ```
- return file changes to last commit (then you need to commit)
```sh
git checkout –'file name' 
 ```
- delete a file in git and system
```sh
git rm 'file name'
 ```
- Showing the details of a line of code, for example, its author
 ```sh
git blame 'file name with extension ' 'from line number' , ' to line number'
 ```
Deleting commit

- show list of commits
```sh
git log —oneline
 ```
- deleting three last commit
```sh
git rebase -i Head~3 
 ```
- change pick to drop in text editor

branch
- show branches and current branch (current branch tagged with *)
```sh
git branch 
```
- creating new branch
```sh
git branch 'new branch name'
 ```
 - delete branch
 ```sh
 git branch –d 'branch name' 
  ```
- checkout to a branch 
```sh
git checkout 'branch name'  
```
- change branch name : 
```sh
git branch -m old-branch-name new-branch-name
 ```
  ***if you use git hub too, you should push changes to git hub.*** 
 ```sh
git push origin -u new-branch-name
 ```

- merge two branch (master with temp): 
```sh
git checkout master
 ``` 
```sh
git merge temp
```
Git hub
- clone a project from git hub
```sh
git clone 'project github link'
```
- origin : when you clone a repo from a outrepo like git hub that repo in your local named master and in git hub named origin/master or just origin
- send changes from local(master) to git hub(origin)
```sh
git push origin master
```
- get changes from git hub(origin) to local(master) ***contribute to a project***
```sh
git pull origin master
```         
***git push –u origin master , you don’t have to write origin master after that***
- git remote
```sh
git remote add 'remote name(origin)' 'remote link'
```

***a project can have several remotes***


Conflict

***two changes in a same file at a time***
- pull first(get changes from origin)
- if git auto merge two changes , you just commit and push changes

***if changes was in two different part of file git can auto merge***
- else : edit the changes by urself and commit and push  

tag
- show list of tags
```sh
git tag
```
- Tagging a commit to identify versions
```sh
git tag –a 'version name' -m 'message' 
```
- tag a older commit
```sh
git tag –a 'vesion name' 'commit path' -m 'message' 
```
- to find a tag by name or part of the name
```sh
git tag –l '”name tag to find or Part of the tag name*”' (Necessary:”*) 
```
- push the tags to origin(git hub) 
```sh
git push origin 'tag name' 
```
-  push all tags
```sh
git push origin –tags
```
- checkout to a version
```sh
git checkout 'tag name'
```

Sign

***first you need to create a sign key with a signature like pgp**
- set a signing key to get
```sh
git config –global user.signingkey 'secret key id'
```
- sign the tags
```sh
git tag –s –a 'version name' -m 'message' 
```
-  sign the commits
```sh
git commit –S –m 'message'
```

Debug

***Imagine you are in a situation where you have a bug in your code, but you don't exactly know when it was introduced. However, you can identify a commit within the commit history where the bug did not exist. In such a case, you can make use of this Git feature. The feature is bisect***
```sh
git bisect start
```
```sh
git bisect bad 'commit path that has the bug' 
```
or if you in a trable now you can write nothing
```sh
git bisect good A commit that does not have the bug'
```
This will return you the commit from which the error seems to have occurred and switches to that commit. And you have to tell the algorithm whether there is an error in the commit given to you or not with the command  “git bisect bad” or “git bisect good”
You can continue this process until you find the exact commit in which the error occurred

***It works with binary search algorithm***

Pull request

In Github or Gitlab, there is something called Pool Request or Merge Request, by which you can clone or fork a project and change something in it, request the main developer of the project to add the change to her/his own project.
