# Bash Scripting Essentials

## For Loop (Iterating Over Lists)

Syntax:

```bash
for thing in (list); do
    (something)
done
```

- **Purpose**: Iterates over items in a list (e.g., files, words).
- **Example**:
  ```bash
  for file in *.txt; do
      echo "Processing $file"
  done
  ```

## Read Command (Input Handling)

- **Basic Read with Prompt**:

  ```bash
  read -p "Enter your name: " name
  ```

  - Displays a prompt and reads input into a variable.

- **Read Raw Text (No Backslash Escape)**:

  ```bash
  read -r line
  ```

  - Reads input without interpreting backslashes (preserves raw text).

## If-Else Conditional

Syntax:

```bash
if [[ arguments ]]; then
    (something)
else
    (something)
fi
```

- **Purpose**: Tests conditions and executes code accordingly.
- **Example**:
  ```bash
  if [[ $age -gt 18 ]]; then
      echo "Adult"
  else
      echo "Minor"
  fi
  ```
- **Note**: Use `[[ ]]` for modern string/pattern tests; `[ ]` for POSIX compatibility.

## Variable Scope

- **Default Behavior**: All variables are global by default.
- **Making Local**: Use the `local` keyword inside functions.
  ```bash
  local var="value"
  ```

## Defining Functions

Syntax:

```bash
function_name() {
    (something)
}
```

- **Passing Arguments**: Arguments are passed like command-line args (`$1`, `$2`, etc.).
- **Returning Status**: Use `return` for exit codes (0 for success).
- **Example**:
  ```bash
  foo() {
      echo "Arg1: $1"
      return 0
  }
  foo "hello"
  ```

## While Loop

Syntax:

```bash
while [[ condition ]]; do
    (something)
done
```

- **Purpose**: Repeats while the condition is true.
- **Example**:
  ```bash
  count=1
  while [[ $count -le 5 ]]; do
      echo $count
      ((count++))
  done
  ```

## Brace Expansion

- **Syntax**: `{a..f}`
- **Purpose**: Generates sequences (e.g., letters, numbers).
- **Called**: Brace expansion.
- **Example**:
  ```bash
  echo {a..f}  # Outputs: a b c d e f
  ```

## C-Style For Loop

Syntax:

```bash
for (( init; condition; increment )); do
    (command)
done
```

- **Purpose**: Numeric loops, similar to C.
- **Example**:
  ```bash
  for (( i=1; i<=5; i++ )); do
      echo $i
  done
  ```
