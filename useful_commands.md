------------------------------------------------------------------------

## General & Useful Commands for Terminal

#### Primarily made for Bioinformatics Bootcamp 2025

-   This is based on a personal file of mine, so apologies for odd
    formatting!

<br>

#### Hopefully you find some of these useful! p.s. I do not take responsibility for any laptop explosions and whatnot lol

<br>

------------------------------------------------------------------------

<br>

**(some) Shell Aliases** - these are also mentioned/explained when
brought up below!

| Command | Meaning                 | Easier                                     |
|---------|-------------------------|--------------------------------------------|
| cd      | change directory        | change directory/folder                    |
| pwd     | print working directory | current directory/folder                   |
| mv      | move/rename             | move/rename to \[new pathway/name\]        |
| rm      | remove                  | delete                                     |
| ll      | long list               | shows contents of current directory/folder |

<br>

------------------------------------------------------------------------

<br>

### Getting Around: General Navigation

<br>

``` bash
~
```

-   Takes you to your profile ‘home’ directory/folder (this is not your
    personal ‘scratch’ folder)
-   Can be done by simply entering ‘~’ or ‘cd ~’

``` bash
pwd
```

-   Print working directory = ‘pwd’, tells you the pathway for the
    directory you’re currently in

``` bash
mkdir
```

-   Make directory = ‘mkdir’, creates a new directory/folder

``` bash
cd [pathway/folder]
```

-   Change directory = ‘cd’, this moves you around the files (terminal
    is basically one huge filing system)

``` bash
cd ../
```

-   Changes the directory, back one folder/directory
-   Can do as many times as you want, for how far you want to go: ../../
    = back 2 folders, ../../../ = back 3 etc

``` bash
ll
```

-   Shows you the contents of the folder/directory you’re currently in

``` bash
ll ../
```

-   Shows you the contents of the previous folder/directory, whilst
    keeping you in your current folder
-   Can do as many times as you want, like ‘cd ../’ so: ll ../../ = view
    contents back 2 folders, ll ../../../ = view contents back 3 etc

``` bash
ll *[text]
```

-   Shows you everything that ends with \[text\]

``` bash
ll [text]*
```

-   Shows you everything that starts with \[text\]

``` bash
ll *[text]*
```

-   Shows you everything that contains \[text\]

``` bash
ll ./[shared file start name]*/
```

-   Shows everything in the folders/directories that start with \[shared
    file start name\]
-   i.e. if you have folders called \[Folder_1, Folder_2, Folder_3,
    etc\] = ll ./Folder\*/
-   Same concept applies as the other examples with asterisks (see above)
    i.e. starts/ends with \[text\], all folders that include \[text\]

``` bash
ll- h
```

-   Shows you the contents of a folder/directory using Gb and Mb, etc

<br>

### Editing: For files/scripts
Most of these are executed in the (to be) edited file, in edit mode. Open the file with 'vim', edit with 'i', stop editing with 'ESC'

<br>

``` bash
#
```

-   The computer won't read anything that begins with a hashtag
-   Good for annotating and adding instructions to scripts

``` bash
vim [file/script]
```

-   Edit a file/script
-   Actually inserting/editing the file is possible after pressing ‘i’,
    only once you’ve opened it with ‘vim’
-   Exit insert mode using ESC, saving/deleting/etc have to be done
    outside of insert/‘i’ mode

``` bash
:%d
```

-   In file/script editor: deletes ALL contents of slurm script, when
    you’re not in insert mode (‘i’ in vim)

``` bash
:w
```

-   In file/script editor: “writes” your changes on the slurm script, aka
    saves your changes
-   Have to exit editing mode first, via ESC

``` bash
:q
```

-   In file/script editor: closes slurm script, usually have to use save
    changes first with ‘:w’

``` bash
:q!
```

-   In file/script editor: force closes slurm script editing (vim),
    without saving

<br>

### File Viewing (Contents)

<br>

``` bash
less [file/script]
```

-   View contents of a file/script one page at a time, opens as a file,
    exit the viewing with ‘q’

``` bash
cat [file/script]
```

-   View contents of a whole file/script regardless of size, loads up
    the whole thing, opens **in the command line**
-   Don’t do this with massive files, you will regret it lol

``` bash
head [file/script]
```

-   View the first 10 lines of a file

``` bash
tail [file/script]
```

-   View the last 10 lines of a file

<br>

### Submitting Scripts

<br>

``` bash
sbatch [script]
```

-   Submits script/job to the queue

``` bash
squeue -u b.[hawk username]
```

-   Shows you your submitted/waiting/running jobs in the SCW queue

``` bash
squeue -u b.[hawk username] --start
```

-   Shows you the predicted start time for submitted/waiting jobs in the
    scw queue keep in mind it's not very accurate

``` bash
scancel [job id/number]
```

-   Cancels the specified job in the SCW queue, regardless of whether it's
    waiting or running

``` bash
seff [job id/number]
```

-   Shows you the job details/stats i.e. how long it took, CPU usage,
    etc for a completed job

<br>

### File/Directory Management

<br>

``` bash
rm [file]
```

-   Deletes a file
-   **Be careful with this, you CANNOT recover files**

``` bash
rm -i [file]
```

-   Will ask before it deletes a file

``` bash
rm -r [directory]
```

-   Deletes the directory and everything inside

``` bash
rm -d [directory]
```

-   Deletes the directory, only if it's empty

``` bash
rm *[text]
```

-   Deletes everything that ends in \[text\]

``` bash
rm [text]*
```

-   Deletes everything that starts with \[text\]

``` bash
rm *[text]*
```

-   Deletes everything that contains \[text\]

``` bash
cp [file/script] [new name/new location pathway]
```

-   Copies a file to a new version (with that new name), or makes a copy
    with the SAME name in a different directory

``` bash
mv [file/script] [new name/new location pathway]
```

-   Move = ‘mv’, can be used to rename files or move them to another
    directory/folder
-   The name will only be changed if it's a NEW name that does not
    already exist in the current directory
-   Moving the file to a new directory can be done by inserting the new
    location pathway after ‘\>’

<br>

### Other Useful Commands

<br>

``` bash
myquota
```

-   Shows how much storage you have in your project folders

``` bash
history
```

-   Shows you your last 500 entries in the command line, this will open
    in the command line (as opposed to a file)

``` bash
history | grep "[text]"
```

-   Shows you your last 500 entries in the command line, containing
    \[text\], this will open in the command line (as opposed to a file)

<br>

### More Specific Script-Related Commands

``` bash
cut -c1-[100] [alignment file]
```

-   Cuts the \[100\]th character from each line

``` bash
module avail [module/program name]
```

-   Shows available modules/versions i.e. module avail cons = what
    consensify modules/versions are there

``` bash
module load [module and version]
```

-   Loads up a module to use

``` bash
module purge
```

-   Clears all modules
-   Doesn’t always work, especially if you’re source activating
    environments etc - this won’t clear those

<br>

#### Hopefully you’ve found some of these helpful! Let me know if I can reword anything for future readers! :)

p.s. if you found any spelling mistakes, let me know! grammarly does not
work on Rmd lol

<br>
