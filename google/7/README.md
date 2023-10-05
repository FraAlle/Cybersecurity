## Python

In python, "\w" search for any alphanumeric character, "+" match for any occurensy of the specified character.
For example: "b\wa+b" search for anything that start with b and has "ab" in the string.
`include re` is needed when using regular expressions.
Seeking emails using notation
`user@email1.com` -> `\w+@\w+\.\w+` so in python we use a function like this `re.findall("\w+@\w+\.\w+",file_log)`