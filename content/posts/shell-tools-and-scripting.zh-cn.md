+++
date = "2020-05-13"
title = "Shell tools and Scripting"
tags = [
    "Shell"
]
categories = [
    "Shell"
]
series = ["Missing Semester"]
featured_image = "https://images.unsplash.com/photo-1589287665644-da432657a081?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80"
+++

# Shell Scripting

- ## Variable

  ```bash
  foo=bar
  echo "$foo"
  // prints bar
  echo '$foo'
  // prints $foo
  ```

  

- ## Control Flow

  ```bash
  mcd () {
  	mkdir -p "$1"
  	cd "$1"
  }
  ```

  > - `$0` - Name of the script
  > - `$1` to `$9` - Arguments to the script. `$1` is the first argument and so on.
  > - `$@` - All the arguments
  > - `$#` - Number of arguments
  > - `$?` - Return code of the previous command
  > - `$$` - Process Identification number for the current script
  > - `!!` - Entire last command, including arguments. A common pattern is to execute a command only for it to fail due to missing permissions, then you can quickly execute it with sudo by doing `sudo !!`
  > - `$_` - Last argument from the last command. If you are in an interactive shell, you can also quickly get this value by typing `Esc` followed by `.`

- ## Exist Codes

  ```bash
  true
  echo $?
  // 0
  false
  echo $?
  // 1
  false || echo "Oops, fail"
  // Oops, fail
  true || echo "Oops, fail"
  //
  true && echo "Oops, fail"
  // Oops, fail
  false && echo "Oops, fail"
  //
  false ; echo "This will always run"
  // This will always run
  ```

  > - Exit codes can be used to conditionally execute commands using `&&` (and operator) and `||` (or operator). Commands can also be separated within the same line using a semicolon `;`. The `true` program will always have a 0 return code and the `false` command will always have a 1 return code. 
  > - A value of 0 usually means everything went OK, anything different from 0 means an error occurred.

- 