## **Index**
1. [Understanding File Permissions in Linux](#1understanding-file-permissions-in-linux)
2. [Using `chmod` to Modify Permissions](#2-using-chmod-to-modify-permissions)
3. [Conditional Operators in Linux](#3-conditional-operators-in-linux)
   - [Numeric Operators](#numeric-operators)
   - [String Operators](#string-operators)
   - [File/Directory Tests](#filedirectory-tests)
4. [Linux Loops](#4-linux-loops)
   - [For Loop](#for-loop)
   - [While Loop](#while-loop)
   - [Until Loop](#until-loop)
   - [Do-While Loop (Simulated)](#do-while-loop-simulated)

## **1.Understanding File Permissions in Linux**
Breakdown:
- Owner: `rwx` (full access).
- Group: `r-x` (read and execute only).
- Others: `r--` (read only).

---

## **2. Using `chmod` to Modify Permissions**

### **Command Syntax**
```bash
chmod [options] mode file
```
- `mode`: Defines new permissions (numerical or symbolic).
- `file`: Target file or directory.

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

## **3. Conditional Operators in Linux**

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

## **4. Linux Loops**

Loops automate repetitive tasks by executing commands multiple times based on conditions.

### **For Loop**
**Purpose**: Iterates over a fixed range or list.  
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
**Purpose**: Executes commands while a condition is true.  
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
**Purpose**: Executes commands until a condition becomes true.  
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
Linux shell scripting does not have a direct do-while loop, but it can be simulated using `while`.  
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

