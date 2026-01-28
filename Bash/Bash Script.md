# Bash Scripting Basics

## 1. How to Create a Bash Script

Create a new script file using any code editor. For example, using `nano`:

`nano myscript.sh`

> You can use **any editor** like `vim`, `code` (VS Code), or `gedit`.  
> The script name can be anything, but it’s common to use the `.sh` extension.

---

## 2. Make the Script Executable

After creating the file, you need to give it executable permissions:

`chmod +x myscript.sh`

This allows the script to be run as a program.

---

## 3. Run the Bash Script

Execute the script using:

`./myscript.sh`

---

## 4. Shebang (Interpreter Line)

At the very top of your script, add this line:

`#!/bin/bash`

This line tells the system **which interpreter** should be used to execute the script (in this case, Bash).

---

## 5. Variables in Bash

### Declaring a Variable

`myname="Shikhar"`

⚠️ **Important:**  
There must be **no spaces** around the `=` sign.

### Accessing a Variable

Use the `$` symbol to access the variable value:

`echo $myname`

---

### Single Quotes vs Double Quotes

#### Using Single Quotes `' '`

`echo 'hello my name is $myname'`

**Output:**

`hello my name is $myname`

➡️ Variables are **not expanded** inside single quotes.

#### Using Double Quotes `" "`

`echo "hello my name is $myname"`

**Output:**

`hello my name is Shikhar`

➡️ Variables **are expanded** inside double quotes.

---

## 6. Subshells in Bash

Subshells allow you to store the output of a command in a variable.

### Example 1: Listing Files

`file=$(ls) echo $file`

This stores the output of the `ls` command in the variable `file`.

### Example 2: Date and Time

`a=$(date) echo $a`

This prints the current date and time.

---

## 7. Environment Variables

To view environment variables, use:

`env`

This displays all environment variables available in the current shell.

---

## 8. Math Operations in Bash (Using `expr`)

⚠️ **Spaces are mandatory** when using `expr`.

### Addition

`expr 10 + 30`

### Multiplication

`expr 10 \* 4`

> The `*` must be escaped with `\` because it has a special meaning in Bash.