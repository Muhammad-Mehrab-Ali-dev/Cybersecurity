# 🐧 Quick Start with Linux

> **Linux Fundamentals | Command Line | Filesystem | Permissions | Users & Groups**

This directory contains my hands-on documentation for **LabEx — Quick Start with Linux**, a beginner-level Linux course designed to build a practical command-line foundation.

Rather than simply collecting commands, I am documenting **what each command does, why it is used, what output it produces, and how the concept connects to cybersecurity**.

This course is one of the foundational stages of my broader:

**Linux → Networking → Scripting → Cybersecurity**

learning path.

---

## 🎯 Course Objective

The purpose of this course is to build a strong foundation in everyday Linux command-line operations before moving into more advanced system administration and cybersecurity topics.

Throughout these labs, I practice:

* Linux terminal fundamentals
* Users and groups
* Files and directories
* File operations
* File contents and comparison
* File permissions
* File ownership
* User account management
* Practical Linux problem-solving

---

## 🧠 My Learning Approach

My goal is **not to memorize Linux commands blindly**.

Instead, I follow this process:

```text
Understand the concept
        ↓
Run the command
        ↓
Observe the output
        ↓
Understand what changed
        ↓
Verify the result
        ↓
Document the learning
```

This approach helps me build practical Linux knowledge that can later be applied to cybersecurity investigations, administration, automation, and security labs.

---

# 📚 Course Labs

The course contains **10 practical labs/challenges**.

| #  | Lab                                                                               | Main Concept                       | Status          |
| -- | --------------------------------------------------------------------------------- | ---------------------------------- | --------------- |
| 01 | [Your First Linux Lab](./Lab-01-Your-First-Linux-Lab)                             | Linux environment & basic commands | 🟢 Completed    |
| 02 | [Display User and Group Information](./Lab-02-Display-User-and-Group-Information) | Users & groups                     | 🟢 Completed    |
| 03 | [Basic Files Operations](./Lab-03-Basic-Files-Operations)                         | File operations                    | 🟢 Completed    |
| 04 | Files and Directories                                                             | Filesystem navigation & management | ⏳ Documentation |
| 05 | File Contents and Comparing                                                       | Reading & comparing files          | ⏳ Documentation |
| 06 | The Manuscript Mystery                                                            | Practical file investigation       | ⏳ Documentation |
| 07 | Permissions of Files                                                              | Linux permissions                  | ⏳ Documentation |
| 08 | Change File Ownership                                                             | Ownership & access control         | ⏳ Documentation |
| 09 | User Account Management                                                           | User administration                | ⏳ Documentation |
| 10 | The Joker's Trick                                                                 | Practical challenge                | ⏳ Documentation |

> **Note:** The status will be updated as each lab is completed and documented with commands, explanations, and practical evidence.

---

# 🔬 What I Am Practicing

## 01 — Linux Basics

Learning how to interact with Linux through the terminal and understand the basic command-line environment.

Examples:

```bash
pwd
whoami
id
ls
cd
```

---

## 02 — Users & Groups

Understanding Linux identity and group membership.

Key concepts:

```text
User
  ↓
Groups
  ↓
Permissions
  ↓
Access
```

This is an important foundation for understanding Linux access control.

---

## 03 — Files & Directories

Learning how Linux organizes information through a hierarchical filesystem.

Practiced operations include:

```bash
pwd
ls
cd
mkdir
touch
cp
mv
rm
```

---

## 04 — File Contents

Learning how to inspect information stored inside files from the command line.

Examples include:

```bash
cat
head
```

The focus is on understanding file contents rather than simply opening files graphically.

---

## 05 — File Comparison

Learning how to compare files and identify differences.

This introduces a useful concept for cybersecurity:

> **Changes in files can provide important clues during investigation.**

---

## 06 — File Permissions

Understanding the Linux permission model:

```text
             File
              │
       ┌──────┼──────┐
       │      │      │
     Owner   Group  Others
       │      │      │
       └──────┼──────┘
              │
       ┌──────┼──────┐
       │      │      │
       r      w      x
      Read   Write Execute
```

Where:

```text
r = Read
w = Write
x = Execute
```

I also practice both symbolic and numeric permission notation.

Example:

```bash
chmod 755 script.sh
```

---

## 07 — File Ownership

Learning how Linux associates files with:

```text
Owner
Group
```

and how ownership interacts with permissions.

Example:

```bash
chown user:group file
```

---

## 08 — User Account Management

Exploring basic Linux account administration, including concepts related to:

* Creating users
* Modifying users
* Managing groups
* Locking accounts
* Unlocking accounts
* Removing users

---

# 🛡️ Cybersecurity Connection

Although **Quick Start with Linux** is a beginner course, the concepts are directly relevant to cybersecurity.

| Linux Foundation | Cybersecurity Application |
| ---------------- | ------------------------- |
| Users            | Identity                  |
| Groups           | Access management         |
| Permissions      | Authorization             |
| Ownership        | Resource control          |
| Files            | Evidence & system data    |
| Directories      | Filesystem investigation  |
| Terminal         | Security tooling          |
| File comparison  | Change detection          |
| User accounts    | Authentication & access   |

These concepts will become increasingly important when I move into:

```text
Linux
   ↓
Networking
   ↓
Bash / Scripting
   ↓
System Administration
   ↓
Cybersecurity
   ↓
Security Labs
   ↓
Projects & Research
```

---

# 📸 Practical Evidence

Each lab is being documented separately with:

* Commands used
* Command output
* Concept explanations
* Important observations
* Cybersecurity relevance
* Screenshots of practical work
* Challenges and solutions

The purpose of the screenshots is not decoration.

They provide **evidence of hands-on practice** and show how the commands were actually executed in a Linux environment.

---

# 📂 Repository Structure

```text
Lab-01-Quic-Start-with-Linux/
│
├── Lab-01-Your-First-Linux-Lab/
│   └── README.md
│
├── Lab-02-Display-User-and-Group-Information/
│   └── README.md
│
├── Lab-03-Basic-Files-Operations/
│   └── README.md
│
├── Lab-04-Files-and-Directories/
│   └── README.md
│
├── Lab-05-File-Contents-and-Comparing/
│   └── README.md
│
├── Lab-06-The-Manuscript-Mystery/
│   └── README.md
│
├── Lab-07-Permissions-of-Files/
│   └── README.md
│
├── Lab-08-Change-File-Ownership/
│   └── README.md
│
├── Lab-09-User-Account-Management/
│   └── README.md
│
├── Lab-10-The-Joker's-Trick/
│   └── README.md
│
└── README.md
```

---

# 📈 Progress

```text
Quick Start with Linux
        │
        ├── 01  ████████████████████  Complete
        ├── 02  ████████████████████  Complete
        ├── 03  ████████████████████  Complete
        ├── 04  ░░░░░░░░░░░░░░░░░░░░  In Progress
        ├── 05  ░░░░░░░░░░░░░░░░░░░░  In Progress
        ├── 06  ░░░░░░░░░░░░░░░░░░░░  In Progress
        ├── 07  ░░░░░░░░░░░░░░░░░░░░  In Progress
        ├── 08  ░░░░░░░░░░░░░░░░░░░░  In Progress
        ├── 09  ░░░░░░░░░░░░░░░░░░░░  In Progress
        └── 10  ░░░░░░░░░░░░░░░░░░░░  In Progress
```

**3 / 10 labs documented**

---

# 🚀 Next Step

After completing this Linux foundation, I will continue expanding my practical knowledge into:

* Networking fundamentals
* Linux administration
* Bash scripting
* Processes & services
* SSH
* Package management
* Security tools
* Cybersecurity labs
* Practical security projects

This repository will continue to evolve as I progress through my cybersecurity learning journey.

---

## 🧩 Key Takeaway

> **Linux is not just a collection of commands. It is an environment where users, files, processes, permissions, and system resources interact.**

Understanding these fundamentals is the first step toward becoming comfortable with Linux in real-world cybersecurity environments.

---

### 🐧 Part of My Cybersecurity Learning Journey

**Linux → Networking → Scripting → Cybersecurity → Projects → Research**

*Building practical skills one lab at a time.*
