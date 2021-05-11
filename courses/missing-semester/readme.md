# [Missing Semester](https://missing.csail.mit.edu) Notes

> Have the passion, take the action and magic will happen. -[ Bar Refaeli ](https://en.wikipedia.org/wiki/Bar_Refaeli)

## Overview and shell

### 2. Shell Tools and Scripting

1. Assign varibles in bash, use the syntax `foo=bar` without space. Use `$foo` to access the value of varible.

```bash
foo=bar
# "" eval the varible; '' will not replace with varible value
echo "$foo"
echo '$foo'
```

2. Bash supports control flow techniques including `if`, `case`, `while` and `for`.

```shell
# filename: mcd.sh (executable) - mkdir a dir and cd into it: $1 means the first argument to the script/function
mcd () {
    mkdir -p "$1"
    cd "$1"
}
```

Then if you run

```bash
source mcd.sh
mcd testfolder
```

You'll `cd` into a newly created folder named `testfolder`.

Bash uses a variety of special varibles to refer to arguments, error codes and other relevant varibles. E.g.:

| special varible |                        meaning                         |
| :-------------: | :----------------------------------------------------: |
|      `$0`       |                     name of script                     |
|  `$1` to `$9`   |                `n`th arg of the script                 |
|      `$@`       |                     all arguments                      |
|      `$#`       |                number of arguments/args                |
|      `$?`       |    return code of previous command (`0` successful)    |
|      `$$`       | process identification number (pid) for current script |
|      `!!`       |        entire last command, including arguments        |
|      `$_`       |                last arg of last command                |
