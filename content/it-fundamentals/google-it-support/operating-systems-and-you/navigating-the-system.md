---
title: Navigating the System
date: 2022-10-07 13:42:00 +0500
weight: 1
collapsibleMenu: true
alwaysOpen: false
LastModifierDisplayName: AbuTurab
LastModifierEmail: cyberfrontofficial@proton.me
---

## **Basic Commands**

In this, we'll learn about:
- **Windows**
  + GUI (Graphical User Interface)
  + CLI (Command Line Interface)
- **Linux**
  + Command
  + Shell
  > The CLI interpreter on Linux is called a shell, and the language that we'll use to interact with this shell is called **Bash**.

### List Directories in a GUI

- On Windows, filesystems are assigned to drive letters, which look like **C:, or D:, or X:**.
- The parent/root directory of **C:** would be written **C:\**, and the root directory of **X:** would be written **X:\**.
- Subdirectories are separated by **\**.

### Windows List Directories in CLI

- To list contents of **C** drive
  
  ```console
  ls C:\
  ```

- To get help for specific command
  
  ```console
  Get-Help <command name>
  ```
  
  + In case of, `ls` command,
  
  ```console
  Get-Help ls
  ```
  
  + To get more detailed help
  
  ```console
  Get-Help ls-full
  ```
- To see hidden files in a directory
  
  ```console
  ls -Force C:\
  ```

### **Linux: List Directories**

- To list the contents of root directory
  
  ```console
  ls /
  ```
  
  + **/bin**: essential binaries for program
  + **/etc**: system configuration file
  + **/home**: Where user files and configs live
  + **/proc**: Contain information of currently running processes
  + **/usr**: Meant for user installed software
  + **/var**: Stores system logs and anything that constantly changing
- `ls` command has very useful flags too.
- To see available flags for `ls`
  
  ```console
  ls --help
  ```
  
- `man` shows the manual pages.
  
  ```console
  man <command>
  ```
  
- To see hidden files, and long listing
  
  ```console
  ls -al
  ```
  
- You can hide a file by prepending a `.` in the start of the filename.

#### Flags
  
  Similar to Windows command parameters, a flag is a way to specify additional options for a command.

### **Windows: Changing Directories in a GUI**

#### Absolute path
  
  An absolute path is one that starts from the main directory.

#### Relative path
  
A Relative path is the path from your current directory.

### Windows: Changing Directories in the CLI

- To know where you are in the folder
  
  ```console
  pwd
  ```
  
- To change the directory you're in
  
  ```console
  cd <path\to\the\directory>
  ```
  
- To go one level up
  
  ```console
  cd ..
  ```
  
- Get to the $HOME directory
  
  ```console
  cd ~
  ```
  
### Windows: Making Directories in the & CLI

- To make a new directory
  
  ```console
  mkdir <directory name>
  ```

- To make a directory with spaces in its name
  
  ```console
  mkdir 'directory name'
  mkdir directory` name
  ```
  
### Linux: Making Directories in Bash

- To make a directory with spaces in its name
  
  ```console
  mkdir directory\ name
  mkdir 'directory name'
  ```

### Windows: Command History

- To see the history of previous commands
  
  ```console
  history
  ```

- To reverse-search through history, shortcut is `<ctrl+r>`
- To clean PowerShell palette
  
  ```console
  clear
  ```

### **Windows: Copying Files & Directories**

- To copy a file

  ```console
  cp <Path\to\the\file\to\be\copied> <Path\to\the\directory\of\copying> 
  ```

  - To copy multiple file at once, **Wildcard** is used

	  ```console
	  cp *.<common pattern> <path\to\where\copied>
	  ```

- To copy a directory and its content
  
  ```console
  cp <directory name> <Path\to\where\copied> -Recurse -Verbose
  ```

#### Wildcard
  
A character that's used to help select files based on a certain pattern.

### Linux: Copying Files & Directories

- To copy a directory

  ```console
  cp <Directory/to/be/copied> <Path/where/to/be/copied>
  ```

## **File and Text Manipulation**

### Windows: Display File Contents

- To view the file contents
  
  ```console
  cat <File Name>
  ```

- To view the file contents, one page at a time
  
  ```console
  more <File Name>
  ```

- To see only part of the file contents
  
  ```console
  cat <File Name> -Head <Number of Lines>
  ```

- To see only part of the file contents from the tail
  
  ```console
  cat <File Name> -Tail <Number of Lines>
  ```

### Linux: Display File Contents

- To see file's contents, interactively
  
  ```console
  less <File Name>
  ```

- `more` has been abandoned in favor of more useful `less` command on Linux.
- To see only part of a file's contents, `head` is used, which by default only shows first 10 lines
  
  ```console
  head <File Name>
  ```

- To see only part of file's contents, `tail` is used, which by default only shows last 10 lines
  
  ```console
  tail <File Name>
  ```

### Windows: Modifying Text Files

- To modify file's contents from a CLI
  
  ```console
  start notepad++ <File Name>
  ```

### Windows PowerShell

- PowerShell is a powerful and complex command line language.
- To list directories, the real PowerShell command is can be found by:
  
  ```console
  Get-Alias ls
  ```

so, to list directories
  
  ```console
  Get-ChildItem <path\to\directory>
  ```

- Some old but not powerful as PowerShell, cmd.exe commands are
  
  ![cmd.exe](/notes/google-it-support/Navigating%20the%20System.png)
  
### Windows: Searching within Files

- In GUI, **Indexing Options** applications are used.
- In command-line, search is done as:
  
  ```console
  Select-String <Search String> <path\to\the\file>
  ```

- To search in multiple files at once
  
  ```console
  Select-String <Search String> *.<file extension name>
  ```

### Windows: Searching within Directories

- `-Filter` parameter is used with `ls` so search for particular files in a directory.
  + The `-Filter` parameter will filter the results for file names that match a pattern.
  
  ```console
  ls <path\to\the\file> -Recurse -Filter *.exe
  ```

  + The **asterisk** means match anything, and the **.exe** is the file extension for executable files in Windows.

### Linux: Searching within Files

- To search in files
  
  ```console
  grep <Search String> <path/to/the/file>
  ```

- To search through multiple files at once
  
  ```console
  grep <Search String> *.txt
  ```

### Windows: Input, Output, and the Pipeline
  
  ```console
  echo hello_word > hello.py
  ```

- The **echo** is an alias for PowerShell command `Write-Output`.
- Every Windows process and every PowerShell command can take input and can produce output. To do this, we use something called **I/O streams** or **input output streams**.
- I/O streams are
  + stdin
  + stdout
  + stderr
- The symbol **>** is something we call a **Redirector operator** that let us change where we want our **stdout** to go.
- The symbol **>>** is used to not create a new file, just append the `stdout`
  
  ```console
  echo 'Hello Planet' >> hello.py
  ```
  
- `|` Pipe operator is used to redirect the stdout of one command to stdin of another command.
  
  ```console
  cat hello.py | Select-String planet
  ```

- To put new stdout to a new file.
  
  ```console
  cat hello.py | Select-String pla > planet.txt
  ```

- If we don't want to see error in CLI, to get them in a file
  
  ```console
  rm secure_file 2> error.txt
  ```
 
  + **All the output streams are numbered, 1 is for stdout and 2 for stderr**
- If we don't care about error messages and don't want to save them in a file, we can redirect them to a null variable (a black hole for stderr)
  
  ```console
  rm secure_file 2> $null
  ```

### Linux: Input, Output, and the Pipeline

- On Linux, **stdin** operator can be used via symbol **<**.
  
  ```console
  cat < SomeFile.py
  ```
  
  + Here we are using **<** operator for file input instead of keyboard input.
- To redirect error message to a file
  
  ```console
  ls /dir/fake_dir 2> error_output.txt
  ```

- To filter out error message completely without saving
  
  ```console
  ls /dir/fake_dir 2> /dev/null
  ```

### **Windows and Linux Advanced Navigation**
- For more advance navigation, **regex** is used.

### Regular expression (Regex)

Used to help you do advance pattern-based selections.
