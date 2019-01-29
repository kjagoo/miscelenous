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

