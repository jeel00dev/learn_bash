## Standard File Descriptors Table

| Number | Name   | Meaning                                              |
| ------ | ------ | ---------------------------------------------------- |
| `0`    | stdin  | Input (e.g., from keyboard or piped data)            |
| `1`    | stdout | Normal output (e.g., successful command results)     |
| `2`    | stderr | Error output (e.g., diagnostic messages or failures) |

- **Key Idea**: These are like channels. By default, stdin reads from the terminal, stdout/stderr write to the terminal. You can redirect them to files, pipes, or other streams for automation and error handling.

## How to Use Them (Redirection Basics)

Redirection allows you to control where input comes from and where output goes. Use symbols like `>`, `<`, `|`, and `&` in commands.

### 1. Redirecting stdout (1)

- **To a file** (overwrites file):
  ```bash
  ls > output.txt  # stdout to file
  ```
- **Append to a file**:
  ```bash
  echo "Hello" >> output.txt  # Append stdout
  ```

### 2. Redirecting stderr (2)

- **To a file**:
  ```bash
  ls non_existent_file 2> errors.txt  # stderr to file
  ```
- **Append**:
  ```bash
  command 2>> errors.txt
  ```
- **Redirect stderr to stdout** (combine errors with normal output):
  ```bash
  command 2>&1 > combined.txt  # stderr to stdout, then to stdout file
  ```

### 3. Redirecting stdin (0)

- **From a file**:
  ```bash
  grep "error" < app.log  # Input from file
  ```
- **From heredoc** (inline input):

  ```bash
  cat << EOF
  Line 1
  Line 2
  EOF
  ```

  ```bash
  cat << EOF >> redirect.txt
  Line 1
  Line 2
  EOF
  ```

### 4. Piping (Combining Commands)

- Pipe stdout of one command to stdin of another:
  ```bash
  ls | grep ".txt"  # ls output -> grep input
  ```

### 5. Advanced: Redirect Both stdout and stderr

- To the same file:
  ```bash
  command > output.txt 2>&1
  ```
- Discard output (to /dev/null):
  ```bash
  command > /dev/null 2>&1  # Silence everything
  ```

### 6. In Scripts

- Check for errors:
  ```bash
  if command > output.txt 2> errors.txt; then
      echo "Success"
  else
      cat errors.txt
  fi
  ```
