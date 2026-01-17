">" = redirect output(overwrite)
ex. echo "hello" > text.txt

">>" = redirect output(append)
ex. echo "hello" >> text.txt

type explains where a command comes from and what type of command it is.
ex. type -a ls

env = prints all the environment variables

help = for builtin tools && man for external tools

file = what kind of file somthing is by examining it's contents.

tr = translate
ex. echo &PATH | tr : '\n' this will translate : to new line(\n)

hash = caches the full path of executalbes after they are run once in that
terminal session.

echo $? = exit code of last command that we run

bash -n (filename) = check for any syntax errors in (filename)

${!i} = for for loops iteration through all the arguements
$0 is script or execute program name
$1 is first arg and so on.
$# number of arguements
$@ all arguements as individual words
$\* all arguements as single string
($$) =process id of the script
($?) = exit status

help test = all the requireed flags for conditional statements

: = is just null command

(()) = arithematic evaluation # check out help let
[[]] = advanced conditional test # check out help test
