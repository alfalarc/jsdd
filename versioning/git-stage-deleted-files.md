[JSDD](../README.md) &gt; [Start with Git](git-start.md) &gt; stage deleted files from anywhere in the working tree

# How to stage deleted files from anywhere in the working tree

You have deleted or renamed some files and they appear as deleted in your ```git status``` result:
```bash
$ git status
# On branch master
# Changed but not updated:
#   (use "git add/rm <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
# deleted:    path/to/deleted_file
# deleted:    otherpath/to/other_file
# deleted:    yetanotherpathto/anotherone
#
```

You can't use ```git rm .``` to stage all the deletions at once, because this would wipe out all your working directory.
To stage these deleted file and not touch anything else, you can just do:
```bash
git add -u .
```

Et voilà !
```bash
$ git status
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
# deleted:    path/to/deleted_file
# deleted:    otherpath/to/other_file
# deleted:    yetanotherpathto/anotherone
#
```
