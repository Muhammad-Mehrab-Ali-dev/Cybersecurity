# Lab 03 — Create Personalized Terminal Greeting

**Learning Path:** Linux Journey → Grasshopper → Getting Started → Linux History
**Lab:** Create Personalized Terminal Greeting
**Task:** Save the ASCII-Art Banner
**Status:** ✅ Completed

---

## 📌 Overview

This lab demonstrates how to generate an ASCII-art representation of the word **`Welcome`** using the default `figlet` font and save the output to a text file using Linux output redirection.

The exercise provides practical experience with basic Linux command-line operations, filesystem navigation, standard output, file creation, and command verification.

Although this is a beginner-level exercise, the underlying concepts are important for cybersecurity because Linux security work frequently involves working with the terminal, redirecting command output, creating evidence files, processing logs, and automating repetitive tasks.

---

## 🎯 Objective

Create a file named:

```text
welcome-banner.txt
```

inside:

```text
/home/vboxuser/Desktop/labex/pratice
```

The file must:

* Use the **default `figlet` font**
* Contain the ASCII-art rendering of `Welcome`
* Contain no additional text
* Exist in the required directory
* Not be empty

---

## 📋 Requirements

| Requirement       | Expected Result                        |
| ----------------- | -------------------------------------- |
| Working directory | `/home/vboxuser/Desktop/labex/pratice` |
| Output file       | `welcome-banner.txt`                   |
| Command           | `figlet`                               |
| Input             | `Welcome`                              |
| Font              | Default FIGlet font                    |
| Output            | ASCII-art text                         |
| File state        | Exists and is non-empty                |

---

# 🛠️ Implementation

## 1. Navigate to the Required Directory

First, move into the directory specified by the lab.

```bash
cd /home/vboxuser/Desktop/labex/pratice
```

Verify the current working directory:

```bash
pwd
```

Expected output:

```text
/home/vboxuser/Desktop/labex/pratice
```

### Concept

`cd` means **change directory**.

`pwd` means **print working directory**.

These commands are fundamental for safely navigating the Linux filesystem and confirming where commands will operate.

---

## 2. Generate the ASCII-Art

Run:

```bash
figlet Welcome
```

`figlet` converts ordinary text into large ASCII-art characters.

Because the task requires the **default FIGlet font**, no custom font option is specified.

---

## 3. Redirect the Output to a File

Create the required banner file:

```bash
figlet Welcome > welcome-banner.txt
```

This command performs two operations:

1. `figlet Welcome` generates the ASCII-art.
2. `>` redirects the command's standard output into `welcome-banner.txt`.

The resulting file is:

```text
/home/vboxuser/Desktop/labex/pratice/welcome-banner.txt
```

---

# 🔎 Understanding Output Redirection

The `>` operator is one of the fundamental features of the Linux shell.

Normally:

```bash
figlet Welcome
```

sends output to the terminal:

```text
figlet
  │
  │ standard output
  ▼
Terminal
```

With output redirection:

```bash
figlet Welcome > welcome-banner.txt
```

the shell redirects standard output into a file:

```text
figlet
  │
  │ standard output
  ▼
   >
   │
   ▼
welcome-banner.txt
```

### Important behavior

The `>` operator creates the file if it does not already exist.

If the file already exists, `>` normally **overwrites its existing contents**.

This behavior becomes important when working with logs, command output, scripts, and security-analysis results.

---

# ✅ Verification

Creating a file is only part of the task. The result should also be verified.

## Check the File

```bash
ls -l welcome-banner.txt
```

This confirms that the file exists and provides information such as:

* Permissions
* Owner
* Group
* File size
* Modification time
* Filename

---

## Display the Contents

```bash
cat welcome-banner.txt
```

This should display the ASCII-art rendering of:

```text
Welcome
```

The file should contain **only the generated FIGlet output**.

---

## Check the File Is Not Empty

```bash
wc -c welcome-banner.txt
```

`wc -c` counts the number of bytes in the file.

A value greater than `0` confirms that the file contains data.

---

# 🧪 Complete Command Sequence

The complete workflow can be performed as:

```bash
cd /home/vboxuser/Desktop/labex/pratice
pwd
figlet Welcome > welcome-banner.txt
ls -l welcome-banner.txt
cat welcome-banner.txt
wc -c welcome-banner.txt
```

---

# 🧠 Concepts Learned

## `cd`

```bash
cd /path/to/directory
```

Changes the current working directory.

---

## `pwd`

```bash
pwd
```

Displays the absolute path of the current working directory.

---

## `figlet`

```bash
figlet Welcome
```

Generates ASCII-art text from ordinary characters.

---

## `>`

```bash
command > file
```

Redirects standard output to a file.

---

## `ls`

```bash
ls
```

Lists directory contents.

With:

```bash
ls -l
```

it displays detailed file information.

---

## `cat`

```bash
cat file
```

Displays file contents in the terminal.

---

## `wc`

```bash
wc -c file
```

Counts the number of bytes in a file.

---

# 🔐 Cybersecurity Relevance

This exercise is intentionally simple, but several concepts introduced here are directly applicable to cybersecurity.

### 1. Linux Command-Line Proficiency

Cybersecurity professionals commonly work with Linux systems through the command line.

Being comfortable with commands such as:

```bash
cd
pwd
ls
cat
```

provides the foundation for more advanced security tasks.

### 2. Output Redirection

The same redirection technique can be used to save the results of security-related commands:

```bash
some-security-command > results.txt
```

This can be useful when:

* Saving scan results
* Collecting logs
* Recording command output
* Performing investigations
* Creating evidence files
* Automating security workflows

### 3. Verification

Security work requires more than executing commands.

Results must be checked and validated.

This lab reinforces the workflow:

```text
Execute
   ↓
Generate Output
   ↓
Store Output
   ↓
Verify File
   ↓
Inspect Contents
   ↓
Confirm Expected Result
```

That mindset becomes increasingly important as Linux and cybersecurity tasks become more complex.

---

# ⚠️ Common Mistakes

### Mistake 1 — Wrong Working Directory

Running the command before navigating to the required directory can create the file in the wrong location.

**Correct:**

```bash
cd /home/vboxuser/Desktop/labex/pratice
```

---

### Mistake 2 — Using a Custom Font

The task requires the default FIGlet font.

Do not specify a custom font such as:

```bash
figlet -f somefont Welcome
```

Use:

```bash
figlet Welcome > welcome-banner.txt
```

---

### Mistake 3 — Using `echo`

This:

```bash
echo "Welcome" > welcome-banner.txt
```

does not satisfy the task because it produces ordinary text rather than FIGlet ASCII-art.

---

### Mistake 4 — Adding Extra Content

The output file must contain only the FIGlet rendering.

Do not add:

* Explanations
* Comments
* Shell commands
* Additional text
* Manual decorations

---

### Mistake 5 — Not Verifying the Result

Always check the generated file:

```bash
ls -l welcome-banner.txt
cat welcome-banner.txt
```

and confirm that it is not empty:

```bash
wc -c welcome-banner.txt
```

---

# 📸 Evidence

The completed task is documented with a screenshot stored in the repository:

```text
Screenshots/
└── ASCII-Art-Banner.png
```

The screenshot provides visual evidence of the terminal commands and resulting ASCII-art banner.

---

## 🗂️ Repository Structure

```text
Lab-03-Create-Personalized-Terminal-Greeting/
│
├── README.md
│
└── Screenshots/
    └── ASCII-Art-Banner.png
```

---

# 📚 Skills Practiced

### Linux Fundamentals

* [x] Filesystem navigation
* [x] Working-directory management
* [x] Terminal commands
* [x] File creation
* [x] File inspection
* [x] Standard output
* [x] Output redirection
* [x] Basic file verification

### Cybersecurity Foundations

* [x] Linux command-line familiarity
* [x] Understanding command output
* [x] Saving command results
* [x] Verification mindset
* [x] Terminal-based workflow

---

# 📝 Lab Takeaway

The main lesson from this exercise is not simply how to create an ASCII-art banner.

The more important concept is understanding how a Linux command can generate output and how the shell can redirect that output into a file.

The workflow can be summarized as:

```text
Command
   ↓
Standard Output
   ↓
Output Redirection (>)
   ↓
File
   ↓
Verification
```

This same workflow appears repeatedly in Linux administration, scripting, system analysis, and cybersecurity.

---

# 🚀 Learning Progression

This lab is part of my broader **Linux → Cybersecurity** learning journey.

The progression I am following is:

```text
Linux Fundamentals
        ↓
Command Line
        ↓
Filesystem & Permissions
        ↓
Processes & Services
        ↓
Networking
        ↓
Bash Scripting
        ↓
Security Tools
        ↓
System Security
        ↓
Practical Cybersecurity
```

The objective is to build understanding progressively rather than simply memorize commands.

---

# 🔖 Quick Reference

| Task                   | Command                                   |
| ---------------------- | ----------------------------------------- |
| Navigate to lab        | `cd /home/vboxuser/Desktop/labex/pratice` |
| Show current directory | `pwd`                                     |
| Generate ASCII-art     | `figlet Welcome`                          |
| Save output            | `figlet Welcome > welcome-banner.txt`     |
| List file              | `ls -l welcome-banner.txt`                |
| View contents          | `cat welcome-banner.txt`                  |
| Check file size        | `wc -c welcome-banner.txt`                |

---

# 🏁 Completion

**Lab:** Lab 03 — Create Personalized Terminal Greeting
**Task:** Save the ASCII-Art Banner
**Status:** ✅ Completed
**Environment:** Linux Terminal
**Tool:** FIGlet
**Output:** `welcome-banner.txt`
**Font:** Default FIGlet font

---

> **Note**
>
> This repository documents my hands-on progression from Linux fundamentals toward practical cybersecurity skills. Each lab focuses not only on completing the task, but also on understanding the underlying Linux concepts, verifying results, documenting evidence, and connecting the knowledge to real-world cybersecurity workflows.
# Lab 03 — Create Personalized Terminal Greeting

This folder contains the practical work completed during **Lab 03: Create Personalized Terminal Greeting**.

## Screenshot

The lab screenshot is stored inside the [`Screenshots`](./Screenshots) folder.

* **ASCII Art Banner** — `ASCII-Art-Banner.png`

## Notes

The complete lab notes are available in [`Create-Personalized-Terminal-Greeting.docx`](./Create-Personalized-Terminal-Greeting.docx).
