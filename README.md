# Git Hello World

## Use of Git locally

### Installation

In Linux: `sudo apt-get install git`

### Use

1. Initialize a git repository

Open a directory.
```
mkdir learngit
cd learngit
```

Make the directory a git repository.

```
git init
Initialized empty Git repository in /Users/ysiad2001/learngit/.git/
ls -a
.  ..  .git
```

The `.git` contains config files for git.

2. Edit and commit

Create a file.

```
touch README.md
vim README.md
# edit the file
```
Add the file to the staged zone (It is possible to add multiple files to the staged zone.)

```
git add README.md
git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md

git add file1 file2 file3
```

Commit all files in the staged zone into the repository

```
git commit -m "wrote a readme file"
```

3. Restore the workspace with a staged version

```
git checkout -- README.md
```

4. Restore the workspace to a earlier commit version 

Check the commit log

```
git log
commit c547be2c09a1f65e17f8dc0447b1e1545a04fe53 (HEAD -> master)
Author: ysiad <1980449502@qq.com>
Date:   Mon Aug 9 01:30:38 2021 +0800

    Something

commit c1b82deaffd8ba89e74a59f9c0f806b4283525fe
Author: ysiad <1980449502@qq.com>
Date:   Mon Aug 9 01:29:50 2021 +0800

    Something
```

Restore to a previous version. Here `HEAD^` means the second to last commit. `HEAD^^` means the third to last, etc. 

```
git reset --hard HEAD^
```

Now the last commit is removed from log. However, it can still be restored from the commit ID

```
git reset --hard c547b
```
In case you forget the commit ID

```
git reflog #example
e475afc HEAD@{1}: reset: moving to HEAD^
1094adb (HEAD -> master) HEAD@{2}: commit: append GPL
e475afc HEAD@{3}: commit: add distributed
eaadf4e HEAD@{4}: commit (initial): wrote a readme file
```

5. Remove files

Remove a file from the workspace

```
rm README.md
```

Remove that from the repository as well...

```
git rm README.md
```

...Or restore that from the repository

```
git checkout README.md
```

## Use of git remotely