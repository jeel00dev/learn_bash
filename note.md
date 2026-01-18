# Bash Quick Notes

## Redirections

- `ls -li`: For inode Numbers

- `>`: Redirect output (overwrite)  
  Example:

  ```bash
  echo "hello" > text.txt
  ```

- `>>`: Redirect output (append)  
  Example:

  ```bash
  echo "hello" >> text.txt
  ```

- `>>>`: Redirect string output
  | Operator | Input source | Typical use |
  | -------- | --------------- | ----------------- |
  | `<` | file | read file |
  | `<<` | multi-line text | configs, scripts |
  | `<<<` | single string | parsing variables |

```
  < file ───────▶ stdin
  << text block ─▶ stdin
  <<< string ─────▶ stdin
```

## Commands

- `type`: Explains where a command comes from and what type of command it is.  
  Example:

  ```bash
  type -a ls
  ```

- `env`: Prints all the environment variables.

- `help`: For builtin tools (use `man` for external tools).

- `file`: Determines what kind of file something is by examining its contents.

- `tr`: Translate characters.  
  Example:

  ```bash
  echo $PATH | tr : '\n'
  ```

  This translates `:` to a new line (`\n`).

- `hash`: Caches the full path of executables after they are run once in that terminal session.

- `echo $?`: Displays the exit code of the last command that was run.

- `bash -n <filename>`: Checks for any syntax errors in `<filename>`.

## Variables and Parameters

- `${!i}`: For loop iteration through all the arguments.

- `$0`: Script or executable program name.

- `$1`: First argument (and so on for `$2`, etc.).

- `$#`: Number of arguments.

- `$@`: All arguments as individual words.

- `$*`: All arguments as a single string.

- `$$`: Process ID of the script.

- `$?`: Exit status.

## Miscellaneous

- `help test`: Shows all the required flags for conditional statements.

- `:`: Null command.

- `;;`: For breaking out (similar to C++ `break;`).

- `(())`: Arithmetic evaluation (check `help let`).

- `[[ ]]`: Advanced conditional test (check `help test`).
