### Understanding Conditional Statements in Shell Scripting

Conditional statements in shell scripting allow you to make decisions in your scripts.
Based on certain conditions, you can control the flow of the script, deciding what code 
should be executed. Here’s a step-by-step explanation with simple examples:

### 1. Basic `if` Statement

The `if` statement checks a condition, and if the condition is true, it executes the code inside the block.

**Syntax:**
```bash
if [ condition ]; then
  # Code to execute if the condition is true
fi
```

**Example:**
```bash
#!/bin/bash
number=10
if [ $number -gt 0 ]; then
  echo "The number is positive."
fi
```
- **Explanation:** The script checks if the variable `number` is greater than 0 using `-gt`. If true, it prints "The number is positive."

### 2. `if-else` Statement

The `if-else` statement allows you to execute one block of code if the condition is true and another block if it’s false.

**Syntax:**
```bash
if [ condition ]; then
  # Code to execute if the condition is true
else
  # Code to execute if the condition is false
fi
```

**Example:**
```bash
#!/bin/bash
number=-5
if [ $number -gt 0 ]; then
  echo "The number is positive."
else
  echo "The number is negative."
fi
```
- **Explanation:** The script checks if the `number` is greater than 0. If true, it prints "The number is positive"; otherwise, it prints "The number is negative."

### 3. `if-elif-else` Statement

The `if-elif-else` statement is used when you have multiple conditions to check.

**Syntax:**
```bash
if [ condition1 ]; then
  # Code to execute if condition1 is true
elif [ condition2 ]; then
  # Code to execute if condition2 is true
else
  # Code to execute if neither condition1 nor condition2 is true
fi
```

**Example:**
```bash
#!/bin/bash
number=0
if [ $number -gt 0 ]; then
  echo "The number is positive."
elif [ $number -lt 0 ]; then
  echo "The number is negative."
else
  echo "The number is zero."
fi
```
- **Explanation:** The script checks if the `number` is positive, negative, or zero and prints the corresponding message.

### 4. Comparison Operators

Shell scripting provides several operators to compare values:

- **Integer Comparison:**
  - `-eq`: Equal to
  - `-ne`: Not equal to
  - `-lt`: Less than
  - `-le`: Less than or equal to
  - `-gt`: Greater than
  - `-ge`: Greater than or equal to

**Example:**
```bash
#!/bin/bash
a=5
b=10
if [ $a -lt $b ]; then
  echo "a is less than b"
fi
```
- **Explanation:** The script checks if `a` is less than `b` using `-lt`.

- **String Comparison:**
  - `=`: Equal to
  - `!=`: Not equal to
  - `-z`: String is null (zero length)
  - `-n`: String is not null

**Example:**
```bash
#!/bin/bash
str1="hello"
str2="world"
if [ "$str1" != "$str2" ]; then
  echo "Strings are not equal"
fi
```
- **Explanation:** The script checks if `str1` is not equal to `str2`.

### 5. File Test Operators

File test operators allow you to check the properties of files.

- **File Existence:**
  - `-e file`: File exists
  - `-f file`: File exists and is a regular file
  - `-d file`: Directory exists
  - `-r file`: File is readable
  - `-w file`: File is writable
  - `-x file`: File is executable

**Example:**
```bash
#!/bin/bash
file="/path/to/file"
if [ -e $file ]; then
  echo "File exists."
else
  echo "File does not exist."
fi
```
- **Explanation:** The script checks if the file exists using `-e`.

### 6. Logical Operators

Logical operators combine multiple conditions:

- **AND (`&&`)**: Both conditions must be true.
- **OR (`||`)**: At least one condition must be true.
- **NOT (`!`)**: Inverts the condition.

**Example:**
```bash
#!/bin/bash
file="/path/to/file"
if [ -r $file ] && [ -w $file ]; then
  echo "The file is readable and writable."
else
  echo "The file is not readable and writable."
fi
```
- **Explanation:** The script checks if the file is both readable and writable using `&&`.

### 7. `case` Statement

The `case` statement matches a variable against a pattern, useful for handling multiple conditions.

**Syntax:**
```bash
case variable in
  pattern1)
    # Code to execute for pattern1
    ;;
  pattern2)
    # Code to execute for pattern2
    ;;
  *)
    # Default case (optional)
    ;;
esac
```

**Example:**
```bash
#!/bin/bash
echo "Enter your choice (start/stop/restart):"
read choice
case $choice in
  start)
    echo "Starting the service..."
    ;;
  stop)
    echo "Stopping the service..."
    ;;
  restart)
    echo "Restarting the service..."
    ;;
  *)
    echo "Invalid choice."
    ;;
esac
```
- **Explanation:** The script reads the user’s choice and matches it against "start," "stop," and "restart."

### 8. Nested `if` Statements

You can nest `if` statements to create more complex logic.

**Example:**
```bash
#!/bin/bash
file="/path/to/file"
if [ -e $file ]; then
  if [ -r $file ]; then
    echo "The file exists and is readable."
  else
    echo "The file exists but is not readable."
  fi
else
  echo "The file does not exist."
fi
```
- **Explanation:** The script first checks if the file exists and then checks if it’s readable.

### 9. Using `test` Command

The `test` command (or `[ condition ]`) is used to evaluate expressions.

**Example:**
```bash
#!/bin/bash
number=10
if test $number -gt 0; then
  echo "The number is positive."
fi
```
- **Explanation:** The `test` command checks if the `number` is greater than 0.

### Summary

- **`if`**: Executes a block of code if the condition is true.
- **`if-else`**: Provides an alternative block of code to execute if the condition is false.
- **`if-elif-else`**: Allows multiple conditions to be checked in sequence.
- **Comparison Operators**: Used for numeric and string comparisons.
- **File Test Operators**: Used to test file attributes like existence, readability, and writability.
- **Logical Operators**: Combine multiple conditions using `&&` (AND), `||` (OR), and `!` (NOT).
- **`case` Statement**: Matches a variable against multiple patterns, often used for menu-driven scripts.

These conditional statements are essential in shell scripting,
enabling decision-making based on various criteria, which is crucial for automating tasks effectively.
