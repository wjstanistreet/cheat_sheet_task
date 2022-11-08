# Terminal and Git Command Line Cheat Sheet!

# Terminal Basics

- The tilde key `~` indicates the home directory.
>Tip! Typing ~ on its own will return you to the machine's home directory (you can also type cd).
- A fullstop `.` indicates the current directory.
- 2 fullstops `..` is the parent directory of the current directory, AKA, the child.
- You can use shell logic operators, like `&&`, to chain commands together.


## Navigating the terminal
### `cd`:

- `cd` stands for `c`hange `d`irectory which will navigate to the chosen directory - e.g. Navigating from **~** ***(home directory)*** to the directory **Documents**:
    
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


