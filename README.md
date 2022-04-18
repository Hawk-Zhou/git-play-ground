# gitPlayGround

adventure a little bit here

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
    git reset --soft [hash]
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

While adventure on another branch is going on, here's some change in this file on the main.