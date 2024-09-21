# Learn Git by Building an SQL Reference Object

## 1. View all files in a folder
In Git, you can use the following command to see all files in a folder:
```bash
ls -a
```
This will show hidden files as well, such as the `.git` folder in the directory you are in.

## 2. Create and switch to a new branch
To create and switch to a new branch, use the command:
```bash
git checkout -b new_branch
```

## 3. View changes in a file
To see changes in a file, you can use:
```bash
git diff
```

## 4. Delete a branch
To delete a branch, use the following command:
```bash
git branch -d branch_name
```
`-d` stands for "delete". This is safe to do if your changes have been added or merged.

## 5. Merge branches
To merge branches, use:
```bash
git merge branch_name
```

## 6. Rebase a branch
To rebase a branch against `main` so that it has the same commits, you can use:
```bash
git rebase main
```

## 7. Stash changes
To stash changes, use the following command:
```bash
git stash
```

## 8. View stashed changes
To view the list of stashed changes, use:
```bash
git stash list
```

## 9. Pop stashed changes
To bring back the changes from your stash, use:
```bash
git stash pop
```

## 10. View a condensed version of the changes in the latest stash
To see a condensed version of the changes in the latest stash:
```bash
git stash show
```

## 11. View full changes in the latest stash
To view the full changes of the latest stash with patches, use:
```bash
git stash show -p
```
`-p` stands for "patch", and this will show detailed changes made to the files.

## 12. Apply a stash without dropping it
To apply the latest stash without removing it from the list, use:
```bash
git stash apply
```
This method keeps the stash in the list, useful for applying the changes to your current working directory while maintaining a copy in the stash.

## 13. Access specific stashes
You can reference a specific stash using its name, like `stash@{#}`:
```bash
git stash show stash@{0}
```
`stash@{0}` refers to the most recent stash. If you have multiple stashes, the next oldest would be `stash@{1}`, and so on.

## 14. Delete a stash
To delete a specific stash from your list:
```bash
git stash drop stash@{#}
```
Replace `#` with the stash number to delete it.

## 15. Reset to a previous commit
To travel back in time to a specific commit, use the following command:
```bash
git reset HEAD~1
```
`HEAD~1` will reset to the last commit, and you can replace `1` with the number of commits you want to go back.

### Git reset options:
- **Mixed reset**: This will undo the commit and put the changes into the working directory.
- **Hard reset**: This will completely remove the changes.
- **Soft reset**: This will keep the changes in the working tree and stage them.

```bash
git reset --hard HEAD~1
git reset --soft HEAD~1
```
The `--hard` flag will discard the changes, while the `--soft` flag will keep them staged.

## 16. Revert a commit
To revert the most recent commit (HEAD), use:
```bash
git revert HEAD
```
This is a good way to undo a commit without losing it from history.

## 17. Interactive rebase
To enter "interactive" mode to manipulate commits, use:
```bash
git rebase --interactive HEAD~2
```
The `HEAD~2` means you'll be able to modify the last two commits.

## 18. Drop commits during rebase
When in interactive mode, you will see the commits listed with `pick` next to them. To drop a commit, replace `pick` with `d` for both commits, save, and exit the editor.

## 19. Rebase back to the root
To go back to the very first commit (root) and change a commit message, you can use:
```bash
git rebase --interactive --root
```
This command will allow you to manipulate the first commit and beyond.
