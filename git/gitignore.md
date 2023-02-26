# Gitignore.

This is a documentation of writing your .gitignore files for ignoring files in projects.

## Directory setup.
In the root of your project directory, is where you create the .gitignore file.
In most linux distributions, when a filename begins with a dot (.) the file is considered hidden. But you can show it
with the `ls -a`. The  `-a` flag will show the hidden files in the directory. 

## Add to your repo.
When the file is created, you might want to add it to your repo by commiting any changes made in the directory. Do so by
```sh
git init
git add .
git commit -m "first commit"
```

## Adding files and dirs to be ignored.
The gitignore handle's file ignoring quite easily, just by writing the name of the file or folder in the .gitignore file, the file will be ignored.
The file also accept's some regex, so you could do 
```
# .gitignore file

# files that end with bak & log
*.bak
*.log

# specific files
a.bak

# except these files (!)
!b.bak

# files in the root directory
/logs/
/tests
```

All these files will be ignored globall in from the project directory.
Meaning, all sub directories will also be affected if not explicitly
specified by user.

## Fixing the git tree.
Sometimes you might have already added some files to git for tracking and commited changes.
So when you add the filenames to be ignore, because they have already been commited, git still keeps trackes
of the file. **You would have to remove from git tree**. Meaning, you would have to 
prevent git from keeping track of the file.

- First list all the directories and files git is tracking like so ;
  `git ls-tree --name-only --full-tree -r HEAD`

- This will list all files being tracked by git in a tree structure to show all parent directories of files.
  To remove a file from the tree (**Prevent git from tracking that file**), run the following git command.
  `git rm --cached <relative-file-path-from-project-root>`

- Change the `<relative-file-path-from-project-root>` to the complete relative path of th file you wanna remove from the tree.

- Now add and commit changes,
  ```sh
  git commit -am " removed some files from the git tree. "
  ```
