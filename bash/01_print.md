# Bash docs

## Printing
```sh
#! /bin/bash

echo "Hello world."

printf "Hello world."
```

## Variables
```sh
first_name=one
last_name=two

echo "$first_name $last_name"

# lowercase
echo ${first_name^}
# uppercase
echo ${last_name^^}
```

Bash is cool. You do not have to any string interpulation. You can just write variable names
in strings without concatination.

**Note** Always leave no whitespace between the assignment operator, variable name and value.

`export user="shaddy"`

This would export the variable to the all other child process of the shell you are curently on.
You can make it permanent by putting  it in your .bashrc

## Default Variables
There are some predefined variables in bash.
1. $USER  : username
1. $HOSTNAME : hostname
1. $SHELL : current shell
1. $RANDOM : random number 0 to 32767.
1. $PWD : print working directory.

## Conditionals
Bash can also use conditionals.
```sh
one=1
if (( one == 1 ))
then 
  echo "The number is one"
elif (( $one == 2 ))
then 
  echo "The number is two"
else echo "The number is not one or two"
fi
```
The above is a basic bash conditional.
You can also do it like so

```sh
if [ $one -eq 1 ]
then ...
elif [ $one -eq 2 ]
then ...
fi
```
Basically you use the square brackets when you want to use the flags for checking and use the bracket for
when you want to use the symbols for conditional checking.
MOre examples

```sh
if [ $one -eq 1 -o $one -eq 2 ] # if is equal to one or two
if [ $one -eq 1] || [ $one -eq 2 ] # same as above but use double square braces when you wanna use symbols.
if (( $one == 1 ) || ($one == 1)) # same as above.
# AND
if [ $one -eq 1 -a $one -lt 2 ] # if both is true
if [ $one -eq 1 ] && [ $one -lt 2] # same as above
if ( ($one == 1) && ($one < 2) ) # same as above.
```

some useful tags
- -lte : less than or equal
- -lt: less than
- -gte: greater than or equal
- -gt: greather than
- -eq: equals
- -o: or
- -a:  And

## Read keyboard input.

To read keyboard input in bash use the **read** keywaord
```sh
#! /bin/bash

echo "what is your name?"
read uname
echo " Your ane is $uaneme"
```

## Loops

### while loop
```sh
iterator=0
while [ iterator != 10 ]
do
  iterator=$(( iterator+1 ))
  echo "iterator"
done
```

### For loop
```sh
for (( i=0; i<10; i++ ))
do 
  echo "The current is $i"
done
```
### For in loop
```sh
for i in {0..2}
do 
  echo $i
done
```

## Arrays
An array in bash is also quite simple. Implementation is like so
```sh
#! /bin/bash

arr1=() # an empty array

arr1[1]="one" # assigning index one of the arr to "one"

arr2=("one" "two" "two") # assigning data to the array
unset arr[2] # remove the 3rd index of the arr
echo "${#arr2[@]}" # length of the arr
echo "${!arr2[@]}" # indexes of the arr
echo "${arr2[@]}" # all items in the arr
echo "${arr2[1]}" # the first element of an arry

for (( i=0; i < ${#arr2[@]}; i++ )) # looping through the array.
do
  echo ${arr[$i]}
done
```

## Files
Working with files in bash is so really cool with the -f flag in the condition checker

```sh
echo "Enter filename to check!"
read filename
if [   -f "$filename" ]
then
  echo "The file exists!"
else 
  echo "The file does not exist!"
fi
```

```sh
echo "Enter the directory name."
read dirname
if [ -d "$dirname" ]
then echo "Directory exists!"
else echo "Directory does not exist."
fi
```


## Switch
```sh
val=3

case $val in
  3)
    echo "THe value is three";;
  4)
    echo "The value is four";;
  *)
    echo "The value is unknown";;
  esac

```
