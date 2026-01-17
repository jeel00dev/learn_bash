for things in (lists); do
(somthing)
done

read with prompt
read -p
read -r (row text no backslash can escape)

if [[arguements]]; then
(somthing)
else
(somthing)
fi

all the varibales are global by default
use (local) keyword to make it local.

define function
(function name)
{
(somthing)
}

In bash we pass arguements to the functions exactly like command-line arguements.

use return keyword for returning sucess code of the function.
ex.
foo(){
return 0
}

while [[condition]]; do
(somthing)
done

{a..f} = called brace expension

c style for loop
for (( init; condition; increment )); do
(command)
done
