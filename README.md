# gitPlayGround

## Big Update

After reading a recent post explaining how to use git in a team like a pro on the forum of my univ, I followed and tried the teamwork approach and found it very useful.  

A and B get to work on new features. They branch to `feat/A` and `feat/B` respectively. B finished and `git push origin feat/B` and submitted a merge request, which is approved later. A is still working and noticed this. What A needs to do is that:  

```
// get the latest main
git checkout main
git pull origin main

// save work now
git checkout feat/A
git add .
git commit -m "WIP:feat" // WIP means work in progress

// rebase main on feat/A
git rebase main // this will put main's commits on top of A
// if there's any conflict, fix each
git add [conflict file]
// after every conflict is resolved
git rebase --continue

// now it's safe to keep working

// after A finished and staged changes
git commit --amend // this modifies the last commit, the "WIP" one, rewrite a good message

// submit a merge request
```

After these, A and B will get a perfect graph like this:  
![image](https://user-images.githubusercontent.com/76863396/181904232-8cbb8540-19cc-47e0-b22e-49cc8eaf509a.png)


## Soft reset
```
    git reset --soft [hash]
    // discard staged changes
    // discard changes
    git push -f origin main
``` 

## Hard reset  
 (don't do it if someone else is also working on this, use revert)  
```
    git reset --hard [hash]
    // this will point the branch and the head to the commit [hash]
    // and also change everything in the directory to the state of the commit
    git push -f origin main
```

## Revert
```
    git revert HEAD
    // this will create an 'anti-commit'
    // that reverts all changes in HEAD
```

## How to branch
Say, you try to add one function, while another teammate is working on another one.  
Don't do it sequentially and wait teammate san to commit before you can start.  
Branch.
```
    git checkout -b <branch-name>
    // then follow the GUI to push it to remote
```
Then you work. After its done, just push it to your branch.
When teammate san finishes, he/she will just push to main and then
```
    git fetch origin <branch-name>
    // pull your branch
    git checkout <branch-name>
    git merge main
    // not sure why after merging to main,
    // main is behind <branch-name>
    // so we should also bring it to the latest
    git checkout main
    git merge <branch-name>
```
