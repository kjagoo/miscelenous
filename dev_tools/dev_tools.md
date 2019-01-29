## DEv TOOLS COMMANDS

### xargs
 >This is a command line utility for building an execution pipeline from standard input.
 Using xargs allows tools like `echo` and `rm` and `mkdir` to accept standard input as arguments


1. By default xargs reads items from standard input as separated by blanks and executes a command once for each argument.
e.g 
``` 
   echo 'one two three' | xargs mkdir
   ls
   one two three 
```
``` 
   echo 'one two three' | xargs rm
   ls
   one two three 
```


2. This uses `find` to search for files or directories and then uses `xargs` to operate on the results
`Find` and `xargs` can be used together to operate on files that match certain attributes.
e.g 
```
find ./foo -type f -name "*.txt" | xargs rm
``` 

3. Print commands that are executed using `-t`
```
echo 'one two three' | xargs -t rm
```

4. View command and prompt for execution
```
echo 'one two three' | xargs -p  mkdir
```

3. Run multiple commands using `-I`
```
cat foo.txt
one
two
three

cat foo.txt | xargs -I % sh -c 'echo %; mkdir %'
one 
two
three

ls 
one two three
```


### cat command
It has three related functions with regard to text files: displaying them, combining copies of them and creating new ones.
1. Create file
` cat > file` 
- typing after this commands writes into the file. pres ctr+d to exit.
2. Read file contents
` cat foo.txt `
3. Copy contents of one file to another
`cat file1 > file2`
4. Concatenate files
`cat file1 file2 file3` or `cat file1 file2 file3 > file4`

### expr
expr is a command line Unix utility which evaluates an expression and outputs the corresponding value. expr evaluates integer or string expressions, including pattern matching regular expressions.
uses include searching for a substring in a string, finding its index, as well as other things like performing comparisons and arithmetic operations.
```
$ expr 5 - 3
2

$ expr 5 \* 3
15

$ y=10
$ y=`expr $y + 1`
$ echo $y
11

expr length [string]
$ expr length joshua
6

expr substr [string] [pos] [length]
$ expr substr joshua 4 2
ua

$ export a=10
$ export b=0
$ expr $a \| $b
10

```

### sed  
- (stream editor) is a Unix utility that parses and transforms text, using a simple, compact programming language. Used in text manipultion.
1. substitute strings
```
$ echo "welcome to joshua" | sed 's/to/Mr/' 
welcome Mr joshua
```

2. substitute strings in files
```
cat > testfile.txt
There are four cars parked outside

sed 's/car/buses/' ./testfile.txt 
There are four busess parked outside
```

3.multiple commands
```
$ sed -e '
 
> s/This/That/
 
> s/test/another test/' myfile
``` 

4. run sed commands from file
```
$ cat mycommands
 
s/This/That/
 
s/test/another test/

$ sed -f mycommands myfile
```

sed flags 
- g, replace all occurrences.
- A number, the occurrence number for the new text that you want to substitute.
- p, print the original content.
- w file: means write the results to a file.

limiting sed to:
1. a range of lines
```sed '2s/test/another test/' myfile ```
subtitutes on the second line
```sed '2,3s/test/another test/' myfile ```
subtitutes from the 2nd to 3rd line
```sed '2,$s/test/another test/' myfile```
from the 2nd line to the end of the file

2. a pattern that matches a specific line
``` $ sed '/likegeeks/s/bash/csh/' /etc/passwd```

delete lines with sed
``` $ sed '2d' myfile```
- deletes the second line from the stream, not the original file
```$ sed '2,3d' myfile```
- deleting in range
``` $ sed '/test 1/d' myfile```
- deleting if match
```$ sed '/second/,/fourth/d' myfile```
- deleting using 2 patterns. deleting from the second line to the fouth line

Insert and Append Text
You can insert or append text lines using the following flags: 
- (i) flag - insert
- (a) flag.- append
- (c) flag.- modify
- (y) flag - transform characters

(i) flag
```
echo "Another test" | sed 'i\First test '
Another test
First test
```
inserting after `another test`

```
sed '2i\This is the inserted line.' myfile
```
inserts the sentence on the second line. hence the previous 2nd line moves one level down

(a) flag
```
$ sed '2a\This is the appended line.' myfile
```
this appends the sentence on the second line, hence becomes the new 3rd line and other lines below are moved one level lower

(c) flag - modifying lines
```
$ sed '3c\This is a modified line.' myfile
```
this replaces the 3rd line 

(y) flag - transform characters
```
$ sed 'y/123/567/' myfile
```
transforms the occurence of numbers `1,2,3` to `5,6,7`

print line numbers `$ sed '=' myfile`


## awk
>AWK is a programming language designed for text processing and typically used as a data extraction and reporting tool. 
AWK - the (very old) original from AT&T
NAWK - A newer, improved version from AT&T
GAWK - The Free Software foundation's version
Abilities of AWK
- Define variables.
- Use string and arithmetic operators.
- Use control flow and loops.
- Generate formatted reports.

Awk can take the following options:

-F fs     To specify a file separator.

-f file     To specify a file that contains awk script.

-v var=value     To declare a variable.

Define variables
- $0 for the whole line.
- $1 for the first field.
- $2 for the second field.
- $n for the nth field.

```$ awk '{print $1}' myfile`` 
prints the first field/ word of the line

```
BEGIN {
 
print "Users and thier corresponding home"
 
print " UserName \t HomePath"
 
print "___________ \t __________"
 
FS=":"
 
}
 
{
 
print $1 "  \t  " $6
 
}
 
END {
 
print "The end"
 
}
```