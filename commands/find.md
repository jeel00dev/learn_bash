# Mastering the `find` Command in Linux

The `find` command is a powerful tool for searching files and directories in Linux. It's flexible and essential for users and developers.

## Basic Syntax

**`find WHERE_TO_LOOK CONDITIONS WHAT_TO_DO`**

- **WHERE_TO_LOOK**: Starting directory (e.g., `.` for current, `/` for root).
- **CONDITIONS**: Filters like name, type, size.
- **WHAT_TO_DO**: Actions like print or delete (defaults to print if omitted).

`find` searches recursively from the starting point.

## Common Examples

### Exact Name Match

```bash
find . -name file.txt  # exact name
```

- Searches for files named exactly `file.txt`.
- Case-sensitive.

### Case-Insensitive Name Match

```bash
find . -iname file.txt  # case-insensitive
```

- Ignores case (matches `File.txt`, etc.).

### Only Files

```bash
find . -type f  # only files
```

- Finds regular files (not directories or links).

### Only Directories

```bash
find . -type d  # only directories
```

- Finds directories.

## Advanced Usage

- **Chaining Conditions**: `find . -type f -name "*.txt"`.
- **Actions**: `-exec rm {} \;` to delete matches.
- **Limit Depth**: `-maxdepth 1` for current directory only.
- **Size**: `-size +10M` for files >10MB.
- **Time**: `-mtime -7` for modified in last 7 days.
