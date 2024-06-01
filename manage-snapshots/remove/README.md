[Home](../../README.md)

# Deleting Files in Git

![remove](remove.gif)

Let’s say you have a Git project folder called Mars. Inside this folder, there are two files: file1.txt and file2.txt.

```
Mars/
├── file1.txt
└── file2.txt
```

If you want to delete file2.txt, you might initially use the `rm` command:

```bash
rm file2.txt
```

After deleting the file with `rm`, you might want to check the status of your repository to see the changes you’ve made.

```bash
git status
```
 So the output will indicate that `file2.txt` is deleted from the working directory but not yet staged for removal:

```plaintext
On branch main
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    file2.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

After using `rm file2.txt`, you need to tell Git about the deletion. You do this by staging the deleted file:

```bash
git add file2.txt
```

However, there’s a more efficient way to do this.

Instead of using two separate commands, you can use `git rm` to delete the file from the working directory and stage the deletion in a single step:

```bash
git rm file2.txt
```

This command removes `file2.txt` from both the `working directory` and the `staging area` in one go.

Now you might want to check the status of your repository.

```bash
git status
```

The output will show that `file2.txt` is deleted and staged for removal:

```plaintext
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    file2.txt
```

After using `git rm` and checking the status, you need to commit the changes to your repository:

```bash
git commit -m "Removed file2.txt from the project"
```

[Home](../../README.md)