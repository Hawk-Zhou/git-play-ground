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

While adventure on another branch is going on, here's some change in this file on the main.