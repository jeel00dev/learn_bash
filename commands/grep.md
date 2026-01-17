grep - global regular expression print

grep [OPTIONS] PATTERN FILE
grep "error" app.log

-i for caseinsensitive
-c for count matches

-r for recursive search
grep -r "TODO" . <!-- search inside current dir and sub dir. -->

-n show line numbers
-w match complete word

-e or -E for multiple patterns
grep -E "error|warning|failed" log.txt
grep -e "error" -e "warning" log.txt

-Ax x line after
-Bx x line before
-Cx x line above and below
-o only match that exact arguement
