[Home](../../README.md)

# Renaming Files in Git

![rename](Rename.jpg)

Let’s say you have a Git project folder called Mars. Inside this folder, there are two files: file1.txt and file2.txt.

```
Mars/
├── file1.txt
└── file2.txt
```

If you want to rename `file2.txt` to `main.js`, you might initially use the mv command:

```bash
mv file2.txt main.js
```

After running this command, `file2.txt` is renamed to `main.js` in your working directory. However, Git does not automatically recognize this change. If you check the status using `git status`, you will see something like this:

```bash
git status
```

Output

``` plaintext
On branch main
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    file2.txt
        untracked:  main.js

no changes added to commit (use "git add" and/or "git commit -a")
```

To stage this change, you need to perform two separate operations:

```bash
git add file2.txt
git add main.js
```

Then, if you check the status again, you will see:

```bash
git status
```

Output

``` plaintext
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    file2.txt
        new file:   main.js
```

Instead of using two separate commands, you can use git mv to rename the file and stage the change in one step:

```bash
git mv file2.txt main.js
```

This command renames file2.txt to main.js and stages the change automatically. Now, if you check the status:

```bash
git status
```

You should see:

``` plaintext
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        renamed:    file2.txt -> main.js
```

After using `git mv` and checking the status, you need to commit the changes to your repository:

```bash
git commit -m "Renamed file2.txt to main.js"
```

[Home](../../README.md)