---
tags:
Date /Time: "{date} {time}"
title:
draft: true
---
tr DOESNT ENCODE OR DECODE OR ENCRYPT

Unlike commands like sed or awk, tr cannot read files directly. You must feed data into it using a pipe (|) or a redirect (<).
Bash

```
# This WORKS:
cat file.txt | tr 'a' 'b'

# This DOES NOT work:
tr 'a' 'b' file.txt

```
4 Common Ways to Use tr
1. Changing Case (Uppercase ⇄ Lowercase)

This is the most common use case for tr. You define a set of characters to find, and a set to replace them with.

```
    To Uppercase:
    Bash

echo "hello world" | tr 'a-z' 'A-Z'

    Output: HELLO WORLD

To Lowercase (using built-in character classes):
Bash

    echo "HELLO WORLD" | tr '[:upper:]' '[:lower:]'

        Output: hello world

```
2. Deleting Specific Characters (-d flag)

If you want to completely strip certain characters out of a string (like punctuation, numbers, or specific letters), use the -d flag.

```
    Remove all spaces:
    Bash

echo "1 2 3 4 5" | tr -d ' '

    Output: 12345

Remove parentheses from a phone number:
Bash

    echo "(555) 123-4567" | tr -d '()'

        Output: 555 123-4567

```
3. "Squeezing" Repetitions (-s flag)

If you have data with annoying repeated characters (like multiple spaces or multiple blank lines) and you want to collapse them into a single character, use -s.
```
    Squeeze multiple spaces into one:
    Bash

    echo "Too    many        spaces" | tr -s ' '

        Output: Too many spaces

```
4. Complementing/Inverting the Match (-c flag)

The -c flag tells tr to operate on the opposite of what you selected. It means "everything except these characters."

```
    Delete everything EXCEPT digits:
    Bash

    echo "My phone number is 555-1234!" | tr -cd '[:digit:]'

        Output: 5551234
        (Note: We combined -c and -d to delete everything that wasn't a number).

```
Handy Reference Table
Character Class	What it Matches
[:alnum:]	All letters and digits
[:alpha:]	All letters
[:digit:]	All digits (0-9)
[:space:]	All whitespace (spaces, tabs, newlines)
[:lower:] / [:upper:]	Lowercase / Uppercase letters
