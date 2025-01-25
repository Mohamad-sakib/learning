# input stream and output stream and error stream

# cut , unique , sort

# lc or lc -l

# pipling

# redirecting > using it streams

# Shell Wildcards and Patterns Table

| **Wildcard/Pattern**   | **Description**                                                                         | **Example**                | **Output/Behavior**                                   |     |     |
| ---------------------- | --------------------------------------------------------------------------------------- | -------------------------- | ----------------------------------------------------- | --- | --- |
| `*`                    | Matches **zero or more characters** in a filename or pattern.                           | `ls *.txt`                 | Lists all files ending with `.txt`.                   |     |     |
| `?`                    | Matches **exactly one character**.                                                      | `ls file?.txt`             | Lists `file1.txt`, `file2.txt`, but not `file10.txt`. |     |     |
| `[ ]`                  | Matches **any one character** from the specified set.                                   | `ls file[123].txt`         | Lists `file1.txt`, `file2.txt`, and `file3.txt`.      |     |     |
| `[! ]`                 | Matches **any one character not in the specified set**.                                 | `ls file[!1].txt`          | Lists all files except `file1.txt`.                   |     |     |
| `{ }`                  | Matches a **comma-separated list** of patterns.                                         | `ls file{1,2,3}.txt`       | Lists `file1.txt`, `file2.txt`, and `file3.txt`.      |     |     |
| `{..}`                 | Matches a **range of numbers or letters**.                                              | `ls file{1..5}.txt`        | Lists `file1.txt` to `file5.txt`.                     |     |     |
| `!(pattern)`           | Matches **everything except** the given pattern (requires `extglob` in bash).           | `ls !(file.txt)`           | Lists all files except `file.txt`.                    |     |     |
| \`@(pattern1\|patter2) | Matches eactly one pattern (requires extglob in bash).                                  | \`ls @(file1\|file2).txt\` | Lists file1.txt and file2.txt.                        |     |     |
| `+(pattern)`           | Matches **one or more occurrences** of the given pattern (requires `extglob` in bash).  | `ls +(*.log)`              | Lists `.log` files if present.                        |     |     |
| `^(pattern)`           | Matches **everything except** the given pattern (requires `extglob` in bash).           | `ls ^(file.txt)`           | Lists everything except `file.txt`.                   |     |     |
| `^`                    | Matches the **start of a line** (used in `grep` or regex, not typical shell wildcards). | `grep "^apple" file.txt`   | Finds lines starting with `apple`.                    |     |     |
| `$`                    | Matches the **end of a line** (used in `grep` or regex, not typical shell wildcards).   | `grep "apple$" file.txt`   | Finds lines ending with `apple`.                      |     |     |

---

# `grep` Command Attributes Table

| **Attribute**     | **Description**                                                          | **Example**                        | **Output/Behavior**                                  |
| ----------------- | ------------------------------------------------------------------------ | ---------------------------------- | ---------------------------------------------------- |
| `-i`              | Perform a **case-insensitive** search.                                   | `grep -i "apple" file.txt`         | Matches `apple`, `Apple`, `APPLE`, etc.              |
| `-v`              | **Invert match**, showing lines that do not match the pattern.           | `grep -v "apple" file.txt`         | Lists all lines except those containing `apple`.     |
| `-c`              | **Count** the number of matching lines.                                  | `grep -c "apple" file.txt`         | Displays the count of lines containing `apple`.      |
| `-l`              | List only the **filenames** of files with matching lines.                | `grep -l "apple" *.txt`            | Displays filenames containing `apple`.               |
| `-L`              | List only the **filenames** of files without matching lines.             | `grep -L "apple" *.txt`            | Displays filenames that do not contain `apple`.      |
| `-n`              | Display **line numbers** along with the matching lines.                  | `grep -n "apple" file.txt`         | Shows matching lines with line numbers.              |
| `-o`              | Show **only the matching part** of lines.                                | `grep -o "apple" file.txt`         | Displays only `apple` where it appears in the lines. |
| `-r` or `-R`      | Recursively search directories for matching files.                       | `grep -r "apple" /path/to/dir`     | Searches `apple` in all files under the given path.  |
| `-w`              | Match **whole words** only.                                              | `grep -w "apple" file.txt`         | Matches `apple`, but not `apples` or `pineapple`.    |
| `-x`              | Match **entire lines** only.                                             | `grep -x "apple" file.txt`         | Matches lines that are exactly `apple`.              |
| `-A [num]`        | Show **N lines after** each match.                                       | `grep -A 2 "apple" file.txt`       | Displays 2 lines after each match.                   |
| `-B [num]`        | Show **N lines before** each match.                                      | `grep -B 2 "apple" file.txt`       | Displays 2 lines before each match.                  |
| `-C [num]`        | Show **N lines before and after** each match (context).                  | `grep -C 2 "apple" file.txt`       | Displays 2 lines before and after each match.        |
| `--color`         | **Highlight matches** in color (if supported by the terminal).           | `grep --color "apple" file.txt`    | Displays matches with colored highlights.            |
| `--exclude`       | Exclude files matching a specific pattern from search.                   | `grep --exclude="*.log" "apple" *` | Excludes `.log` files from the search.               |
| `--include`       | Search only in files matching a specific pattern.                        | `grep --include="*.txt" "apple"`   | Searches only in `.txt` files.                       |
| `--line-buffered` | Use **line buffering** for the output (useful in streaming large files). | `grep --line-buffered "apple"`     | Outputs each match as it is found.                   |
| `-e`              | Specify multiple **patterns** to match.                                  | `grep -e "apple" -e "banana"`      | Matches lines containing either `apple` or `banana`. |
| `-f`              | Read patterns from a **file**, one pattern per line.                     | `grep -f patterns.txt file.txt`    | Matches lines based on patterns from `patterns.txt`. |

---

**_grep is a utitliy used to seach the text with in files or files that matchs regax customized patterns._**

To list name of all files in directory contains target text pattern==>
grep -l(only filenames that contains atleast one given text pattern) "test Regax Pattern" \*.txt(in all files ends with txt);\*\*

**mv \*test\* $(mkdir tests) ==> to move all test file to test file afte it get created**

**-d skip to skip is Directory error message in search output**

`jot`**-->command** **|genreate numbers in range|**

# allias

# .zshrc file

# $? -> exit code of previous process

# zsh shell

# zsh has environment variable not global variable

# proces , strams -> std input, output, error streams

# $sakib here $ is used to access varible sakib in global scope of shell script

# a=2 creating variable.

# $PATH

# how a process get lauch in terminal by shell;

# $PS1 holds shell scripit for primary prompt command on shell and can be modified. it defines the appreace of primary prompt command.

# shell scripting means programing or coding or scripting for shell to customize shell or add new feature to it.

# same as web scripting means writing sctript or code for webapplication to create feature of web application

# cd -

# exit

# escape sequeance or sequeance characters are chars with special meaning that shell doesn't read as normal text or literal, read special beacause of specail functionality they offers

# but to make shell read them as normal character or literal we do someting called escaping, to escape escape character in shell % is used.

# %% here first % is escaping {means telling shell to read it as literal} second %

# PROMPT_COMMAND holds command that executes just before PS1 is displayed.

# Oh My Zsh => Oh My Zsh is essentially a customized version of the .zshrc file that is created and maintained by the community to enhance the Zsh shell experience.(not installd by default) :-

## sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# What Does Oh My Zsh Add to .zshrc?

# -->themes, plugins, ease of use, customizability

| Escape Sequence | Description                                     |
| --------------- | ----------------------------------------------- |
| `%n`            | Username                                        |
| `%m`            | Hostname (up to the first `.`)                  |
| `%M`            | Full hostname                                   |
| `%~`            | Current working directory, with `~` for `$HOME` |
| `%1~`           | Basename of the current directory               |
| `%d` or `%/`    | Full working directory                          |
| `%t`            | Current time in 12-hour HH:MM format            |
| `%T`            | Current time in 24-hour HH:MM format            |
| `%D{...}`       | Custom date/time format (e.g., `%D{%a %b %d}`)  |
| `%#`            | `#` if root, `%` otherwise                      |
| `%%`            | A literal `%` character                         |

| Step Number | Step Name           | Description                                                                                                              |
| ----------- | ------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| 1           | User Input          | The user types `ls` and presses Enter.                                                                                   |
| 2           | Tokenization        | The shell parses the input into tokens (command: `ls`, arguments: none).                                                 |
| 3           | Path Resolution     | The shell searches for the `ls` executable in directories listed in the PATH environment variable.                       |
| 4           | Forking             | The shell creates a child process using `fork()` to execute the command.                                                 |
| 5           | Program Execution   | The child process replaces its image with the `ls` program using `exec()`.                                               |
| 6           | Output Handling     | The `ls` program executes and lists the contents of the current directory, sending output to standard output (terminal). |
| 7           | Process Termination | Once the `ls` command completes, the child process terminates.                                                           |
| 8           | Prompt Display      | The shell displays a prompt again, indicating that it is ready for the next command.                                     |

# Steps for Running the ls Command:

User Input: The user types ls and presses Enter.

- Tokenization: The shell breaks the input into tokens to identify the command (ls) and any arguments.

- Command Type Check:

  - Internal Command Check: The shell first checks if the command is a built-in (internal) command, such as cd, echo, or exit. If ls were an internal command, it would execute directly without further steps.
  - External Command Check: If the command is not internal, the shell determines that it is external and proceeds to locate the program.

- Path Resolution: The shell searches for the ls executable in directories listed in the PATH environment variable.

- Forking: The shell creates a child process to handle the external command.

- Program Execution: The child process executes the ls program using the exec() system call.

- Output Handling: The ls program runs and sends its output to standard output (the terminal).

- Process Termination: The child process terminates after ls finishes execution, and the shell resumes control.

- Prompt Display: The shell displays the prompt, ready for the next command.

# points to note

- Internal commands (also known as built-in commands) are part of the shell program itself and do not exist as separate files in the filesystem

- Forking :- Forking refers to the process of creating a new child process from an existing parent process in an operating system. The new child process is a duplicate of the parent process, but it runs independently.

- Does shell lauch other process?
  The shell itself does not directly launch the ls program. Instead, it creates a new child process that executes the ls program,how -->
  Shell Creates a Child Process:

  - When a command like ls is executed, the shell uses the fork() system call to create a child process.

  - This child process is initially a copy of the parent shell process (i.e., it starts as a duplicate of the shell).

  - Child Process Executes the Command:

    - In the child process, the shell uses the exec() family of system calls (e.g., execvp()) to replace the shell's code in memory with the executable code of the ls program.
    - After this step, the child process is no longer a shell—it becomes the ls program.

  - Parent Shell Waits (Optional):

    - The parent shell can wait for the child process to complete execution using the wait() system call (if the command is run in the foreground).//measns parent denpends on the ouput of child to process furter

  - If the command is run in the background (e.g., with &), the parent shell does not wait.//that means output of those may or may not be giving someting to parent perocess but parent doesn't depend on the out of them.

- Child Process Terminates:

  - After the ls program completes its task, the child process terminates, and its resources are released.

- Parent Shell Resumes:

The parent shell regains control and displays a prompt for the next command.

**summary**

The parent shell creates a child process.
The child process is replaced by the executable file (e.g., ls) using exec().
The parent shell optionally waits for the child process to finish.

|About Alias creation ,updation and flow of execution [Open alias.md](alias.md)|
