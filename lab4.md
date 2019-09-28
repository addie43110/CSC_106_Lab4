# Introduction to the Linux Command Line

The following is a set of instructions adapted from "Introduction to Linux: Exercises" from the University of Finland.

## What is the `$` and `<command>`?
Commonly, the symbols `$` or `>` represent the _command prompt_, or the place where you are supposed to begin typing your command. Thus, _do not_ type the `$` symbol as part of the command.

Additionally, arguments to commands are typically written in angled brackets. When you write your command, you should not include those brackets.

## Downloads
Download the tar.gz file `linux-exercise.tar.gz` from Connex.

## Where are we?

Next, open the terminal or bash shell. You can either click on the application at the bottom of your screen, or use the keyboard short-cut, ctrl-alt-t.

To find out where you are in your file system, type:

```
$ pwd
```

`pwd` stands for 'print working directory'. To see what folders and files are in your current folder, use:

```
$ ls
```

Some familiar folder names should appear as output on your screen.

To _change_ into your Downloads folder, type:

```
$ cd Downloads
```

`cd` stands for 'change directory'. Note that the Linux bash shell is case sensitive, so `downloads` is different from `Downloads`. To check that you have successfully entered the Downloads folder, use the `pwd` command again, or check the files listed in the folder using `ls`. 

## tar.gz

What is a tar.gz file? You can think of it simply as a zip file. It compresses folders and/or files into something smaller so that they can be sent more easily. Of course, that means that we need to expand or 'unzip' this tar.gz file.

```
$ tar zxvf linux-exercise.tar.gz
```

## Exercise 1: Moving around

Use the `ls` and `cd` commands to move around the directory tree. If you encounter more tar.gz files, extract them using `tar zxvf` as before.

## Exercise 2: Grep

`grep` is a powerful command that uses regular expressions to search for strings in files. We will use it to find out which .pdb files contain the word 'caffeine'. Use the following commands to try to find out which files have the word 'caffeine'.

```
$ grep caffeine *.pdb //searches all .pdb files
$ grep caffeine */*.pdb //searches all children .pdb files
```

To view the contents of a file, use the command:

```
$ cat <file>
```

## Exercise 3: Create subfolders

There should be 3 result\* folders. Create two more called `result4` and `result5` using the command:

```
$ mkdir <foldername>
```

Then, move the output files `out_4.pdb` and `out_5.pdb` to those respective new folders using the command:

```
$ mv <file> <destination>
```

## Exercise 4: `man`, the Linux manual

To look at the Linux manual pages, use the command

```
$ man <command>
```

Use this command to read the manual pages for the command `ls`. Look for the flag that will sort the output of `ls` by size. Hint: you may find it helpful/interesting to search the man page using `/sort`. This will search the page for any instances of the word 'sort'. You can press `n` to proceed to the next occurrence of the word.

Once you have found the command, use it to sort the output by file size.

Next, search the man page again for the flag that will sort the output in reverse order by size (ie. print the largest file last). Note: you can combine the flags together:

```
$ ls -flag1 -flag2 //okay
$ ls -flag1flag2 // this is better
```

## Exercise 5: `*` Wildcards (optional activity, if time permits)

You may have noticed we used the `*` character earlier on. It is called a 'wildcard' and indicates part of a string that we either don't know or do not care about it.

Examples:
- `*potato` matches the strings `potato`, `1potato`, `20potato`, `yeaaeeeeepotato`, etc.
- `potato*` similarly matches the strings `potato`, `potato1`, `potato12`, `potatofoobar`, etc.

Thus, we say that the wildcard symbol matches 0 or more characters.

Another character, the `?` matches exactly one character.

Examples:
- `p?tato` matches `potato`, `p0tato`, `p2tato`, `pntato`, etc.
- `????` matches any string with exactly four characters

Exercises:
- list only those files that have an 'a' in the name and end in '.pdb'
- list those files that have a name with exactly 7 characters and end in '.pdb'
