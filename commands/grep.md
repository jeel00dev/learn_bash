## Basic Syntax

```bash
grep [OPTIONS]
```

- **PATTERN**: The text or regex to search for (quote if it contains spaces or special chars).
- **FILE**: The file(s) to search in (can be multiple or use wildcards like `*.log`).

### Simple Example

```bash
grep "error" app.log
```

- Searches for lines containing "error" in `app.log` and prints them.

## Common Options

### Case-Insensitive Search (-i)

- Ignores case differences.

```bash
grep -i "error" app.log
```

### Count Matches (-c)

- Counts the number of matching lines instead of printing them.

```bash
grep -c "error" app.log
```

### Recursive Search (-r)

- Searches recursively in directories.

```bash
grep -r "TODO" .  # Search inside current dir and subdirs
```

### Show Line Numbers (-n)

- Prefixes each match with its line number.

```bash
grep -n "error" app.log
```

### Match Whole Words (-w)

- Matches only complete words (not substrings).

```bash
grep -w "error" app.log
```

### Multiple Patterns (-e or -E)

- `-E` enables extended regex (e.g., for pipes `|` as OR).
- `-e` specifies patterns (can use multiple).

```bash
grep -E "error|warning|failed" log.txt
```

```bash
grep -e "error" -e "warning" log.txt
```

### Context Lines

- Show lines around matches for context.
  - `-A x`: x lines **after** the match.
  - `-B x`: x lines **before** the match.
  - `-C x`: x lines **above and below** the match.

```bash
grep -A 2 "error" app.log  # 2 lines after
```

```bash
grep -B 3 "error" app.log  # 3 lines before
```

```bash
grep -C 1 "error" app.log  # 1 line above and below
```

### Only Matching Part (-o)

- Prints only the exact matching text, not the whole line.

```bash
grep -o "error" app.log
```

```bash

grep -Rnw cpp -e 'create_win'
```

- -R → recursive (search inside all subdirectories)
- -n → show line number
- -w → match the whole word create_win
- cpp → directory to search in
- -e 'create_win' → pattern to search
