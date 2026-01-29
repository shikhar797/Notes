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


In Bash scripting, the

`if` statement is a fundamental control structure that executes a block of code based on whether a given condition is true (exit status zero) or false (non-zero). The structure must always end with `fi`. 

Basic Syntax

The most basic `if` statement syntax is:

bash

```
if [ condition ]; then
  # Commands to execute if the condition is true
fi
```

**Key rules:**

- `if`, `then`, `else`, `elif`, and `fi` are shell keywords and must appear as the first word on a line or be separated from the previous statement by a semicolon `;`.
- Spaces are required inside the square brackets: `[ condition ]` is correct, `[condition]` is not.
- It is a good practice to quote variables within conditions to avoid issues with spaces or empty values (e.g., `[ "$var" -eq 1 ]`). 

Types of If Statements

|Statement|Description|Syntax Example|
|---|---|---|
|**If**|Executes commands if the condition is true.|`if [ "$num" -gt 10 ]; then echo "Greater"; fi`|
|**If-Else**|Executes one block if true, a different block if false.|`if [ "$num" -gt 10 ]; then echo "Greater"; else echo "Less than or equal"; fi`|
|**If-Elif-Else**|Checks multiple conditions sequentially. The first one that is true gets executed.|`if [ "$num" -gt 10 ]; then echo "Greater"; elif [ "$num" -eq 10 ]; then echo "Equal"; else echo "Less than"; fi`|

Common Conditional Expressions

Conditions use test operators within `[ ]` (or the more modern `[[ ]]`) or `(( ))` for arithmetic operations. 

|Category|Operator|Meaning|Example|
|---|---|---|---|
|**Numeric**|`-eq`|Equal to|`[ "$a" -eq "$b" ]`|
||`-ne`|Not equal to|`[ "$a" -ne "$b" ]`|
||`-gt`|Greater than|`[ "$a" -gt "$b" ]`|
||`-lt`|Less than|`[ "$a" -lt "$b" ]`|
||`-ge`|Greater than or equal to|`[ "$a" -ge "$b" ]`|
||`-le`|Less than or equal to|`[ "$a" -le "$b" ]`|
|**String**|`=` or `==`|Equal to|`[ "$s1" = "$s2" ]`|
||`!=`|Not equal to|`[ "$s1" != "$s2" ]`|
||`-z`|String is empty|`[ -z "$s1" ]`|
||`-n`|String is not empty|`[ -n "$s1" ]`|
|**File**|`-f`|Exists and is a regular file|`[ -f "$file" ]`|
||`-d`|Exists and is a directory|`[ -d "$file" ]`|
||`-e`|File exists|`[ -e "$file" ]`|

Multiple Conditions

Use logical operators to combine conditions. 

- **AND:** Use `&&` with `[[ ]]` or `-a` with `[ ]`.
- **OR:** Use `||` with `[[ ]]` or `-o` with `[ ]`. 

bash

```
if [[ "$num" -gt 5 && "$num" -lt 10 ]]; then
  echo "Number is between 5 and 10"
fi
```


### 🔹 Exit Code

Exit codes are numeric values returned when a command is terminated.  
They indicate whether the command **executed successfully or failed due to some error**.

- `0` → command executed successfully
    
- `non-zero` → command failed
    

To check the exit code of the last executed command:

`echo $?`

Exit codes are commonly used in **shell scripts** to make decisions using conditions.

---

### 🔹 Redirection

Redirection is used to **redirect output or error messages** of a command to a file instead of displaying them on the terminal.  
It is mainly used for **logging output** or **hiding unwanted messages**.

Example:

`command > output.txt`  -> this overrides the file
`command >> error.txt`  -> this appends the file 
