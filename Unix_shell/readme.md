
# Shell Basics and Commands: Concise Notes

#### 1. **Introducing the Shell**
- **Shell**: CLI program for running commands and automating tasks. Bash is the most common shell.
- **Advantages**: Automates repetitive tasks, improves efficiency, supports pipelines, and is essential for remote computing.
- **Prompt**: `$` indicates readiness for input. Do not type it when executing commands.
- **First Command**: `ls` lists directory contents.


#### 2. **Navigating Files and Directories**
- **Commands**:
  - `pwd`: Prints current directory.
  - `ls`: Lists directory contents.
  - `cd [path]`: Changes the current directory.
- **Paths**:
  - Absolute: `/Users/nelle/Desktop`.
  - Relative: `Desktop/shell-lesson-data`.
- **Shortcuts**:
  - `~`: Home directory.
  - `..`: Parent directory.
  - `-`: Previous directory.
- **Options**:
  - `ls -F`: Classify output with `/` (directory), `*` (executable).
  - `ls -a`: Show hidden files (`.` and `..`).


#### 3. **Working with Files and Directories**
- **File/Directory Management**:
  - `mkdir [path]`: Create a directory.
  - `touch [file]`: Create an empty file.
  - `mv [source] [destination]`: Move or rename.
  - `cp [source] [destination]`: Copy files.
  - `rm [path]`: Remove files.
  - `rm -r [path]`: Remove directories recursively.
- **Wildcards**:
  - `*`: Matches zero or more characters (`*.txt` for all `.txt` files).
  - `?`: Matches a single character.

#### 4. **Pipes and Filters**
- **Redirection**:
  - `>`: Redirect output to a file, overwriting it.
  - `>>`: Append output to a file.
  - `<`: Use a file as input.
- **Chaining Commands**:
  - `|`: Pipe output of one command as input to another.
  - Example: `wc -l *.txt | sort -n | head -n 1`.
- **Commands**:
  - `cat [file]`: Display file contents.
  - `sort`: Sort file contents.
    - `sort -n`: Numeric sort.
  - `head -n [num]`: Show first `n` lines.
  - `tail -n [num]`: Show last `n` lines.

#### 5. **Key Points**
- **Efficiency**: Shell is ideal for repetitive and large-scale tasks.
- **Files**:
  - Organized hierarchically in directories.
  - Extensions (e.g., `.txt`, `.png`) are conventions, not mandatory.
- **Safety**: Deleting (`rm`) is permanent; use `-i` for confirmation.



### Short Notes: Unix Shell Commands with Examples and Explanations

---

#### **Redirection (`>`, `>>`)**
- **`>`**: Overwrites the content of a file with the command output.
  ```bash
  echo "Hello World" > file.txt  # file.txt contains "Hello World"
  ```
- **`>>`**: Appends the command output to the file without overwriting.
  ```bash
  echo "Welcome" >> file.txt  # file.txt now adds "Welcome" to the previous content.
  ```
- **Caution**: Redirecting output to the same file being read can corrupt data.
  ```bash
  sort -n lengths.txt > lengths.txt  # This can delete the content of lengths.txt.
  ```

---

#### **Head and Tail Commands**
- **`head`**: Displays the first N lines of a file.
  ```bash
  head -n 3 animals.csv  # Shows the first 3 lines of animals.csv
  ```
- **`tail`**: Displays the last N lines of a file.
  ```bash
  tail -n 2 animals.csv  # Shows the last 2 lines of animals.csv
  ```
- **Combining `head` and `tail`**:
  ```bash
  head -n 5 animals.csv | tail -n 3  # Shows lines 3-5 of animals.csv
  ```

---

#### **Pipes (`|`)**
- Pipes (`|`) allow the output of one command to be used as input to another.
  ```bash
  sort -n lengths.txt | head -n 1  # Find the smallest value in lengths.txt
  ```

---

#### **Combining Commands**
- Find the smallest file by line count:
  ```bash
  wc -l *.pdb | sort -n | head -n 1
  ```
- Find the top 3 smallest files:
  ```bash
  wc -l *.pdb | sort -n | head -n 3
  ```

---

#### **Filters and Unix Philosophy**
- **Filters** like `wc`, `sort`, and `head` transform data in a pipeline.
- Example:
  ```bash
  wc -l *.txt | sort -n | head -n 1
  ```
  This command:
  1. Counts lines in `.txt` files (`wc -l`).
  2. Sorts them numerically (`sort -n`).
  3. Selects the smallest file (`head -n 1`).

---

#### **Practical Example: Processing a CSV File**
Input (`animals.csv`):
```csv
2012-11-05,deer,5
2012-11-05,rabbit,22
2012-11-05,raccoon,7
2012-11-06,rabbit,19
2012-11-06,deer,2
2012-11-06,fox,4
2012-11-07,rabbit,16
2012-11-07,bear,1
```
Pipeline:
```bash
cat animals.csv | head -n 5 | tail -n 3 | sort -r > final.txt
```
**Explanation**:
1. `cat animals.csv`: Reads the file.
2. `head -n 5`: Takes the first 5 lines.
3. `tail -n 3`: Extracts the last 3 of these lines.
4. `sort -r`: Sorts these lines in reverse order.
5. `> final.txt`: Saves the result to `final.txt`.

---

#### **Dynamic File Processing**
- Extract specific fields with `cut`:
  ```bash
  cut -d, -f2 animals.csv | sort | uniq  # Unique animals
  ```


#### **Pipe Construction**
Build complex commands step-by-step:
1. Start simple:
   ```bash
   cat animals.csv
   ```
2. Add filtering:
   ```bash
   head -n 5
   ```
3. Further process:
   ```bash
   tail -n 3 | sort -r
   ```

---

#### **Command Options**
- **`wc`**: Counts lines, words, and characters.
  ```bash
  wc -l file.txt  # Count lines
  ```
- **`sort`**: Sorts text.
  - `-n`: Numerical sort.
  - `-r`: Reverse order.
- **`grep`**: Searches for patterns in text.
  ```bash
  grep "rabbit" animals.csv  # Find lines containing "rabbit"
  ```
- **`uniq`**: Removes duplicate lines (requires sorted input).
  ```bash
  sort file.txt | uniq
  ```

---

#### **Advantages of Unix Tools**
- **Modular**: Each tool does one job well.
- **Flexible**: Combine commands for complex tasks.
- **Reusable**: Easily script repetitive tasks.

#### **Disadvantages**
- **Steep Learning Curve**: Requires knowledge of syntax and tools.
- **Error-Prone**: Small mistakes (e.g., missing quotes) can lead to data loss.

---

#### **Visualization**
1. **Pipeline Flow**:
   Input File → Command1 → Command2 → Output File.

   Example:
   ```bash
   wc -l animals.csv | sort -n | head -n 1
   ```

2. **Redirection**:
   Command Output → File → Next Command.

   Example:
   ```bash
   echo "Test" > file.txt | wc -l
   ```

### Short Notes on Shell Commands and Navigation

---

#### **Definition and Introduction**
- A **shell** is a command-line interface that interprets and executes user commands.
- Example Shells: Bash, Zsh, Fish.
- Default Prompt: `$`, indicating readiness for a command.

#### **Shell Prompt**
- The **prompt** might include user and hostname:
  ```bash
  nelle@localhost $
  ```
- Input commands after `$`, and press **Enter** to execute.

#### **Basic Commands**
1. **`ls`** - Lists contents of the current directory.
   ```bash
   $ ls
   ```
   Output:
   ```
   Desktop     Documents   Downloads
   ```
   - **Options**:
     - `ls -F`: Classify contents (`/` for directories, `*` for executables).
     - `ls -a`: Show hidden files.

2. **`pwd`** - Prints the current working directory.
   ```bash
   $ pwd
   ```
   Output:
   ```
   /Users/nelle
   ```

3. **`clear`** - Clears the terminal display.
   ```bash
   $ clear
   ```

---

#### **Help and Documentation**
1. **`--help`**: Provides command-specific options and usage.
   ```bash
   $ ls --help
   ```
2. **`man`**: Opens the manual for a command.
   ```bash
   $ man ls
   ```

3. **`help`**: For built-in commands like `cd`.
   ```bash
   $ help cd
   ```

---

#### **Navigating Files and Directories**
1. **File System Hierarchy**:
   - Organized like an inverted tree:
     ```
     /
     ├── Users/
     │   ├── nelle/
     │   ├── larry/
     ├── tmp/
     └── data/
     ```
   - `/` is the root directory.
   - **Home Directory**: Default starting location, e.g., `/Users/nelle`.

2. **`cd`** - Change directory.
   ```bash
   $ cd Desktop
   ```
   Navigate to a subdirectory.

3. **Absolute Path**: Complete path from the root directory.
   ```bash
   /Users/nelle/Documents
   ```

4. **Relative Path**: Path relative to the current directory.
   ```bash
   Documents
   ```



#### **Key Features**
- **Tab Completion**: Auto-completes commands or file names by pressing `Tab`.
- **Short vs. Long Options**:
  - Short: Single dash and a letter (`-a`).
  - Long: Double dash and a word (`--all`).



#### **Example Scenario: Automating Tasks**
- **Nelle’s Problem**: Process 1520 files with `goostats.sh` (a hypothetical program).
- **Solution**: Use shell loops to automate tasks.
  ```bash
  $ for file in *.txt
  > do
  >   bash goostats.sh $file results-$file
  > done
  ```
  **Explanation**:
  - `for file in *.txt`: Iterate over `.txt` files.
  - `bash goostats.sh $file results-$file`: Process each file and save results.



#### **Advantages of Shell**
- **Efficiency**: Automates repetitive tasks.
- **Scalability**: Handles multiple files easily.
- **Versatility**: Works across different operating systems.

#### **Challenges**
- **Steep Learning Curve**: Requires familiarity with syntax and commands.
- **Errors**: Mistakes in paths or commands can lead to unexpected behavior.



#### **Visualization**
1. **File System**:
   ```
   /
   ├── Users/
   │   ├── nelle/
   │       ├── Documents/
   │       ├── Desktop/
   │       └── Downloads/
   ```
2. **Command Execution Flow**:
   ```
   Prompt > Command > Processing > Output
   ```

### Detailed Notes on Shell Basics and Navigation

---

### **Short Option vs. Long Option**
- **Short Options**: Quick to type for interactive shell commands.
  - Example: `ls -l` (lists in long format).
- **Long Options**: Improve script readability.
  - Example: `ls --long` (equivalent to `ls -l`).



### **Command Errors**
- Invalid options result in an error:
  ```bash
  $ ls -j
  ls: invalid option -- 'j'
  Try 'ls --help' for more information.
  ```



### **Command Documentation**
1. **`--help`**: Lists supported options and their usage.
   ```bash
   $ ls --help
   ```
2. **`man` Command**: Displays a detailed manual.
   ```bash
   $ man ls
   ```
   - Navigation:
     - `↑` / `↓`: Move line by line.
     - `Spacebar` / `b`: Scroll a page down or up.
     - `/pattern`: Search for a term.
     - `n` / `Shift+n`: Jump to the next or previous match.
     - `q`: Exit.

3. **Web Manual Pages**:
   - Search for `Unix man page <command>` online for additional resources.

---

### **Exploring `ls` Options**
1. **`ls -l`**: Lists files with details like size, permissions, and modification time.
2. **`ls -lh`**: Formats file sizes in human-readable units (e.g., KB, MB).
3. **`ls -t`**: Sorts by modification time.
4. **`ls -r`**: Reverses the order of the listing.
5. **Combined Options**:
   ```bash
   $ ls -ltr
   ```
   - Lists files in reverse chronological order.



### **Navigating Directories**

1. **Current Directory**
   - View current location with:
     ```bash
     $ pwd
     ```
   - Example output:
     ```
     /Users/nelle
     ```

2. **Viewing Directory Contents**
   - **List Current Directory**:
     ```bash
     $ ls
     ```
   - **List Subdirectory**:
     ```bash
     $ ls -F Desktop
     ```

3. **Changing Directories**
   - **Move to a Subdirectory**:
     ```bash
     $ cd Desktop/shell-lesson-data
     ```
   - **Go Up One Level**:
     ```bash
     $ cd ..
     ```

4. **Hidden Files**
   - Use `-a` to display hidden files/directories (`.`, `..`):
     ```bash
     $ ls -Fa
     ```
     Example output:
     ```
     ./  ../  exercise-data/  north-pacific-gyre/
     ```


### **Directory Navigation Example**

#### Goal:
Move from home directory to `exercise-data`.

1. **Step-by-Step Commands**:
   ```bash
   $ cd Desktop
   $ cd shell-lesson-data
   $ cd exercise-data
   ```

2. **Verify Location**:
   ```bash
   $ pwd
   ```
   Output:
   ```
   /Users/nelle/Desktop/shell-lesson-data/exercise-data
   ```

---

### **Key Special Directories**
- **`.`**: Current directory.
- **`..`**: Parent directory.
- **`~`**: Home directory.

---

### **Combining Options**
- Options can be grouped:
  ```bash
  $ ls -F -a
  ```
  Equivalent to:
  ```bash
  $ ls -Fa
  ```

### **Practical Use Case**
#### Task:
List the contents of `Desktop` in long format, including hidden files, and sort by modification time.

1. **Command**:
   ```bash
   $ ls -altr Desktop
   ```
2. **Explanation**:
   - `-a`: Show all files.
   - `-l`: Long format.
   - `-t`: Sort by time.
   - `-r`: Reverse the order.

3. **Output Example**:
   ```
   -rw-r--r--  1 nelle  staff   1048 Nov  5 10:30 notes.txt
   drwxr-xr-x  3 nelle  staff    512 Nov  7 15:42 scripts/
   drwxr-xr-x  4 nelle  staff    512 Nov  7 18:00 projects/
   ```

### **Advantages of Directory Organization**
1. **Efficiency**: Quickly locate files using meaningful hierarchy.
2. **Scalability**: Manage large file systems effectively.
3. **Automation**: Combine commands in scripts for repetitive tasks.


### Concise Notes on Shell Commands and Operations



#### **Getting Help**
- `ls --help`: Displays help for the `ls` command.
- `man ls`: Opens manual for `ls` command.
  - Navigation: `↑`, `↓`, `Spacebar`, `b` for scrolling; `/search` to find terms; `q` to exit.



#### **Exploring Files and Directories**
1. **Commands**:
   - `pwd`: Print current directory.
   - `ls [options] [path]`: List contents of a directory.
     - Options: `-l` (long format), `-h` (human-readable sizes), `-t` (sort by time), `-r` (reverse order).
   - `cd [path]`: Change directory.
     - `cd ..`: Move up one level.
     - `cd -`: Return to previous directory.
     - `cd ~/`: Go to the home directory.

2. **Paths**:
   - **Relative**: From the current location (e.g., `cd Desktop`).
   - **Absolute**: Full path from root (e.g., `/Users/nelle/Desktop`).

3. **Special Directories**:
   - `.`: Current directory.
   - `..`: Parent directory.
   - `~`: Home directory.



#### **Managing Files and Directories**
1. **Creating**:
   - `mkdir [path]`: Create a directory.
   - `mkdir -p [nested/directories]`: Create nested directories.

2. **Moving and Renaming**:
   - `mv [source] [destination]`: Move or rename files.
   - `mv -i`: Prompt before overwriting.

3. **Copying**:
   - `cp [source] [destination]`: Copy files.
   - `cp -r [source_dir] [destination_dir]`: Copy directories recursively.

4. **Deleting**:
   - `rm [file]`: Remove files.
   - `rm -r [dir]`: Remove directories.
   - `rm -i`: Interactive deletion for safety.



#### **File Content Manipulation**
1. **View and Create Files**:
   - `cat [file]`: Print file content.
   - `nano [file]`: Open text editor to create or edit files.
   - `touch [file]`: Create an empty file.

2. **Redirecting Output**:
   - `>`: Redirect output to a file (overwrites).
   - `>>`: Append output to a file.



#### **Wildcards**
- `*`: Matches zero or more characters (`*.txt` for all `.txt` files).
- `?`: Matches one character (`?ethane.pdb` matches `methane.pdb`).



#### **Combining Commands**
1. **Piping**:
   - `|`: Pass output of one command as input to another.
   - Example: `wc -l *.pdb | sort -n | head -n 1`.

2. **Chaining Commands**:
   - `;`: Run commands sequentially.
   - `&&`: Run the next command only if the first succeeds.


#### **Example Commands**
1. **List the smallest file by lines**:
   ```bash
   wc -l *.pdb | sort -n | head -n 1
   ```

2. **Move specific files to a folder**:
   ```bash
   mv sucrose.dat maltose.dat raw/
   ```

3. **Copy all dataset files to a backup**:
   ```bash
   cp *dataset* backup/datasets
   ```

4. **Sort a file numerically**:
   ```bash
   sort -n file.txt
   ```

5. **Create a directory structure**:
   ```bash
   mkdir -p 2024-11-23/data/raw 2024-11-23/data/processed
   ```

#### **Key Points**
- Shortcuts:
  - `Ctrl+C`: Stop current command.
  - `Tab`: Auto-complete paths/commands.
- Use pipes and redirects for efficiency.
- Be cautious with `rm` and `>` to prevent data loss.


### **Additional Details to Include**

#### **1. Command Syntax and Terminology**
- **General Command Syntax**:
  ```bash
  command [options] [arguments]
  ```
  - **Command**: The operation to perform (e.g., `ls`).
  - **Options**: Modify command behavior (`-l`, `-h`).
  - **Arguments**: Specify the target of the command (e.g., `file.txt`).

#### **2. Directory Hierarchy Explanation**
- Filesystem hierarchy is organized like an inverted tree:
  ```
  /
  ├── Users/
  │   ├── nelle/
  │       ├── Desktop/
  │       ├── Documents/
  │       └── Downloads/
  ```
  - `/`: Root directory.
  - Hidden files and directories begin with `.` (e.g., `.bash_profile`).



#### **3. More on Wildcards**
- Wildcards allow flexible file selection:
  - `*.txt`: Matches all `.txt` files.
  - `a*`: Matches files starting with `a`.
  - `?`: Matches exactly one character (e.g., `?ane.pdb` matches `bane.pdb` and `cane.pdb`).


#### **4. `less` Command**
- Alternative to `cat` for viewing files page by page:
  ```bash
  less file.txt
  ```
  - **Navigation**:
    - `Space`: Scroll forward.
    - `b`: Scroll backward.
    - `/pattern`: Search for a term.
    - `q`: Quit.


#### **5. Explanation of Key Shell Tools**
- **`grep`**:
  - Searches for patterns in files:
    ```bash
    grep "deer" animals.csv
    ```
    Output: Lines containing "deer".
  - Options:
    - `-i`: Case-insensitive search.
    - `-v`: Invert match (lines NOT containing the pattern).

- **`uniq`**:
  - Removes duplicate lines (requires sorted input):
    ```bash
    sort file.txt | uniq
    ```

- **`cut`**:
  - Extracts specific fields from text:
    ```bash
    cut -d, -f2 animals.csv
    ```
    Output: Second column (animal names) from `animals.csv`.


#### **6. More Practical Examples**
- **Sorting Files in Reverse Chronological Order**:
  ```bash
  ls -lt | sort -r
  ```

- **Copying Files Based on Date**:
  ```bash
  cp 2015-11-*-*.txt backup/
  ```
  - Copies all `.txt` files from November 2015 to the `backup` directory.

- **Iterative Commands (Loops)**:
  - Process multiple files using a loop:
    ```bash
    for file in *.csv
    do
      echo "Processing $file"
      head -n 1 $file
    done
    ```

#### **7. Safety with `rm`**
- Emphasize interactive deletion with `-i`:
  ```bash
  rm -i file.txt
  ```
- Recursive directory removal:
  ```bash
  rm -r folder_name
  ```

#### **8. Advanced Navigation**
- Move multiple levels up:
  ```bash
  cd ../../
  ```
- Combine shortcuts with paths:
  ```bash
  cd ~/Documents/../Desktop
  ```

#### **9. Shell Scripts**
- A shell script is a file containing a sequence of commands:
  ```bash
  #!/bin/bash
  echo "Starting script..."
  wc -l *.txt | sort -n | head -n 1
  echo "Done."
  ```
- Run a script:
  ```bash
  bash script.sh
  ```

#### **10. Unix Philosophy**
- **Pipes and Filters**: Each command does one job well, and you can combine them for complex tasks.
- Example:
  ```bash
  sort file.txt | uniq | wc -l
  ```
