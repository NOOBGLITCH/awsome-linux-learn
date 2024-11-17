
# Welcome to the **Awsome Learn Linux** 🐧

<div align="center">    <img src="https://i.ibb.co/GHDwkFR/cropped-image.png" alt="Linux Image" height="200" width="200" />
</div>
<hr>

This project provides you with essential information, cheat sheets, and commands to master Linux. Whether you're a beginner or an experienced user, this repository is your go-to guide for navigating the Linux operating system. 
<hr>

[🐧Linux All Commands Cheatsheets](https://github.com/NOOBGLITCH/awsome-linux-learn/blob/main/linux%20all%20commands%20chetsheets%20.pdf)

<hr>

## 🔧 **Prerequisites**

To get the most out of this repository, you need:
- A basic understanding of how to use the Linux terminal.
- A Linux operating system (Ubuntu, CentOS, etc.) or a virtual environment like Docker to practice.

For beginners, it's recommended to start with the **Cheat Sheets** and **Commands** sections before diving into loops, functions, and scripts.

---

## 📚 **What You Will Find**

- **Cheat Sheets**: Quick reference guides for common Linux commands, utilities, and configurations.
- **Commands**: A comprehensive list of essential commands categorized by functionality.
- **Loops & Functions**: Detailed explanations and examples of loops (`for`, `while`, `until`) and functions in shell scripting to automate tasks and improve productivity.

---

**Then, dive into the sections and start mastering Linux! 💻**

## **Topics Covered** 📘

1. [Understanding File Permissions in Linux 🔒](#1-understanding-file-permissions-in-linux-)
2. [Using `chmod` to Modify Permissions ⚙️](#2-using-chmod-to-modify-permissions-%EF%B8%8F)
3. [Conditional Operators in Linux 🧮](#3-conditional-operators-in-linux-)
   - [Numeric Operators](#numeric-operators)
   - [String Operators](#string-operators)
   - [File/Directory Tests](#filedirectory-tests)
4. [Linux Loops 🔄](#4-linux-loops-)
   - [For Loop](#for-loop)
   - [While Loop](#while-loop)
   - [Until Loop](#until-loop)
   - [Do-While Loop (Simulated)](#do-while-loop-simulated)
5. [Linux Functions 🔧](#5-linux-functions-)
   - [Simple Function](#simple-function)
   - [Function with Arguments](#function-with-arguments)
   - [Function with Return Value](#function-with-return-value)
   - [Recursive Function](#recursive-function)
   - [Function with Default Parameters](#function-with-default-parameters)
 6. [File System Hierarchy 📁](#6-file-system-hierarchy-)
---

## **1. Understanding File Permissions in Linux 🔒**

File permissions determine who can **read**, **write**, or **execute** a file. These permissions are divided into three categories:
- **Owner**: `rwx` (full access).
- **Group**: `r-x` (read and execute only).
- **Others**: `r--` (read only).

This helps in managing file access and security for different users on a system.

---

## **2. Using `chmod` to Modify Permissions ⚙️**

The `chmod` command is used to modify file and directory permissions.

### **Command Syntax**
```bash
chmod [options] mode file
```
- `mode`: Defines the new permissions (numeric or symbolic).
- `file`: The target file or directory.

### **Common Examples**
1. **Set full access (777)**:
   ```bash
   chmod 777 file.txt
   ```

2. **Set read/write for owner, read for group and others (644)**:
   ```bash
   chmod 644 file.txt
   ```

3. **Recursive permissions for directories**:
   ```bash
   chmod -R 755 /path/to/directory
   ```

---

## **3. Conditional Operators in Linux 🧮**

Conditional operators are used to perform comparisons or checks in shell scripts.

### **Numeric Operators**
- **`-eq`**: Equal to.
- **`-ne`**: Not equal to.
- **`-lt`**: Less than.
- **`-le`**: Less than or equal to.
- **`-gt`**: Greater than.
- **`-ge`**: Greater than or equal to.

### **String Operators**
- **`=`**: Strings are equal.
- **`!=`**: Strings are not equal.
- **`-z`**: String is null (zero length).
- **`-n`**: String is not null.

### **File/Directory Tests**
- **`-f`**: File exists and is a regular file.
- **`-d`**: Directory exists.
- **`-e`**: File or directory exists.
- **`-r`**: File is readable.
- **`-w`**: File is writable.
- **`-x`**: File is executable.

---

## **4. Linux Loops 🔄**

Loops automate repetitive tasks in Linux by executing commands based on conditions.

### **For Loop**  
Iterates over a fixed range or list.

**Syntax**:
```bash
for variable in list; do
  commands
done
```

**Examples**:
1. **Using a range with `{}`**:
   ```bash
   for i in {1..10}; do
     echo $i
   done
   ```

2. **Using C-style syntax (`i++`)**:
   ```bash
   for ((i = 1; i < 10; i++)); do
     echo $i
   done
   ```

---

### **While Loop**  
Executes commands as long as a condition is true.

**Syntax**:
```bash
while [ condition ]; do
  commands
done
```

**Example**:
```bash
i=1
while [ $i -le 10 ]; do
  echo $i
  i=$((i + 1))
done
```

---

### **Until Loop**  
Executes commands until a condition becomes true.

**Syntax**:
```bash
until [ condition ]; do
  commands
done
```

**Example**:
```bash
i=1
until [ $i -gt 10 ]; do
  echo $i
  i=$((i + 1))
done
```

---

### **Do-While Loop (Simulated)**  
Linux does not have a direct `do-while` loop, but you can simulate it using a `while` loop.

**Purpose**: Executes commands at least once before checking the condition.

**Syntax**:
```bash
commands
while [ condition ]; do
  commands
done
```

**Example**:
```bash
i=1
echo $i
while [ $i -lt 10 ]; do
  i=$((i + 1))
  echo $i
done
```

---

## **5. Linux Functions 🔧**

Functions help automate complex tasks, making your scripts more modular and reusable.

### **Simple Function**
A simple function without arguments or return values.

**Syntax**:
```bash
function_name() {
  commands
}
```

**Example**:
```bash
greet() {
  echo "Hello, Linux!"
}
greet
```

### **Function with Arguments**
Functions can accept parameters passed to them.

**Syntax**:
```bash
function_name() {
  echo "Argument 1: $1"
  echo "Argument 2: $2"
}
```

**Example**:
```bash
greet_user() {
  echo "Hello, $1!"
}
greet_user "Alice"
```

### **Function with Return Value**
Functions can return a value using `return`.

**Syntax**:
```bash
function_name() {
  return 0  # or any integer value
}
```

**Example**:
```bash
add() {
  sum=$(( $1 + $2 ))
  return $sum
}
add 3 5
echo "Sum: $?"
```

### **Recursive Function**
A function that calls itself to perform repetitive tasks.

**Example**:
```bash
factorial() {
  if [ $1 -le 1 ]; then
    echo 1
  else
    prev=$(factorial $(( $1 - 1 )))
    echo $(( $1 * $prev ))
  fi
}
result=$(factorial 5)
echo "Factorial: $result"
```

### **Function with Default Parameters**
Functions can use default parameters if no argument is passed.

**Example**:
```bash
greet() {
  name=${1:-"Guest"}
  echo "Hello, $name!"
}
greet "Alice"
greet
```

---
## **6. File System Hierarchy 📁**

The Linux file system is structured in a tree-like hierarchy, with directories having specific roles. Here are the key directories:

- **`/`** - Root directory; the base of the entire file system.
- **`/bin`** - Essential system binaries (e.g., `ls`, `cp`).
- **`/boot`** - Kernel boot loader files.
- **`/dev`** - Device files.
- **`/etc`** - System configuration files.
- **`/home`** - User home directories (e.g., documents, settings).
- **`/lib`** - Libraries used by binaries.
- **`/media`** - Mount points for removable media (e.g., USB drives).
- **`/mnt`** - Temporary mount points for filesystems.
- **`/opt`** - Optional application software packages.
- **`/proc`** - Kernel and process information.
- **`/root`** - Home directory of the root user.
- **`/run`** - Runtime information about the system since the last boot.
- **`/sbin`** - System binaries, typically for administrative tasks.
- **`/srv`** - Data for services provided by the system.
- **`/tmp`** - Temporary files storage.
- **`/usr`** - User programs and utilities, including subdirectories like `/usr/bin`, `/usr/local`.
- **`/var`** - Variable data (logs, caches, spool files, etc.).

## 🌐 **Learn More About Linux**

- [Learn Shell](https://www.learnshell.org/) - Interactive tutorials to master Linux shell scripting.
- [Linux Journey](https://linuxjourney.com/) - Explore Linux concepts with a structured, beginner-friendly approach.
## 📄 **License**

This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

💡 **Feel Free to Contribute!**

**We welcome contributions to make this guide even better! If you have scripts, tips, or enhancements to share, feel free to create a pull request! 🚀**

---

**Start mastering Linux today! 🌟**
