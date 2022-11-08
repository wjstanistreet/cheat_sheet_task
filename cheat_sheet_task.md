# Terminal and Git Command Line Cheat Sheet!

# Terminal Basics: 

- The tilde key `~` indicates the home directory.
>Tip! Typing ~ on its own will return you to the machine's home directory (you can also type cd).
- A fullstop `.` indicates the current directory.
- 2 fullstops `..` is the parent directory of the current directory, AKA, the child.


## Navigating the terminal:
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
    

<!-- > According to [DopeGhoti](https://unix.stackexchange.com/questions/355168/what-does-touch-stand-for) on StackOverflow, `touch`ing a file is named as such because you're "putting fresh fingerprints on it." -->