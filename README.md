# Hello world

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
git add file1 file2
```

Commit all files in the staged zone into the repository

```
git commit -m "wrote a readme file"
```
