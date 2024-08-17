### Understanding Variables in Shell Scripting

Variables in shell scripting allow you to store and manipulate data,
such as strings, numbers, or the output of commands. Here's a step-by-step guide to understanding variables :

#### 1. Declaring and Assigning Variables
- **Syntax:** In shell scripting, you declare and assign a value to a variable using the `=` operator. Make sure there are no spaces around the `=` operator.

    ```bash
    #!/bin/bash
    greeting="Hello, World!"
    number=42
    ```
    - `greeting` is a variable containing the string `"Hello, World!"`.
    - `number` is a variable containing the integer `42`.

#### 2. Accessing Variables
- To access the value of a variable, you use the `$` symbol before the variable name.

    ```bash
    #!/bin/bash
    greeting="Hello, World!"
    echo $greeting  # Output: Hello, World!
    ```

#### 3. Using Double Quotes
- When a variable contains spaces or special characters, enclose it in double quotes to ensure it's interpreted correctly.

    ```bash
    #!/bin/bash
    name="John Doe"
    echo "Hello, $name!"  # Output: Hello, John Doe!
    ```

#### 4. Variables with Command Substitution
- You can assign the output of a command to a variable using command substitution, which is done using `$(command)`.

    ```bash
    #!/bin/bash
    current_date=$(date)
    echo "Today's date is: $current_date"
    ```

#### 5. Environment Variables
- Environment variables are special variables that are available system-wide. Common examples include `$HOME` and `$USER`.

    ```bash
    #!/bin/bash
    echo "Home directory: $HOME"
    echo "Current user: $USER"
    ```

#### 6. Exporting Variables
- To make a variable available to other scripts, use the `export` command.

    ```bash
    #!/bin/bash
    greeting="Hello from parent script!"
    export greeting
    ./child_script.sh
    ```

    In `child_script.sh`:

    ```bash
    #!/bin/bash
    echo $greeting  # Output: Hello from parent script!
    ```

#### 7. Arithmetic Operations
- You can perform arithmetic operations using variables.

    ```bash
    #!/bin/bash
    num1=10
    num2=5
    sum=$((num1 + num2))
    echo "Sum: $sum"  # Output: Sum: 15
    ```

#### 8. Read-Only Variables
- You can make a variable read-only, meaning it cannot be changed after it's set.

    ```bash
    #!/bin/bash
    readonly pi=3.14
    pi=3.14159  # Error: pi is a readonly variable
    ```

#### 9. Unsetting Variables
- To remove a variable's value, use the `unset` command.

    ```bash
    #!/bin/bash
    name="John Doe"
    unset name
    echo $name  # Output will be empty
    ```

#### 10. Example Script Using Variables
- Here's a simple script that uses variables in various ways:

    ```bash
    #!/bin/bash
    first_name="John"
    last_name="Doe"
    year_of_birth=1990
    current_year=$(date +%Y)
    age=$((current_year - year_of_birth))
    echo "Name: $first_name $last_name"
    echo "Year of Birth: $year_of_birth"
    echo "Current Year: $current_year"
    echo "Age: $age"
    ```

### Summary
- **Declaring:** Variables are declared and assigned using `=`.
- **Accessing:** Use `$` before the variable name to access its value.
- **Quoting:** Double quotes help prevent issues with spaces or special characters.
- **Command Substitution:** Use `$(command)` to capture command output into a variable.
- **Environment Variables:** These are special system-wide variables like `$HOME` and `$USER`.
- **Exporting:** Use `export` to make a variable accessible to other scripts.
- **Arithmetic:** Perform arithmetic with `$((expression))`.
- **Read-Only:** `readonly` prevents modification of a variable.
- **Unset:** `unset` removes a variable's value.

Variables are essential in shell scripting, allowing you to write dynamic and flexible scripts.
