## Python

In python, "\w" search for any alphanumeric character, "+" match for any occurensy of the specified character.
For example: "b\wa+b" search for anything that start with b and has "ab" in the string.
`include re` is needed when using regular expressions.
Seeking emails using notation
`user@email1.com` -> `\w+@\w+\.\w+` so in python we use a function like this `re.findall("\w+@\w+\.\w+",file_log)`
`re.findall("\w", "h32rb17")` return the string but in char characters
*   . matches to all characters, including symbols
*   \d matches to all single digits `[0-9]`
*   \s matches to all single spaces 
*   \. matches to the period character
*   `\d{2}` search for all numbers with 2 digits
*   `\d{1,3}` search for 1 to 3 numbers

# Read files
`with open ("text.txt","r") as file: ` with handle errors and once finished with the file, it automatically close the file.
*   `.read()` convert files into strings
*   if u want to append strings to a text u must use the `a` in the open option and than for write into a file, u just need to use `.write(string)`.

# Split

converts a string into a list based on a specified character that's passed into `.split()`.

# Join

convert a list into a string