# 🧪 Mini Challenge — Know Your Linux Identity

> **Linux Journey → Grasshopper → Getting Started → Linux History → Lab 02**

This mini challenge is part of my hands-on **Linux and Cybersecurity learning journey**.

The objective is to understand how Linux identifies users, groups, and privileged accounts rather than simply memorizing commands.

---

## 📌 Lab Overview

| Item               | Details                                             |
| ------------------ | --------------------------------------------------- |
| **Lab**            | Lab 02 — Your First Linux Lab                       |
| **Challenge**      | Know Your Linux Identity                            |
| **Category**       | Linux Fundamentals                                  |
| **Focus**          | Users, Groups, UID, GID & Root                      |
| **Learning Path**  | Cybersecurity → Linux → Linux Journey → Grasshopper |
| **Level**          | Beginner                                            |
| **Practical Area** | Linux Administration & Cybersecurity                |

---

# 🎯 Objectives

By completing this challenge, I practiced how to:

* Display a custom message in the Linux terminal.
* Identify the currently logged-in user.
* Display detailed user and group information.
* Inspect the Linux `root` account.
* Display only the username using the `id` command.
* Compare Linux identity commands based on the amount of information they provide.
* Understand why Linux user identity is important for cybersecurity.

---

# 🧪 Challenge Tasks

The challenge required completing the following tasks without simply copying the exact command sequence from the lesson.

### 1. Display a greeting containing a personal message

### 2. Find the current username

### 3. Display complete user and group information

### 4. Check information about the `root` account

### 5. Display only the username using `id`

### 6. Determine which command provides the most and least information

---

# 1️⃣ Display a Personal Greeting

### Command

```bash
echo "Hello, Linux! I am learning cybersecurity."
```

### Explanation

The `echo` command displays text in the terminal.

It is a simple command, but it is useful for learning how the shell receives a command and produces output.

### Basic concept

```text
echo
 │
 └──> Displays text on the terminal
```

The message itself can be customized.

---

# 2️⃣ Find the Current Username

### Command

```bash
whoami
```

### Purpose

`whoami` displays the username of the user running the current shell.

### Example

```text
muhammad
```

The exact username depends on the Linux environment.

### Easy way to remember

```text
whoami
   ↓
"Who am I?"
   ↓
Current username
```

### Cybersecurity relevance

Knowing the current user is important when working with:

* File permissions
* User privileges
* Administrative access
* System resources
* Access control
* Privilege escalation

Before investigating what a user can access, we need to know **which user we are**.

---

# 3️⃣ Display Complete User and Group Information

### Command

```bash
id
```

### Example Output

```text
uid=1000(muhammad) gid=1000(muhammad) groups=1000(muhammad),27(sudo)
```

> The actual output can differ depending on the Linux distribution and system configuration.

---

## 🔍 Understanding `id` Output

A typical output contains several important pieces of information.

### UID

```text
uid=1000(muhammad)
```

`UID` means **User ID**.

Linux internally identifies users using numerical IDs.

For example:

```text
1000 → User ID
muhammad → Username
```

---

### GID

```text
gid=1000(muhammad)
```

`GID` means **Group ID**.

It identifies the user's primary group.

---

### Groups

```text
groups=1000(muhammad),27(sudo)
```

This shows the groups to which the user belongs.

Groups are important because Linux permissions can be assigned based on group membership.

---

## 🧠 Identity Structure

```text
                 Linux User
                     │
        ┌────────────┼────────────┐
        │            │            │
       UID          GID         Groups
        │            │            │
   User identity  Primary      Additional
                  group         groups
```

---

# 4️⃣ Check Information About the Root Account

### Command

```bash
id root
```

### Example Output

```text
uid=0(root) gid=0(root) groups=0(root)
```

> The exact output may vary between Linux systems.

---

## 🔐 What Is `root`?

`root` is the Linux **superuser account**.

The root account has extensive privileges over the operating system.

A normal user has limited permissions, while root can perform many administrative operations that ordinary users cannot.

---

## ⭐ UID 0

One particularly important fact is:

```text
root → UID 0
```

In Linux, UID `0` represents the superuser identity.

This is an important concept when studying Linux security and privilege management.

---

## ⚠️ Why Root Matters in Cybersecurity

Root privileges can allow an account or process to:

* Modify protected system files.
* Change permissions and ownership.
* Manage system services.
* Create or remove accounts.
* Install or remove system software.
* Access sensitive system resources.

Because of this, unauthorized access to root privileges can have serious security consequences.

This connects directly to cybersecurity topics such as:

* Privilege escalation
* Access control
* Least privilege
* `sudo`
* File permissions
* Account security
* System hardening

---

# 5️⃣ Display Only the Username Using `id`

### Command

```bash
id -un
```

### Example Output

```text
muhammad
```

This produces only the username rather than displaying the complete identity information.

---

## 🔍 Understanding the Options

The command can be understood as:

```text
id
 │
 ├── -u → Display the user ID
 │
 └── -n → Display the name instead of the number
```

Together:

```bash
id -un
```

means:

> Display the name associated with the current user's UID.

Therefore, the result is the username.

---

# 📊 Command Comparison

One of the goals of this challenge was to determine which command provides the most information and which provides the least.

| Command          | What It Shows                         | Information Level       |
| ---------------- | ------------------------------------- | ----------------------- |
| `echo "message"` | Custom text                           | Not an identity command |
| `whoami`         | Current username                      | Low                     |
| `id -un`         | Current username using `id`           | Low                     |
| `id root`        | Root's UID, GID and groups            | Detailed                |
| `id`             | Current UID, GID, username and groups | **Most complete**       |

### Simplified View

```text
          MORE IDENTITY INFORMATION
                    ▲
                    │
                   id
                    │
                 id root
                    │
                whoami
                    │
                 id -un
                    │
                    ▼
          LESS IDENTITY INFORMATION
```

### Conclusion

For the **current user's complete identity**, `id` provides the most information.

For displaying **only the username**, `id -un` provides the least identity information among the identity-related commands used in this challenge.

---

# 🆚 `whoami` vs `id`

Both commands can reveal the username, but they have different purposes.

## `whoami`

```bash
whoami
```

Answers:

> **Which user am I?**

Example:

```text
muhammad
```

---

## `id`

```bash
id
```

Answers a broader question:

> **What is my complete Linux identity?**

Example:

```text
uid=1000(muhammad) gid=1000(muhammad) groups=1000(muhammad),27(sudo)
```

Therefore:

```text
whoami
   ↓
Username

id
   ↓
Username
   +
UID
   +
GID
   +
Groups
```

---

# 🔐 Why Linux Identity Matters in Cybersecurity

Linux security is strongly connected to **identity, permissions and privileges**.

A simplified model is:

```text
                    User
                     │
                     ▼
                    UID
                     │
              ┌──────┴──────┐
              │             │
             GID          Groups
              │             │
              └──────┬──────┘
                     │
                     ▼
               Permissions
                     │
                     ▼
              Resource Access
                     │
                     ▼
               System Security
```

Understanding users and groups provides the foundation for later cybersecurity topics such as:

* Linux file permissions
* File ownership
* Group-based access
* `sudo`
* Privilege escalation
* User management
* Process ownership
* Access control
* System auditing

---

# 🧠 Key Concepts Learned

## User

A user represents an identity that can interact with a Linux system.

---

## UID

**UID = User ID**

A numerical identifier assigned to a Linux user.

Example:

```text
UID 1000 → normal user
UID 0    → root/superuser
```

The exact UID ranges and conventions can vary between systems, but UID `0` has the special superuser meaning.

---

## GID

**GID = Group ID**

A numerical identifier representing a Linux group.

---

## Group

A group is a collection of users.

Groups help Linux organize permissions and access to resources.

---

## Root

`root` is the superuser identity.

```text
root
 ↓
UID 0
 ↓
Extensive administrative privileges
```

---

# 🧪 Commands Practiced

```bash
echo "Hello, Linux! I am learning cybersecurity."

whoami

id

id root

id -un
```

---

# 📝 Quick Revision Notes

| Command   | Remember It As  |
| --------- | --------------- |
| `echo`    | Print text      |
| `whoami`  | Who am I?       |
| `id`      | Full identity   |
| `id root` | Root's identity |
| `id -un`  | Username only   |

---

# 💡 Important Observation

A username is only the human-readable representation of an identity.

Linux also works with numerical identifiers:

```text
Username
    │
    ▼
   UID
    │
    ▼
Linux identifies the user
```

Similarly:

```text
Group Name
    │
    ▼
   GID
    │
    ▼
Linux identifies the group
```

This distinction becomes particularly important when working with Linux permissions and system administration.

---

# 🛡️ Cybersecurity Takeaway

> **Before understanding what a user is allowed to do, we need to understand who the user is.**

This small challenge introduced an important cybersecurity foundation:

```text
Identity
   ↓
Users & Groups
   ↓
UID / GID
   ↓
Permissions
   ↓
Privileges
   ↓
Access Control
   ↓
System Security
```

Understanding this chain will make later Linux cybersecurity topics easier to understand, especially **permissions, `sudo`, privilege escalation and access control**.

---

# 📸 Lab Evidence

The completed challenge was performed in the Linux environment and documented with a screenshot.

### Evidence File

```text
Screenshots-of-mini-challange.png
```

The screenshot provides practical evidence of the commands executed during the challenge and their terminal output.

---

# 📁 Repository Structure

This lab is organized within my cybersecurity learning repository as:

```text
Cybersecurity/
└── Linux/
    └── Linux-journey/
        └── Grasshopper/
            └── 01-Getting-Started/
                └── 01-Linux-History/
                    └── Lab-02-Your-First-Linux-Lab/
                        └── Final-Mini-Challenge/
                            ├── README.md
                            └── Screenshots-of-mini-challange.png
```

---

# ✅ Challenge Checklist

* [x] Display a personal greeting
* [x] Identify the current Linux username
* [x] Display complete user and group information
* [x] Inspect the `root` account
* [x] Display only the username using `id`
* [x] Compare identity commands
* [x] Understand UID and GID
* [x] Understand Linux groups
* [x] Understand the purpose of the root account
* [x] Connect Linux identity concepts with cybersecurity
* [x] Document practical lab evidence

---

# 🎓 Learning Outcome

After completing this challenge, I can now explain the basic Linux identity model rather than only remembering commands.

I understand that Linux identifies users and groups using numerical IDs, that `id` can provide detailed identity information, that `whoami` provides the current username, and that the `root` account represents the superuser identity with UID `0`.

These concepts form part of the foundation required for understanding **Linux permissions, privilege management and cybersecurity**.

---

# 🚀 Next Step

The next Linux lessons will build upon these fundamentals and move toward more practical Linux concepts, including:

```text
Users
  ↓
Groups
  ↓
File Ownership
  ↓
File Permissions
  ↓
Processes
  ↓
Privileges
  ↓
System Administration
  ↓
Linux Security
```

---

## 👨‍💻 Author

**Muhammad Mehrab Ali**

BSCS Student | Cybersecurity Learner

Currently building practical cybersecurity skills through:

* Linux labs
* Hands-on practice
* Technical documentation
* Cybersecurity fundamentals
* Practical projects
* Continuous learning

---

> **Learning philosophy:**
> **Don't just copy the command. Understand what it does, why it works, what its output means, and how the concept connects to cybersecurity.**
