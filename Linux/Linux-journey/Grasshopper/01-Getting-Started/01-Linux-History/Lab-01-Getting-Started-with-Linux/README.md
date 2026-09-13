# 🐧 Getting Started with Linux

> **Cybersecurity / Linux Journey — Lab 01**

This lab is my foundation for understanding Linux from a **cybersecurity perspective**.

The goal is not to memorize commands blindly, but to understand **what happens when a command is typed, how the shell interprets it, how Linux processes it, and how the result is produced.**

---

## 🎯 Learning Objectives

By completing this lab, I learned:

* How the **Terminal, Shell, Commands, Linux Kernel, and Hardware** interact
* How Linux organizes **files, directories, and paths**
* How to navigate the filesystem using `pwd`, `cd`, and `ls`
* How to inspect files and directories
* How Linux **file permissions** are represented
* How to create and read files using `echo`, `>`, `>>`, and `cat`
* How to inspect large files using `head` and `tail`
* How shell special characters affect command behavior
* How to work with dates, calendars, and simple calculations
* How command **options and arguments** work
* Why these fundamentals are important for cybersecurity

---

# 1. 🖥️ Terminal, Shell & Commands

A basic Linux command flow can be understood as:

```text
User
  ↓
Terminal
  ↓
Shell
  ↓
Command / Program
  ↓
Linux OS / Kernel
  ↓
Hardware
```

### Terminal

The **Terminal** is the interface where I interact with Linux by typing commands.

### Shell

The **Shell** is the program that interprets the commands I type.

Examples include:

* Bash
* Zsh
* Fish

### Command / Program

A command or program performs a requested task.

For example:

```bash
date
```

The general process is:

```text
I type: date
      ↓
Terminal receives the input
      ↓
Shell interprets it
      ↓
date program executes
      ↓
Output appears in the terminal
```

### 🔐 Cybersecurity Relevance

Linux security work frequently involves the terminal for:

* Inspecting files
* Checking permissions
* Investigating processes
* Reading logs
* Examining network information
* Running security tools
* Automating repetitive tasks

---

# 2. 💻 Understanding the Linux Prompt

A normal user may see:

```text
user@linux:~$
```

A root shell may look like:

```text
root@kali:~#
```

The prompt indicates that the shell is ready to receive a command.

### Important

Do **not** type the prompt itself.

If you see:

```text
user@linux:~$ pwd
```

You type only:

```bash
pwd
```

### `$` vs `#`

```text
$ → commonly represents a normal user shell
# → commonly represents a root shell
```

> The exact prompt can vary depending on the Linux distribution and shell configuration.

---

# 3. 📁 Files, Directories & Paths

Linux uses the term **directory** instead of folder.

Example:

```text
/home/user/
├── notes.txt
└── projects/
    └── project.txt
```

Here:

```text
notes.txt                  → file
projects/                  → directory
/home/user/projects/       → path
```

A **path** tells Linux where something is located.

### 🔐 Cybersecurity Relevance

Filesystem navigation is fundamental to:

* Security investigations
* CTFs
* Malware analysis
* Log analysis
* Finding configuration files
* Locating suspicious scripts and files

---

# 4. 📍 `pwd` — Where Am I?

`pwd` means:

> **Print Working Directory**

It shows the directory I am currently working in.

```bash
pwd
```

Example output:

```text
/home/user
```

### Mental Model

```text
pwd → Where am I?
```

### 🔐 Cybersecurity Relevance

Knowing the exact working directory helps prevent mistakes before modifying, deleting, or investigating files.

---

# 5. 🚶 `cd` — Change Directory

`cd` means:

> **Change Directory**

It is used to move through the filesystem.

```bash
cd /home/user/projects
```

### Important Forms

Go to the parent directory:

```bash
cd ..
```

Go to the home directory:

```bash
cd ~
```

Return to the previous directory:

```bash
cd -
```

Running `cd` without an argument normally takes the user to their home directory:

```bash
cd
```

### Important

`cd` works with **directories**, not ordinary files.

For example:

```bash
cd notes.txt
```

If `notes.txt` is a file, Linux will return an error because it is not a directory.

### Mental Model

```text
cd → Where do I want to go?
```

---

# 6. 📋 `ls` — What Is Here?

`ls` means:

> **List directory contents**

Basic usage:

```bash
ls
```

### Useful Options

Detailed listing:

```bash
ls -l
```

Show hidden files:

```bash
ls -a
```

Human-readable file sizes:

```bash
ls -lh
```

Detailed listing + hidden files:

```bash
ls -la
```

### `ls -l` Example

```text
-rwxr-xr-- 1 user group 1234 Sep 7 script.sh
```

The first section represents the file type and permissions:

```text
-rwxr-xr--
│
├── -     → file type
├── rwx   → owner permissions
├── r-x   → group permissions
└── r--   → others' permissions
```

Basic permissions:

```text
r → read
w → write
x → execute
```

### 🔐 Cybersecurity Relevance

Permissions are critical for security because they determine who can:

* Read a file
* Modify a file
* Execute a file

---

# 7. 📝 `echo` — Display Text

`echo` displays text or values.

```bash
echo "Hello, Linux"
```

Output:

```text
Hello, Linux
```

Another example:

```bash
echo "I am learning Linux"
```

Quotation marks are useful when text contains spaces or shell-special characters.

### 🔐 Cybersecurity Relevance

`echo` is useful for:

* Testing shell behavior
* Creating simple files
* Testing variables
* Building basic shell scripts

---

# 8. ➡️ Output Redirection — `>` and `>>`

Normally:

```bash
echo "Hello"
```

prints the output to the terminal.

With redirection:

```bash
echo "Hello" > greeting.txt
```

the output is written to a file.

### `>` — Overwrite

```bash
echo "First" > test.txt
```

`test.txt` contains:

```text
First
```

Then:

```bash
echo "Second" > test.txt
```

The previous content is replaced:

```text
Second
```

### `>>` — Append

```bash
echo "Third" >> test.txt
```

Now:

```text
Second
Third
```

### Remember

```text
>   → create/overwrite
>>  → append
```

### 🔐 Cybersecurity Relevance

Redirection is important when:

* Saving command output
* Collecting investigation results
* Creating logs
* Building shell scripts
* Automating security tasks

---

# 9. 📖 `cat` — Read File Contents

`cat` displays the contents of text files.

```bash
cat greeting.txt
```

### Show Line Numbers

```bash
cat -n file.txt
```

### Combine Files

```bash
cat file1.txt file2.txt file3.txt > combined.txt
```

### Append a File

```bash
cat file2.txt >> existingfile.txt
```

### Combine All `.txt` Files

```bash
cat *.txt > all_text_combined.txt
```

### Combine With Line Numbers

```bash
cat -n file1.txt file2.txt > combined_numbered.txt
```

### ⚠️ Important Redirection Warning

Avoid:

```bash
cat file1.txt file2.txt > file1.txt
```

because the shell opens `file1.txt` for output **before `cat` reads the input**, which can truncate the file and destroy its original contents.

### 🔐 Cybersecurity Relevance

`cat` is frequently useful for quickly inspecting:

* Logs
* Configuration files
* Scripts
* Text files
* Security-related output

---

# 10. 🕐 `date` — Date & Time

`date` displays the system's current date and time.

```bash
date
```

For an ISO-style date:

```bash
date +%F
```

Example:

```text
2026-09-07
```

Save the date:

```bash
date +%F > today.txt
```

Read it:

```bash
cat today.txt
```

### 🔐 Cybersecurity Relevance

Accurate timestamps are important during:

* Log analysis
* Authentication investigations
* Incident response
* Security event correlation

---

# 11. 📅 `cal` — Calendar

`cal` displays a calendar.

```bash
cal
```

Save it to a file:

```bash
cal > calendar.txt
```

Read it:

```bash
cat calendar.txt
```

> Some minimal Linux systems may not include `cal` by default. If `command not found` appears, the utility may simply not be installed.

---

# 12. 🧮 `expr` — Simple Calculations

`expr` can perform basic arithmetic.

```bash
expr 5 + 3
```

Output:

```text
8
```

Examples:

```bash
expr 20 - 7
expr 24 / 6
```

### Multiplication

The `*` character has a special meaning to the shell because it is used for wildcard/globbing.

Therefore:

```bash
expr 6 \* 7
```

Output:

```text
42
```

The backslash:

```text
\
```

escapes the special meaning of `*`.

### Important

Spaces matter:

```bash
expr 5 + 3
```

is not the same as:

```bash
expr 5+3
```

Save the result:

```bash
expr 6 \* 7 > calculation.txt
```

Then:

```bash
cat calculation.txt
```

### 🔐 Cybersecurity Relevance

`expr` itself is not a major cybersecurity tool.

The important lesson is understanding **how the shell interprets special characters**.

---

# 13. 🧩 Command Structure

A common Linux command structure is:

```text
command [options] [arguments]
```

Example:

```bash
figlet -f slant "Linux"
```

Breakdown:

```text
figlet       → command
-f           → option
slant        → option value
"Linux"      → argument
```

### Option vs Argument

**Option**

Changes how a command behaves.

Example:

```bash
ls -l
```

`-l` changes the output format.

**Argument**

Tells the command what to operate on or process.

Example:

```bash
cat file.txt
```

`file.txt` is the argument.

### Mental Model

```text
COMMAND → What should I run?
OPTION  → How should it behave?
ARGUMENT → What should it operate on?
```

Understanding this structure becomes increasingly important as Linux commands become more advanced.

---

# 14. 🎨 `figlet` — ASCII Art

`figlet` converts text into large ASCII-style text.

```bash
figlet "Linux"
```

Example with a font:

```bash
figlet -f slant "Linux"
```

Here:

```text
-f → font option
slant → selected font
```

Save the output:

```bash
figlet "Linux" > art.txt
```

Read it:

```bash
cat art.txt
```

> `figlet` is mainly useful for practice and experimentation rather than cybersecurity itself.

---

# 15. 🔝 `head` — Beginning of a File

`head` displays the beginning of a file.

```bash
head file.txt
```

By default, it normally displays the first **10 lines**.

Show the first 5 lines:

```bash
head -n 5 file.txt
```

### 🔻 `tail` — End of a File

`tail` displays the end of a file.

```bash
tail file.txt
```

Show the last line:

```bash
tail -n 1 file.txt
```

### 🔐 Cybersecurity Relevance

Logs can contain thousands or millions of lines.

Instead of displaying everything:

```bash
head
```

can quickly show the beginning, while:

```bash
tail
```

can quickly show the most recent/end entries.

These become especially useful when combined with tools such as `grep`, `less`, and pipelines.

---

# 16. 🧹 `clear` — Clean the Terminal

`clear` clears the visible terminal screen.

```bash
clear
```

Keyboard shortcut:

```text
Ctrl + L
```

### Important

Clearing the screen does **not** delete files.

```text
clear / Ctrl+L → clean the visible terminal
rm             → remove files/directories
```

> `clear` is mainly a usability command rather than a cybersecurity tool.

---

# 17. 🧠 The Basic Linux Filesystem Workflow

A useful mental model from this lab:

```text
pwd
 ↓
Where am I?

ls
 ↓
What is here?

cd
 ↓
Where do I want to go?

echo
 ↓
Produce text

>
 ↓
Save / overwrite output

>>
 ↓
Append output

cat
 ↓
Read the file
```

This simple workflow forms an important foundation for Linux administration and cybersecurity.

---

# 18. 🔬 Final Practical Exercise

Create a file:

```bash
echo "Terminal ready" > terminal-ready.txt
```

Read it:

```bash
cat terminal-ready.txt
```

Check that it exists:

```bash
ls
```

Check its details:

```bash
ls -l
```

### What happened?

```text
echo
 ↓
Generated text
 ↓
>
Redirected output
 ↓
terminal-ready.txt
 ↓
cat
 ↓
Read the file
 ↓
ls
 ↓
Confirmed the file exists
```

---

# 📚 Command Reference

| #  | Command / Symbol | Purpose                        | Example                   |
| -- | ---------------- | ------------------------------ | ------------------------- |
| 1  | `pwd`            | Show current directory         | `pwd`                     |
| 2  | `cd`             | Change directory               | `cd /home`                |
| 3  | `cd ..`          | Move to parent directory       | `cd ..`                   |
| 4  | `cd ~`           | Go to home directory           | `cd ~`                    |
| 5  | `cd -`           | Return to previous directory   | `cd -`                    |
| 6  | `ls`             | List directory contents        | `ls`                      |
| 7  | `ls -l`          | Detailed listing               | `ls -l`                   |
| 8  | `ls -a`          | Show hidden files              | `ls -a`                   |
| 9  | `ls -lh`         | Human-readable sizes           | `ls -lh`                  |
| 10 | `ls -la`         | Detailed + hidden files        | `ls -la`                  |
| 11 | `echo`           | Display text                   | `echo "Hello"`            |
| 12 | `>`              | Create/overwrite file          | `echo "Hi" > file.txt`    |
| 13 | `>>`             | Append to file                 | `echo "Hi" >> file.txt`   |
| 14 | `cat`            | Display file contents          | `cat file.txt`            |
| 15 | `cat -n`         | Display line numbers           | `cat -n file.txt`         |
| 16 | `date`           | Show date/time                 | `date`                    |
| 17 | `date +%F`       | ISO date format                | `date +%F`                |
| 18 | `cal`            | Display calendar               | `cal`                     |
| 19 | `expr`           | Basic calculations             | `expr 5 + 3`              |
| 20 | `\*`             | Escape multiplication symbol   | `expr 5 \* 3`             |
| 21 | `figlet`         | Display ASCII text             | `figlet "Linux"`          |
| 22 | `figlet -f`      | Select ASCII font              | `figlet -f slant "Linux"` |
| 23 | `head`           | Show beginning of file         | `head file.txt`           |
| 24 | `head -n`        | Show specific number of lines  | `head -n 5 file.txt`      |
| 25 | `tail`           | Show end of file               | `tail file.txt`           |
| 26 | `tail -n`        | Show specific lines from end   | `tail -n 1 file.txt`      |
| 27 | `clear`          | Clear terminal display         | `clear`                   |
| 28 | `Ctrl + L`       | Clear/refresh terminal display | `Ctrl + L`                |

---

# 🔐 Cybersecurity Takeaways

Although these are beginner Linux commands, they establish several concepts that are used throughout cybersecurity:

### Filesystem

```text
pwd → cd → ls
```

Understanding where files are and how to navigate them.

### Permissions

```text
r → read
w → write
x → execute
```

Understanding who can access or execute files.

### File Investigation

```text
cat
head
tail
```

Reading and inspecting files and logs.

### Command Output

```text
>
>>
```

Saving and collecting command results.

### Shell Behavior

```text
\
*
" "
```

Understanding how the shell interprets special characters.

### Command Structure

```text
command
   +
options
   +
arguments
```

This structure becomes essential when working with advanced Linux and cybersecurity tools.

---

# 📸 Lab Evidence

Screenshots from the practical exercises are stored in the `Screenshots/` directory.

Examples include:

* `pwd-command.png`
* `cd-commands.png`
* `ls-commands.png`
* `echo-command.png`
* `Overwrite-Append-Redirection.png`
* `cat-commands.png`
* `date-commands.png`
* `cal-commands.png`
* `expr-command.png`
* `figlet-commands.png`
* `head-commands.png`
* `tail-commands.png`
* `clear-command.png`

These screenshots document the commands being executed and the resulting terminal output.

---

# 🗂️ Lab Structure

```text
Cybersecurity/
└── Linux-journey/
    └── Grasshopper/
        └── 01-Getting-Started/
            ├── 01-Linux-History/
            └── Lab-01-Getting-Started-with-Linux/
                └── Screenshots/
                    ├── pwd-command.png
                    ├── cd-commands.png
                    ├── ls-commands.png
                    ├── echo-command.png
                    ├── cat-commands.png
                    ├── date-commands.png
                    ├── cal-commands.png
                    ├── expr-command.png
                    ├── figlet-commands.png
                    ├── head-commands.png
                    ├── tail-commands.png
                    ├── clear-command.png
                    └── Overwrite-Append-Redirection.png
```

---

# 🚀 What's Next?

This lab establishes the basic Linux foundation required for the next stages of my cybersecurity journey.

Next topics will build toward:

```text
Linux Fundamentals
       ↓
Filesystem & Permissions
       ↓
Processes & Services
       ↓
Networking
       ↓
Shell Scripting
       ↓
Security Tools
       ↓
CTFs / Labs
       ↓
Practical Cybersecurity
```

> **Principle:** Understand the concept first, then practice the command.

---

## 📌 Key Lesson

> **Linux is not about memorizing commands. It is about understanding how the system works and knowing which tool to use for a specific task.**

This lab is my first step toward developing that understanding from a **cybersecurity perspective**.
