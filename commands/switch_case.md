## Case Statement

### Syntax

```bash
case VARIABLE in
pattern1) commands ;;
pattern2) commands ;;
*) default commands ;;
esac
```

### Key Parts

- `case` → starts the switch-like statement
- `VARIABLE` → the value to test
- `pattern)` → what to match against
- `;;` → ends one case (very important!)
- `*` → default case (like else)
- `esac` → ends the case block (case reversed)

### Example

```bash
#!/usr/bin/env bash

day="Mon"

case $day in
Mon) echo "Start of the week" ;;
Fri) echo "Almost weekend" ;;
Sun) echo "Holiday!" ;;
*) echo "Just another day" ;;
esac
```

```bash
#!/usr/bin/env bash
case $char in
    [a-z])
        echo "Lowercase letter"
        ;;
    [A-Z])
        echo "Uppercase letter"
        ;;
    [0-9])
        echo "Digit"
        ;;
    *)
        echo "Something else"
        ;;
esac
```
