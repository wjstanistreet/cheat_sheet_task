# Terminal and Git Command Line Cheat Sheet!

# Terminal Basics

- The tilde key `~` indicates the home directory.
>Tip! Typing ~ on its own will return you to the machine's home directory (you can also type cd).
- A fullstop `.` indicates the current directory or selects everything within.
- 2 fullstops `..` is the parent directory of the current directory, AKA, the child.
- You can use shell logic operators, like `&&`, to chain commands together.


## Navigating the terminal
### `cd`:

- `cd` stands for `c`hange `d`irectory and will navigate to the chosen directory - e.g. Navigating from **~** ***(home directory)*** to the directory **Documents**:
    
    input:
    ```
    → ~ cd Documents 
    ```
    output:
    ```
    → Documents
    ```

  
- You can 'chain' directories to navigate to the directory you want in a single line - e.g. Navigating from **~** to **day_02**:

    input:
    ```
    → ~ cd Documents/__BNTA__/coursework/week_01/day_02
    ```
    output:
    ```
    → day_02
    ```
    >Tip! Pressing tab **⇥** will autocomplete what you're typing.
    >If the directory has multiple autocomplete options, use **⇥** to navigate through them. 

- Using a `-` after `cd` will return to the parent directory - e.g. Navigating from **__BNTA__** to **Documents**:

    input:
    ```
    → __BNTA__ cd - 
    ```
    output:
    ```
    → Documents
    ```

### `ls`:

- `ls` stands for `l`i`s`t and will display all unhidden files and folders within a current directory - e.g. listing all unhidden files in **__BNTA**:

    input:
    ```
    → __BNTA__ ls 
    ```
    output:
    ```
    CV          c7_coursenotes          coursework
    ```
- You can add flags to some functions to specify extra details by adding `-` and a character - e.g. listing all files in **__BNTA**:

    input:
    ```
    → __BNTA__ ls -a
    ```
    output:
    ```
    .          .DS_Store          c7_coursenotes
    ..         CV                 coursework
    ```
- A table of some flags:
    | Flag      | Description |
    | ----------- | ----------- |
    | ls -a      | All files       |
    | ls -l   |  Details       |
    | ls -S     | Sort by file size |
    | ls -r   |  List in reverse       |
    
## Creating and modifying files/folders
### Creating:
### `mkdir`:
- `mkdir` stands for `m`a`k`e `dir`ectory and will create a directory within the current directory - e.g. Creating a directory **week_02** in **coursework** and lists the directories:

    input:
    ```
    → coursework mkdir week_02 && ls
    ```
    output:
    ```
    week_01       week_02
    ```

### `touch`:
- `touch` will create a file within the current directory - e.g. Creating a file **test.txt** in **week_01** and lists the directories:

    input:
    ```
    → week_01 touch test.txt && ls
    ```
    output:
    ```
    day_02       test.txt
    ```
    
    > According to [DopeGhoti](https://unix.stackexchange.com/questions/355168/what-does-touch-stand-for) on StackOverflow, `touch`ing a file is named as such because you're "putting fresh fingerprints on it."

### Modifying:
### `mv`:
- `mv` stands for `m`o`v`e and will move a file to a different directory - e.g. Moving **test.txt** in **week_01** to **week_02**:

    input:
    ```
    → week_01 mv test.txt ~/Documents/__BNTA__/courseworks/week_02
    ```
    in **week_02**:
    ```
    test.txt
    ```

- `mv` can be used to rename files - e.g. Renaming **test.txt** to **anothertest.txt**:

    input:
    ```
    → week_02 mv test.txt anothertest.txt && ls
    ```
    output:
    ```
    anothertest.txt
    ```

### Removing:
### `rm`:
- `rm` stands for `r`e`m`ove and will remove a selected file in the current directory - e.g. Removing **anothertest.txt** in **week_02**:

    input:
    ```
    → week_02 rm anothertest.txt && ls
    ```
    output:
    ```
    
    ```

    - To remove a directory you need to recursively remove everything contained within it. This can be done by adding `-r` after `rm` - e.g. Removing **week_02** from **coursework**:

    input:
    ```
    → coursework rm -r week_02 && ls
    ```
    output:
    ```
    week_01
    ```


# Git Commands:

Git allows a developer to track and manage changes of their software via *version control*. By exporting to GitHub, code can be sent to the cloud which safeguards it, while allowing other devs to view and work on each other's code.  

Git can be controlled through the terminal using functions defined by Git.

## Setup:
To create a Git repository, a base directory is needed. This can be a new dir, created using `mkdir`, or an prexisting dir. 

1. Firstly, navigate to your chosen directory and intialise it using `git init`.

### `git init`:
- `git init` will initialise the current directory, creating a new git repo - e.g. Initlisation of **cheat_sheet_task**:

    input:
    ```
    → cheat_sheet_task git init
    ```
    output:
    ```
    Initialized empty Git repository in /Users/willsmacbook/Documents/__BNTA__/coursework/week_01/day_02/cheat_sheet_task/.git/
    → cheat_sheet_task git:(main)
    ```


2. The files within the new repo need to be 'staged' and can be added using `git add`.

### `git add`:
- `git add` will add a single or multiple files to the stage - e.g. Adding all files from **cheat_sheet_task**:

    input:
    ```
    → cheat_sheet_task git:(main) git add .
    ```
    output:
    ```
    → cheat_sheet_task git:(main) 
    ``` 
    > A single file can be added by specifying the file itself - e.g. `git add cheat_sheet_task.md`.


3. Any changes that are added to the stage can be finalised locally by `commit`ing the changes to git.

### `git commit`:
- `git commit` will commit all staged changes to the local repo. It's common practice to add a message to the commit to document what has been changed. This is done by adding the flag `-m` followed by the message as a string - e.g. Commiting all staged files from **cheat_sheet_task**:

    input:
    ```
    → cheat_sheet_task git:(main) git commit -m "Commit message"
    ```
    output: (where N is a number)
    ```
    [main #######] Commit message
    N file changed, N insertions(+), N deletions(-)
    ``` 
    
4. Once the first commit is done, a repo needs to be created on a GitHub. After a remote repo is created, it needs to be connected to your local repo using `git remote add origin 'Github repo address'`, followed by `git push origin main` to push the local files

### `git push`:
- `git push` will push all comitted changes from the local repo to a remote repo - e.g. Pushing all commited files from **cheat_sheet_task**:

    input:
    ```
    → cheat_sheet_task git:(main) git push
    ```
    output:
    ```

    ``` 

5. Any changes to your local repo can be pushed to your remote repo by repeating this process, starting with:
    1. `git add .`
    2. `git commit -m "_____"`
    3. `git push`

### `.gitignore`:
- `touch .gitingore` will create a `.gitignore` file which allows hide specific files/folders from being pushed to GitHub. The file itself will still be tracked.
