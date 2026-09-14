# Lab 02 — Display User and Group Information

> **Linux Journey · Grasshopper · Getting Started**

## 📌 Overview

This LabEx challenge focuses on identifying the **current Linux user** and inspecting the user's **UID, GID, and group memberships**.

Understanding user identity and group membership is essential for working with Linux permissions, access control, privilege management, and security troubleshooting.

---

## 🎯 Objectives

By completing this challenge, I learned how to:

* Identify the currently logged-in Linux user.
* Display detailed user and group information.
* Understand **UID**, **GID**, and group memberships.
* Verify the execution identity of a Linux shell.

---

## 1. Current User Identity

### Command

```bash
whoami
```

### What it does

Displays the username of the user currently running the shell.

### Example

```bash
whoami
```

Example output:

```text
labex
```

### Solved Challenge

---

## 2. Detailed User and Group Information

### Command

```bash
id
```

### What it does

Displays detailed information about the current user, including:

* **UID** — User ID
* **GID** — Primary Group ID
* **groups** — Groups the user belongs to

### Example

```bash
id
```

Example output:

```text
uid=1000(labex) gid=1000(labex) groups=1000(labex),27(sudo)
```

> The actual UID, GID, username, and groups depend on the Linux environment.

### Understanding the Output

```text
uid=1000(labex)
│       │
│       └── Username
└────────── User ID

gid=1000(labex)
│       │
│       └── Primary group
└────────── Group ID
```

### Solved Challenge

---

## 🔐 Cybersecurity Relevance

User and group identification is a basic but important part of Linux security.

Before investigating permissions, privileges, or access problems, a security analyst should know:

```text
Who am I?
   ↓
What is my UID?
   ↓
What is my primary GID?
   ↓
Which groups do I belong to?
   ↓
What resources can I potentially access?
```

Group membership can affect a user's access to files, directories, devices, and administrative functions.

---

## 📋 Commands Used

| Command  | Purpose                                  |
| -------- | ---------------------------------------- |
| `whoami` | Displays the current username            |
| `id`     | Displays UID, GID, and group memberships |

---

## 🧠 Key Takeaways

* `whoami` → **Who am I?**
* `id` → **Who am I + UID + GID + groups**
* **UID** identifies a user.
* **GID** identifies a group.
* Group membership can influence Linux permissions and access.

---

## 🧪 Challenge Summary

**Challenge:** Display User and Group Information
**Platform:** LabEx
**Area:** Linux Fundamentals
**Focus:** User Identity & Group Management
**Status:** ✅ Completed

---

## 👤 Author

**Muhammad-Mehrab-Ali-dev**

Cybersecurity-Focused CS Student | Linux & Cybersecurity Learner

This lab is part of my ongoing **Linux → Cybersecurity learning journey**, where I am building practical skills through hands-on labs, challenges, and documented projects.

---

### 📚 Learning Path

**Cybersecurity → Linux → Linux Journey → Grasshopper → Getting Started → Lab 02**

The purpose of this repository is to document my practical learning progress and build a strong foundation in **Linux, cybersecurity, networking, and security operations**.

