# Bash Basics & User Automation
Objective

# Understand Bash scripting fundamentals and automate Linux user creation.
# 1. Bash Basics
Check Bash Version
Bash

bash --version

Example output:
GNU bash, version 5.2.x (x86_64-pc-linux-gnu)
Echo Command
Bash

echo "Hello World"

# 2. Variables in Bash
Declaring Variables
Bash

name="joel"
echo "Hello, $name"

Rules:

    No spaces around =

    Access variable using $variable_name

Example:
Bash

number=43
echo "The number is $number"

Environment Variables
Bash

echo "Your PATH is $PATH"

Local vs Global Variables
Bash

myfunction() {
  local local_var="This is local"
  echo $local_var
}

myfunction

# 3. String Operations
Concatenation
Bash

greeting="Hello"
name="World"
echo "$greeting $name"

# 4. Arithmetic Operations

Bash supports integer arithmetic using $(( )).
Bash

num1=23
num2=70
sum=$((num1 + num2))
echo "The sum is $sum"

Operators:

    + Addition

    - Subtraction

    * Multiplication

    / Division

    % Modulus

    Note: Bash does not support floating-point arithmetic natively.

# 5. Arrays in Bash
Bash

fruits=("Apple" "Strawberry" "Mango")

for fruit in "${fruits[@]}"; do
  echo $fruit
done

# 6. Comparison Operators
Numeric Comparison	Description	String Comparison	Description
-eq	Equal to	=	Equal to
-ne	Not equal to	!=	Not equal to
-lt	Less than	<	Less than (ASCII)
-le	Less than or equal to	>	Greater than (ASCII)
-gt	Greater than		
-ge	Greater than or equal to		
# 7. Logical Operators

    && Logical AND

    || Logical OR

    ! Logical NOT

# 8. File Test Operators

    -e Check if file exists

    -d Check if directory exists

    -f Check if regular file

    -s Check if file is not empty

# 9. If-Else Statement
Bash

if [ condition ]; then
  echo "Condition is true"
else
  echo "Condition is false"
fi

# 10. User Creation Automation Script
Script: create_user.sh
Bash

#!/bin/bash

echo "What is the new username?"
read USERNAME

if id "$USERNAME" &>/dev/null; then
    echo "User $USERNAME already exists."
    exit 1
fi

sudo useradd -m $USERNAME
sudo passwd $USERNAME

echo "Done! User $USERNAME is ready."

What This Script Does

    Takes username input.

    Checks if user already exists.

    Creates user with home directory.

    Prompts to set password.

    Displays confirmation message.

# Security Notes

    Avoid using root for daily operations.

    Follow the principle of least privilege.

    Automating administrative tasks reduces human error.

# Key Learning Summary

    Practiced Bash fundamentals.

    Understood variables, arithmetic, and conditionals.

    Learned comparison and file test operators.

    Built first Linux user automation script.
