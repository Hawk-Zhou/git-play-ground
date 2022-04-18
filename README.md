# gitPlayGround


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

## revert
```
    git revert HEAD
```