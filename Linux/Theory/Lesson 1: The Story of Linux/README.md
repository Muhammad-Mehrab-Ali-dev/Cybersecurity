# 🐧 Linux — Theory Lesson 1

## 📖 The Story of Linux

Understanding the history of Linux helps explain how **UNIX, GNU, GPL, and the Linux Kernel** eventually came together to form the foundation of modern GNU/Linux systems.

---

## 🏠 1. UNIX Was Born (1969)

In **1969**, **Ken Thompson** and **Dennis Ritchie** developed UNIX at **Bell Labs**.

The early version of UNIX was written in **Assembly Language**.

### 🧠 Memory Trick

> **UNIX = Ancestor of Linux**

---

## 🖥️ 2. UNIX Becomes Portable (1973)

In **1973**, Dennis Ritchie developed the **C programming language**.

UNIX was then largely rewritten in C, making it much easier to **port to different computer architectures**.

### 💡 Why Was This Important?

C made UNIX significantly more portable and easier to adapt to different computer systems.

### 🧠 Memory Trick

> **C = Carry UNIX Everywhere**

---

## 🌍 3. Richard Stallman Starts GNU (1983)

In **1983**, **Richard Stallman** announced the **GNU Project**.

His goal was to create a **free UNIX-like operating system** whose software users could use, study, modify, and share.

### GNU Stands For

> **GNU's Not UNIX**

GNU developed many important components needed for a UNIX-like operating system, but it still lacked a completed kernel.

---

## ⚙️ 4. GNU Introduces the GPL (1989)

The **GNU General Public License (GPL)** was first published in **1989**.

The GPL gives users important freedoms, including the ability to:

* Use the software
* Study and modify the source code
* Share copies
* Share modified versions under the license's conditions

The GPL became one of the most influential **free and open-source software licenses**.

---

## ❌ 5. GNU's Hurd Kernel

GNU also worked on its own kernel called **Hurd**.

However, Hurd did not become the mature, widely deployed kernel GNU originally needed.

This left GNU with many operating-system components but without a widely adopted complete kernel.

---

# 💡 What Is a Kernel?

The **kernel is the core component of an operating system**.

It manages system resources and provides the interface between software and hardware.

### ⚙️ The Kernel Manages:

```text
CPU
Memory (RAM)
Storage
Input/Output Devices
USB Devices
Network Devices
```

### 🔄 Communication Flow

```text
User
  ↓
Applications
  ↓
Kernel
  ↓
Hardware
```

### 🧪 Example

When you open an application:

```text
Application
     ↓
Requests a service
     ↓
Kernel
     ↓
Hardware Resources
     ↓
Result
```

The application does not normally communicate directly with hardware. The kernel manages access to system resources.

### 🧠 Memory Trick

> **Kernel = Core of the Operating System**

### 👤 Human Body Analogy

| Human Body     | Computer     |
| -------------- | ------------ |
| Brain          | Kernel       |
| Senses & Limbs | Hardware     |
| Activities     | Applications |

---

## 🐧 6. Linus Torvalds Creates the Linux Kernel (1991)

In **1991**, Finnish computer science student **Linus Torvalds** announced that he was working on a new operating-system kernel.

This project became the **Linux kernel**.

The Linux kernel provided the missing piece that could be combined with the GNU system components.

---

## 🎉 7. GNU + Linux

The combination of **GNU operating-system components** with the **Linux kernel** produced a complete UNIX-like operating-system environment.

```text
GNU Components + Linux Kernel
            ↓
        GNU/Linux
```

This combination became the foundation of many Linux distributions used around the world.

---

# 📌 Timeline — Quick Revision

| Year      | Event                                       |
| --------- | ------------------------------------------- |
| **1969**  | UNIX developed at Bell Labs                 |
| **1973**  | UNIX largely rewritten in C                 |
| **1983**  | GNU Project announced                       |
| **1989**  | GPL first published                         |
| **1991**  | Linux kernel project announced              |
| **1990s** | GNU/Linux systems developed and distributed |

---

# 🎯 Key Takeaways

* **UNIX** is an important ancestor of modern Linux systems.
* **C** made UNIX much more portable.
* **GNU** aimed to build a free UNIX-like operating system.
* **GPL** established important freedoms for using, modifying, and sharing software.
* **Hurd** was GNU's kernel project.
* **Linus Torvalds** created the Linux kernel.
* **GNU components + Linux kernel = GNU/Linux.**

---

## 🧠 Ultimate Memory Trick

```text
UNIX
  ↓
C
  ↓
GNU
  ↓
GPL
  ↓
Hurd
  ↓
Linux Kernel
  ↓
GNU/Linux
```

> **UNIX → C → GNU → GPL → Hurd → Linux Kernel → GNU/Linux**
