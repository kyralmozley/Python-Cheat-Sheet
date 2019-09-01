# Python-Cheat-Sheet

# Table of Contents
1. [Basics](##basics)
2. [Flow Control](##flow-control)


## Basics

### Math Operators:

| Operator  | Operation |
| --------- | --------- |
| **        | Exponent  |
| %         | Modulo    |
| //        | Integer Division (floor)  |
| /         | Division  |
| *         | Multiplication  |
| -         | Subtraction  |
| +         | Addition |
| += | Addition Assigment |

As well as addition, can do augmented assignment for -, *, /, and %

### Comparison Operators:

| Operator  | Operation |
| --------- | --------- |
| ==  | Equal To |
| !=  | Not Equal To |
| <  | Less Than |
| >  | Greater Than |
| <=  | Less Than or Equal To |
| >=  | Greater than |


### Types
- Integer (int), whole numbers
- Floating Point Number (float), number with decimal
- Strings (strs), Surrounded by 'single quotes'
  - You can use + to concatenate strings together: 'hello ' + 'world' is 'hello world'
  - You can use * to perform string replication: 'hello' * 2 is 'hellohello'
- Boolean, True or False
  - Three boolean operators (and, or, and not)

  

### Variables
A variable is initalised first time a value is stored in it. A variable name:
- Can only be one word
- Can only use letters, numbers, and underscore 
- Cannot begin with a number
Official Python code style says underscores should be used, not camelcase (variable_name not variableName) 

### Basic Commands
- print()   #print value
  - print('cat', 'dog', 'mouse', sep=',') outputs cat,dog,mouse
- input()   #get user input
- len()     #get length 
- #comment
- str() / int() / float()     #convert to string, integer or floating point
- type()    # get type

### Strings

- Escape character, \, lets you put characters like ' in a string
  - \' , \" : Quotes
  - \t : tab
  - \n : newline
  - \\ : backslash
- If you place an r before string, it is a *raw string*, so ignores whitespace
- Multiline string ''' (note: can also use these for multiline comments)

Useful methods: 
- upper()     make uppercase
- lower()     make lowercase
- isupper()   is it all uppercase?
- islower()   is it all lowercase?
- isalpha()   is only letters? 
- isalnum()   is only letters and numbers?
- isdecimal() is only numeric?
- isspace()   is only space/tab/new lines?
- istitle()   do words begin with an uppercase letter followed by lowercase?
- startswith()
- endswith()
- join() , pass a list of strings, return a string, e.g.
```python
>>> ','.join(['cats', 'rats', 'bats'])
'cats, rats, bats'
>>> ' '.join(['cats', 'rats', 'bats'])
'cats rats bats'
```
- split() takes a string value and returns a list of strings, by default split on whitespace. 
- can justify text with rjust(), ljust(), center()
  - first argument says how much to justify by (e.g. 10)
  - second optional argument says what to fill the space with (e.g. '-' or '*')
- remove whitespace with strip(), lstrip(), rstrip()
  - can pass argument of which characters to strip

## Flow Control <a name="flow-control"></a>
- if statement:
    ...
  else:
    ...
- if statement:
    ...
  elif statement:
    ...
- while condition:
- for i in range(x):
  - range(12, 16) starts at 12, ends at 16 (12,13,14,15)
  - range(0, 10, 2) starts at 0, counts up in 2 till 10 (0,2,4,6,8)
- break / continue (only inside while or for loop)

To terminate a program: 
```python
import sys
sys.exit()
```
### Function 

```python
def func(name):
  print('hello ' + name)
```
Call with func('name'), can return a value. 

There is a value called *None* which represents absence of value (similar to null)
 
If you need to modify a global variable within a function, use *global* statement

### Exception Handling
Use try / except blocks
```python
def spam(divideBy):
    try:
        return 42 / divideBy
    except ZeroDivisionError:
        print("invalid")
```

Exceptions are raised with a *raise* statement.  
```python
if len(phone) != 11:
    raise Exception('input a correct phone number')
```

traceback.format_exec() returns a string for the call stack (print stack trace equiv.)

Assertions are used as santity checks. An assert statement:
```python
assert condition, 'string if false'
```

## Lists

A list is a value that contains multiple values in an ordered sequence. A list looks like spam=['cat', 'bat', 'rat'].
Like all good programming langauges, indexing starts at zero (spam[0] = 'cat').

Lists are a *mutable* data type - it can have values added, removed or changed.


Negative indecies refer from end of list, so [-1] gives you the last element, [-2] the 2nd to last and so on.

[1:4] gives you a *slice* with elements 1 upto (not including) 4.
[0:-1] gives you all elements except the last

- To concatenate a list together, simply add them: list1 + list2
- list.insert(index, value) inserts a value at that index to the list
- list.append(value)
- list.remove(value) removes the value from list, or ValueError if not in it
  - if duplicate exist, only removes first
- *del* allows you to delete values at an index
```python
>>> spam = ['cat', 'bat', 'rat']
>>> del spam[1]
>>> spam
['cat', 'rat']
```
- you can loop over elements in a list,e.g.  for i in spam:
- in or not in to test if value is/isn't in the list
- index(value) returns the index of value in list, or ValueError if not in the list
- you can multiple assign values of a list: 
```python
>>> cat = ['fat', 'black', 'hairy']
>>> size, colour, type = cat
```
Oh yeah, strings are technically a list of characters, so you can do things like 
```python
>>> name = 'Kyra'
>>> name[0]
'K'
```

### Sorting
The sort() method sorts in place. You cannot sort lists that have a mix of data types. It sorts using ASCII order (e.g. uppercase before lowercase).
- list.sort()
- list.sort(reverse=True) will sort in reverse order
- To sort in regular alphabetical order, list.sort(key=str.lower) which treats everything as if it was lowercase.

## Tuple 
Almost identical to a list, except: 
- Use parentheses instead of square brackets 
- They, unlike lists are *immutable*, their values cannot be modified, appended or removed 
Use tuples when you don't intend for sequence of values to change, because they are immutable python also optimises code making it slightly faster than a list.

If you only have one value in tuple, indicate by placing trailing comma: ('cat', )

To convert a tuple to a list: `tuple(list)`
To convert a list to a tuple: `list(tuple)`

## Dictionaries
A dictionary has a key-value pair. They are typed with braces
```python
>>> myDictionary = {
      'size':   'fat',
      'color':  'grey',
      'type':   'hairy'
   }
```
Unlike lists, they are unordered. Because they are not ordered, you cannot slice them like lists. To access the key: myDictionary['size'] would return 'fat'. 
- To return a list of values, myDictionary.values()
- To return a list of keys, myDictionary.keys() 
- To return a list of key,value pairs, myDicitionary.items()
- Also use in/not in to check if exists in myDicitionary.values() or .keys()
- Get method has a fallback: myDicitionary.get('cat', 0) - if cat is not a key, it will return 0

Can use pprint (pretty print) to print a dictionary nicely

## Pattern Matching and Regular Expressions
\d stands for a digit character. 

Matchig a telephone number format (XXX-XXX-XXXX) is simple, `\d{3}-\d{3}-\d{4}` 
Can use compile, search and group to get:
```python
>>> import re
>>> phoneNum = re.compile(r'\d{3}-\d{3}-\d{4}')
>>> mo = phoneNum.search('My phone number is 415-555-1234')
>>> mo.group()
'415-555-1234'
```
Here we import regex, create a regex object with compile, pass the string to search it - which returns a match object, and then call the group to return the matched text.

Adding parentheses will creates *groups*, so `(\d{3})-(\d{3}-\d{4})` has 2 groups, group(0) is the whole thing, group(1) is the first () and group(2) the second, and groups() will return a tuple. 

- can use a pipe (|) if you want to match multiple expressions
- can optionally match with (text)?, e.g. `r'Bat(wo)?man'`
- * matches 0 or more
- + matches one or more
- findall() returns the strings of every match, whislt search only returns the first instance
- ^ means must start with, whilst $ means must end with this pattern
- . is a wildcard that will match any character
  - .* matches everything (greedy mode) - get as much text as possible
  - .? nongreedy - matches shortest possible
- sub() subsitutes strings, the first argument is the string to replace, the second is the text
```python 
>>> nameRegex = re.compile(r'Agent (\w)\w*')
>>> nameRegex.sub(r'\1****', 'Agent Alice gave the document to Agent Bob')
'A**** gave the document to B****'
```

#### Character Classes

| Char class  | Represents |
| --------- | --------- |
| \d  | 0-9 |
| \D | Any char not 0-9 | 
| \w | Any letter, digit or _ |
| \W | Any char not a ltter, digit or _ |
| \s | Any space, tab, newline |
| \S | Any char not a space, tab, newline |

e.g/ The regular expression \d+\s\w+ will match text that has one or more digit (d+), followed by a whitespace char (s), followed by one or more letter/digit/underscore (w+)

## Reading and Writing Files

Paths
- To get avoid Windows paths using \ whilst Linux/macOS uses / you can use `os.path.join('usr', 'bin')` to make it system independent
- os.getcwd() gets the current working directory
- os.chdir('..') changes directory 
- os.makedirs(...) creates a folder (also creates any necessary intermediate to ensure a full path exists)
- os.path.abspath(path) returns a string of the absolute path
- os.path.ispath(path) will return True if argument is an absolute path
- os.path.relpath(path, start) will return a string of a relative path from start path to path
- os.path.dirname(path) will return a stirng of everything before the last slash
- os.path.exists(path) 
- os.path.isfile(path)
- os.path.isdir(path)
- os.path.getsize(path) returns size of file (in bytes)
- os.listdir(path) returns a list of filename strings for each file in path
- os.unlink(path) will delete the file at path
- os.rmdir(path) will delete folder at path

### File Reading/Writing
Read mode,r, allows you to read a file. Write mode, w, will overwrite the file, and append mode, a, will append text to the end of an existing file.
- To open a file, pass open() the string path of the file, returns file object. Optional second parameter ('r','w', or 'a')
- myfile.read() returns the string stored in the file
- myfile.readlines() will return a list of strings
- myfile.write('some text\n') 
- myfile.close()

### Shelve
You can save variables from Python to binary shelf files, allowing program to restore data
```python
>>> import shelve
>>> shelFile = shelve.open('mydata')
```
### ZipFile
Lets you unzip and work on files.
- exampleZip = zipfile.ZipFile('example.zip')
- namelist() returns list of strings for all files/folders in Zip file
- getinfo() will get info about that particular file (file_size, compress_size)
- close()
- extract('file.txt')
- extractall()
- To create a Zip file:
```python
>>> import zipfile
>>> newZip = zipfile.ZipFile('new.zip', 'w')
>>> newZip.write('spam.txt', compress_type=zipfile.ZIP_DEFLATED)
>>> newZip.close()
```

## Miscellaneous
- pyperclip.copy(text) copies value to clipboard, whilst pyperclip.paste() pastes
