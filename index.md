## C Programming Language

### Basics

Basic 'hello world' script:

```c
#include <stdio.h>

int main(void)
{
    printf("hello, world");
}
```

After writing the above save it as [filename].c and then in the terminal compile it with:

```shell
make [filename]
```

Note that the .c file extension is not required for the make command.

Code needs to be compiled after every change.

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // This is a comment
    string answer = get_string("What's your name? ");
    printf("hello, %s\\\\n", answer);
}
```

**\n** - new line (escape character)

When using the '=' sign, the right side of the sign is executed first, then the left.

### Header Files

For example `#include <stdio.h>` calls the header file standard input output so we can use get_string.

### Troubleshooting

For this CS50 class you can use...

-   help50
-   style50
-   check50

Just write help50 (etc.) followed by the command you wish to run.

### Comments

Start a line with '//' for a comment.

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    //Get numbers from user
    int x = get_int("x: ");
    int y = get_int("y: ");

    //Divide x by y
    float z = (float)x / (float)y;
    printf("%f\\\\n", z);
}
```

### Increasing a variable

For example, if you had an int variable of 'counter', you could increase it by 1 as follows:

```c
counter = counter + 1;
```

or more neatly:

```c
counter += 1;
```

Or even shorter:

```c
counter++;
```

### IF / ELSE Statements

```c
if (x < y)
{
    // True condition here, followed by ;
}
else
{
    // False condition here, followed by ;
}
```

```c
if (x < y)
{
    printf("x is less than y\\\\n);
}
else if (x > y)
{
    printf("x is greater than y\\\\n);
}
else
//Could have written 'else if (x == y)' above but 'else' is cleaner as there are no other possibilities
{
    printf("x is equal to y\\\\n);
}
```

### Full example:

```c
// Conditions and relational operators

#include <cs50.h>
#include <stdio.h>

int main(void)
{
        // Prompt user for x
        int x = get_int("x: ");

        // Prompt user for y
        int y = get_int("y: ");

        // Compare x and y
        if (x < y)
        {
            printf("x is less than y\\\\n");
        }
        else if (x > y)
        {
            printf("x is greater than y\\\\n");
        }
        else
        {
            printf("x is equal to y\\\\n");
        }
}
```

### IMPORTANT

In C you have to use single quotes when referencing single characters, e.g.

```c
if (c == 'y' || c == 'Y')
```

C uses two vertical bars for 'or', as above

In ‘points.c’ - see IDE - the code was comparing points </> 2, but it was better to make a variable called ‘mine’ and set it to 2. Easier to change at a later date.

### Constants

In points.c the variable ‘mine’ is set to be a constant, which means it cannot be changed accidentally later.

Capitalisation is usually used to alert you that a variable is a constant, though the capitalisation itself has no effect in code.

‘Or’ is expressed by two vertical bars - ||

‘And’ is expressed by two ampersands - &&

### Loops

```c
while (true)
{
    printf("meow\\n");
}
```

‘true’ in the above example basically means forever

```c
int i = 0;
while (i < 3)
{
    printf("meow\\n");
    i++;
}

// OR

for (int i = 0; i < 3; i++)
{
    printf("meow\\n");
}

// Advantage of the first one is that the variable 'i' was declared outside of the loop, so is usable in other place in code.
```

The above example would print meow three times.

See meowloop.c for notes on the order in which functions need to be called.

Nice bit of code to work out a discount:

```c
#include <stdio.h>
#include <cs50.h>

float discount(float price, int percentage);

int main(void)
{
    float regular = get_float("Regular Price: ");
    int percent_off = get_int("Percent Off: ");
    float sale = discount(regular, percent_off);
    printf("Sale Price: %.2f\\n", sale);
}

float discount(float price, int percentage)
{
    return price * (100 - percentage) / 100;
}
```

Nic way to get the user to input a positive value for a variable is to use a loop that they cannot ‘break out of’ until a positive integer is entered, for example in this code:

```c
#include <stdio.h>
#include <cs50.h>

int main (void)
{
    int n;
    do
    {
        n = get_int("Width: ");
    }
    while (n < 1);

    for (int i = 0; i < n; i++)
    {
        printf("?");
    }
    printf("\\n");
}
```

The ‘do/while’ loop at the start is key.

### Changing ints to floats etc

You can turn an int, say ‘y’, into a float as follows:

```c
(float) y
```

As simple as that.e
