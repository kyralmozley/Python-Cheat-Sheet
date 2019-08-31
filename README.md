# Python-Cheat-Sheet

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

## Flow Control
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
>>> name = 'Kyra'
>>> name[0]
'K'

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

