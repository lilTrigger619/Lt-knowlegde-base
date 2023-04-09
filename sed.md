
# 	Sed command

the sed command is used to replace strings from the standard input of another command or a file

## Usage
`sed "s/\<old string\>/new string to be replaced with/ filename"`
The above will replace the any instance of the exact word provided before after the
first delimeter with the string before the last delimeter.

But this will not be written to the file you are trying to replace.

To do that you would have to use the **-i** flag
`sed s/a/b/ -i testfile.txt`
The above will replace any instance of a with b and write to the file.

The first character after the **s** will be the delimeter for the rest of the command.
