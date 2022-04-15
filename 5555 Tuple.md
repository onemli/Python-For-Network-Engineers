Python has several data types:

- Numbers

- Strings

- Lists

- Dictionaries

- Tuples

- Sets

- Boolean




These data types, in turn, can be classified by several criteria:

- mutable (lists, dictionaries and sets)

- immutable (integers, strings and tuples)

- ordered (lists, tuples, strings and dictionaries)

- unordered (sets)

<br>
<br>

# 2.1   Numbers

With numbers it is possible to perform various mathematical operations.

```python
print(1+2)
print(1.0+2)
print(10-4)
print(2**3)
```

> **Output:**

> ```python
> 3
> 3.0
> 6
> 8
> ```

<br>
<br>
Division int and float:

```python
print(10/3)
print(10/3.0)
```

> **Output:**

> ```python
> 3.3333333333333335
> 3.3333333333333335
> ```

<br>
<br>


The round() function - round a number to a given precision in decimal digits:

```python
print(round(10/3.0, 2))
print(round(10/3.0, 4))
```

> **Output:**

> ```python
> 3.33
> 3.3333
> ```

<br>
<br>


Remainder of division:

```python
print(10 % 3)
```

> **Output:**

> ```python
> 1
> ```

<br>
<br>


Comparison operators:

```python
print(10 > 3.0)
print(10 < 3)
print(10 == 3)
print(10 == 10)
print(10 <= 10)
print(10.0 == 10)
```

> **Output:**

> ```python
> True
> False
> False
> True
> True
> True
> ```

<br>
<br>


The `int()` function allows converting to `int` type. The second argument can specify number system:

```python
founded = '1984'
print(int(founded))
```

> **Output:**

> ```python
> 1984
> ```

<br>
<br>


If you specify that string should be read as a binary number, the result is:

```python
a = '11'
print(int(a, 2))
```

> **Output:**

> ```python
> 3
> ```

<br>
<br>


Convert to int from float:

```python
print(int(3.333))


print(int(3.9))
```

> **Output:**

> ```python
> 3
> 3
> ```

<br>
<br>


The bin() function produces a binary representation of a number (note that the result is a string):

```python
print(bin(8))

print(bin(255))
```

> **Output:**

> ```python
> 0b1000
> 0b11111111
> ```

<br>
<br>


Similarly, function hex() produces a hexadecimal value:

```python
print(hex(10))
```

> **Output:**

> ```python
> 0xa
> ```

<br>
<br>


And, of course, you can do several changes at the same time:

```python
print(int('ff', 16))

print(bin(int('ff', 16)))
```

> **Output:**

> ```python
> 255
> 0b11111111
> ```


<br>
<br>

#  2.2   Strings

 String in Python is:

- sequence of characters enclosed in quotes
- immutable ordered data type

Examples of strings:

```python
motd1 = 'You are Connected To RTR1'
motd2 = "You are Connected To RTR1"

tunnel = """interface Tunnel0
ip address 10.10.10.1 
255.255.255.0
ip mtu 1416 
ip ospf hello-interval 5
tunnel source FastEthernet1/0
tunnel protection ipsec profile DMVPN
"""
```

<br>
<br>


Strings can be summed. Then they merge into one string:

```python
intf = 'interface'
gi = 'GigabitEthernet'

print (intf + ' ' +gi + ' 0/0')
```

> **Output:**

> ```python
> interface GigabitEthernet 0/0
> ```

<br>
<br>


You can multiply a string by a number. In this case, string repeats specified number of times:

```python
print (50*'-')
```

> **Output:**

> ```python
> --------------------------------------------------
> ```
<br>
<br>


The fact that strings are an ordered data type allows to refer to characters in a string by a number starting from zero:

```py
interface = 'interface GigabitEthernet1/0'

print(interface[10])
```

> **Output:**

> ```python
> G
> ```

<br>
<br>


All characters in a string are numbered from zero. But if you need to refer to a character from the end, you can specify negative values (this time with 1).

```python
print(interface[1])
print(interface[-1])
```

> **Output:**

> ```
> n
> 0
> ```

<br>
<br>


In addition to referring to a specific character you can make string slices by specifying a number range. Slicing starts with first number (included) and ends at second number (excluded):

```python
print(interface[0:9])
print(interface[10:25])
```

> **Output:**

> ```python
> interface
> GigabitEthernet
> ```

<br>
<br>


If no second number is specified, slice is until the end of string:

```python
print(interface[10:])
```

> **Output:**

> ```python
> GigabitEthernet1/0
> ```

<br>
<br>


Slice last three character of string:

```python
print(interface[-3:])
```

> **Output:**

> ```python
> 1/0
> ```

<br>
<br>


You can also specify a step in slice. For example, you can get odd numbers:

```python
numbers = '0123456789'

print(numbers[1::2])
```

> **Output:**

> ```python
> 13579
> ```

<br>
<br>


Or you can get all even numbers of string numbers:

```python
print(numbers[::2])
```

> **Output:**

> ```python
> 02468
> ```

<br>
<br>


Slices can also be used to get a string in reverse order:

```python
numbers = '0123456789'
print(numbers[::-1])
```

> **Output:**

> ```python
> 9876543210
> ```

<br>
<br>


The `len()` function allows you to get number of characters in a string:

```python
interface = 'interface GigabitEthernet1/0'
print(len(interface))
```

> **Output:**

> ```python
> 28
> ```


<br>
<br>

## 2.2.1 String Methods



When automating, very often it will be necessary to work with strings, since config file, command output and commands sent - are strings. Knowledge of various methods (actions) that can be applied to strings helps to work with them more efficiently.

 Strings are immutable data type, so all methods that convert string returns a new string and the original string remains unchanged.

<br>
<br>

### upper(), lower(), swapcase(), capitalize(), title() Methods



Methods `upper()`, `lower()`, `swapcase()`, `capitalize()`, `title()` perform string case conversion:

```python
interface = 'interface GigabitEthernet1/0'

print(interface.lower())
print(interface.upper())
print(interface.swapcase())
print(interface.capitalize())
print(interface.title())
```

> **Output:**

> ```python
> interface gigabitethernet1/0
> INTERFACE GIGABITETHERNET1/0
> INTERFACE gIGABITeTHERNET1/0
> Interface gigabitethernet1/0
> Interface Gigabitethernet1/0
> ```

<br>
<br>


It is very important to pay attention to the fact that methods often return the converted string. And, therefore, we must not forget to assign it to some variable (you can use the same).

```python
interface = interface.upper()
print(interface)
```

> **Output:**

> ```python
> INTERFACE GIGABITETHERNET1/0
> ```


<br>
<br>

### count() Method

Method count() used to count how many times a character or substring occurs in a string:

```python
motd = 'Welcome welcome Welcome welcome Welcome'

print(motd.count('Welcome'))
print(motd.count('come'))
```

> **Output:**

> ```python
> 3
> 5
> ```



<br>
<br>

### find() Method

 

You can pass a substring or character to find() and it will return the lowest index where first character of the substring is (for the first match):

```python
interface = 'interface GigabitEthernet1/0'

print(interface.find('Gigabit'))
print(interface[interface.find('Gigabit'):])
```

> **Output:**

> ```python
> 10
> GigabitEthernet1/0
> ```

> ***Info:***
>
> *If no match is found, find() method returns -1.*


<br>
<br>

### startswith() and endswith() Methods



Checking if a string starts or ends with certain symbols (methods startswith(), endswith()):

```python
interface = 'GigabitEthernet1/0'

print(interface.startswith('Gigabit'))
print(interface.startswith('Fast'))
print(interface.endswith('1/0'))
print(interface.endswith('ethernet'))
```

> **Output:**

> ```python
> True
> False
> True
> False
> ```



<br>
<br>

### replace() Method

 

Replacing a sequence of characters in a string with another sequence (method replace):

```python
interface = 'GigabitEthernet1/0'

print(interface.replace('Gigabit', 'Fast'))
```

> **Output:**

> ```python
> FastEthernet1/0
> ```



<br>
<br>

### strip() Method

 

Often when a file is processed, the file is opened line by line. But at the end of each line, there are usually some special characters (and may be at the beginning). For example, new line character.

 

To get rid of them, it is very convenient to use method strip():

```python
interface = '\n\tinterface GigabitEthernet1/0\n'

print(interface)
print(50*'-')
print(interface.strip())
```

> **Output:**

> ```python
> interface GigabitEthernet1/0
> --
> interface GigabitEthernet1/0
> ```

<br>
<br>



By default, strip method removes blank characters. This character set includes: `\t`, `\n`, `\r`, `\f`, `\v`

Method `strip()` can be passed as an argument of any characters. Then at the beginning and at the end of the line all characters that were specified in the line will be removed:

```python
ad_metric = '[110/1045]'

print(ad_metric.strip('[]'))
```

> **Output:**

> ```python
> 110/1045
> ```


<br>
<br>


Method `strip()` removes special characters at the beginning and at the end of the line. If you want to remove characters only on the left or only on the right, you can use `lstrip()` and `rstrip()`.


<br>
<br>

### split() Method

Method `split()` splits the string using a symbol (or symbols) as separator and returns a list of strings:

```python
config = 'switchport trunk allowed vlan 10,20,30,100-200'
commands = config.split()

print(commands_list)
```

> **Output**

> ```python
> ['switchport', 'trunk', 'allowed', 'vlan', '10,20,30,100-200']
> ```

<br>
<br>



In example above, `config.split` splits the string by spaces and returns a list of strings. The list is saved to commands variable.

By default, separator is a space symbol (spaces, tabs, new line), but you can specify any separator in parentheses:

```python
vlans = commands[-1].split(',')

print(vlans)
```

> **Output:**

> ```python
> ['10', '20', '30', '100-200']
> ```

<br>
<br>



In commands list, the last element is a string with vlans, so the index -1 is used. Then string is split into parts using split `commands[-1].split(',')`. Since separator is a comma, this list is received `['10','20','30','100-200']`.

 

A useful feature of split method with default separator is that the string is not only split into a list of strings by whitespace characters, but the whitespace characters are also removed at the beginning and at the end of the line:

```python
config = ' switchport trunk allowed vlan 10,20,30,100-200\n\n'

print(config.split())
```

> **Output:**

> ```python
> ['switchport', 'trunk', 'allowed', 'vlan', '10,20,30,100-200']
> ```

<br>
<br>



Method split has another good feature: by default, method splits a string not by one whitespace character, but by any number. For example, this will be very useful when processing show commands:

```python
sh_ip_int_br = "FastEthernet0/0    15.0.15.1  YES manual up     up"

print(sh_ip_int_br.split())
```

> **Output:**

> ```python
> ['FastEthernet0/0', '15.0.15.1', 'YES', 'manual', 'up', 'up']
> ```

<br>
<br>




And this is the same string when one space is used as the separator:

```python
sh_ip_int_br = "FastEthernet0/0    15.0.15.1  YES manual up     up"

print(sh_ip_int_br.split(' '))
```

> **Output:**

> ```python
> ['FastEthernet0/0', '', '', '', '', '', '', '15.0.15.1', '', '', '', 'YES', 'manual', 'up', '', '', '', '', '', '', '', '', 'up']
> ```

<br>
<br>

##  2.3.1 String Formatting

 

When working with strings, there are often situations where different data needs to be substituted in string template. This can be done by combining string parts and data, but Python has a more convenient way - strings formatting.

 

String formatting can help, for example, in such situations:

- need to set values to a string by a certain template
- need to format output by columns
- need to convert numbers to binary format



There are several options for string formatting:

- with operator `%` — older option
- method format — relatively new option
- `f-string` — new option that appeared in Python 3.6
- Although format is recommended, string formatting can often be found through `%`.


<br>
<br>

### format() Method

Example of format method use:

```python
intf = "interface FastEthernet0/{}".format('1')

print(intf)
```

> **Output:**

> ```python
> interface FastEthernet0/1
> ```

<br>
<br>


A special symbol `{}` indicates that the value that is passed to format method is placed here. Each pair of curly braces represents one place for the substitution.

 

Values that are placed in curly braces may be of different types. For example, it can be a string, number or list:

```python
print('{}'.format('10.1.1.1'))
print('{}'.format(100))
print('{}'.format([10, 1, 1,1]))
```

> **Output:**

> ```python
> 10.1.1.1
> 100
> [10, 1, 1, 1]
> ```

<br>
<br>


You can align result in columns by formatting strings. In string formatting, you can specify how many characters are selected for the data. If number of characters in the data is less than number of characters selected, the missing characters are filled with blanks.

 

For example, you can align data in columns of equal width of 15 characters with right side alignment:

```python
vlan, mac, intf = ['100', 'aabb.cc80.7000', 'Gi0/1']
print("{:>15} {:>15} {:>15}".format(vlan, mac, intf))
```

> **Output:**

> ```python
> 100 aabb.cc80.7000      Gi0/1
> ```

<br>
<br>


Alignment to the left:

```python
print("{:15} {:15} {:15}".format(vlan, mac, intf))
```

> **Output:**

> ```python
> 100       aabb.cc80.7000 Gi0/1
> ```

<br>
<br>


Output template can also be multi-string:

```python
ip_template = '''
IP address:
{}'''
print(ip_template.format('10.1.1.1'))
```

> **Output:**

> ```python
> IP address:
> 10.1.1.1
> ```

<br>
<br>


You can also use string formatting to change the display format of numbers.

 

For example, you can specify how many digits after the comma to show:

```python
print("{:.3f}".format(10.0/3))
```



> **Output:**

> ```python
> 3.333
> ```

<br>
<br>


Using string formatting, you can convert numbers to binary format:

```python
print('{:b} {:b} {:b} {:b}'.format(192, 100, 1, 1))
```

> **Output:**

> ```python
> 11000000 1100100 1 1
> ```

<br>
<br>


You can still specify additional parameters such as column width:

```python
print('{:8b} {:8b} {:8b} {:8b}'.format(192, 100, 1, 1))
```

> **Output:**

> ```python
> 11000000 1100100    1    1
> ```

<br>
<br>


You can also specify that numbers should be supplemented with zeros instead of spaces:

```python
print('{:08b} {:08b} {:08b} {:08b}'.format(192, 100, 1, 1))
```

> **Output:**

> ```python
> 11000000 01100100 00000001 00000001
> ```

<br>
<br>




You can enter names in curly braces. This makes it possible to pass arguments in any order and also makes template more understandable:

```python
print('{ip}/{mask}'.format(mask=24, ip='10.1.1.1'))
```

> **Output:**

> ```python
> 10.1.1.1\24
> ```

<br>
<br>


Another useful feature of string formatting is argument number specification:

```python
print('{1}/{0}'.format(24, '10.1.1.1'))
```

> **Output:**

> ```python
> 10.1.1.1/24
> ```

<br>
<br>


For example this can prevent repetitive transmission of the same values:

```python
ip_template = '''
IP address:
{:<8} {:<8} {:<8} {:<8}
{:08b} {:08b} {:08b} {:08b}
'''
print(ip_template.format(192, 100, 1, 1, 192, 100, 1, 1))
```

> **Output:**

> ```python
> 192   100   1    1    
> 11000000 01100100 00000001 00000001
> ```

<br>
<br>


In example above the octet address has to be passed twice - one for decimal format and other for binary.

 

By specifying value indexes that are passed to `format()` method, it is possible to avoid duplication:

```python
ip_template = '''
IP address:
{0:<8} {1:<8} {2:<8} {3:<8}
{0:08b} {1:08b} {2:08b} {3:08b}
'''
print(ip_template.format(192, 100, 1, 1, 192, 100, 1, 1))
```

> **Output:**

> ```python
> IP address:
> 192   100   1    1
> 11000000 01100100 00000001 00000001
> 
> ```

<br>
<br>

### f-strings

 

Python 3.6 added a new version of string formatting - f-strings or interpolation of strings. The f-strings allow not only to set values to template, but also to perform calls to functions, methods, etc.

In many situations `f-strings` are easier to use than format, and f-strings work faster than format and other methods of string formatting.

 

`F-string` is a literal line with a letter f in front of it. Inside f-string, in curly braces there are names of variables that will be substituted:

```python
ip = '10.1.1.1'
mask = 24

print(f"IP: {ip}, mask: {mask}")
```

> **Output:**

> ```python
> IP: 10.1.1.1, mask: 24
> ```

<br>
<br>


The same result with format method you can achieve by: `"IP: {ip}, mask: {mask}".format(ip=ip, mask=mask)`.

 

A very important difference between f-strings and format: f-strings are expressions that are processed, not just strings. In addition to substituting variable values you can write expressions in curly braces:

```python
first_name = 'William'
second_name = 'Shakespeare'

print(f"{first_name.upper()} {second_name.upper()}")
```

> **Output:**

> ```python
> WILLIAM SHAKESPEARE
> ```

<br>
<br>

After colon in `f-strings` you can specify the same values as in format:

```python
oct1, oct2, oct3, oct4 = [10, 1, 1, 1]

print(f'''
IP address:
{oct1:<8} {oct2:<8} {oct3:<8} {oct4:<8}
{oct1:08b} {oct2:08b} {oct3:08b} {oct4:08b}''')
```

> **Output:**

> ```python
> IP address:
> 10    1    1    1   
> 00001010 00000001 00000001 00000001
> ```

<br> 
<br>

# 2.3  List

 

List in Python is:

- sequence of elements separated by comma and enclosed in square brackets
- mutable ordered data type

 

Examples of lists:

```python
list1 = [10,20,30,77]
list2 = ['one', 'dog', 'seven']
list3 = [1, 20, 4.0, 'word']
```

 

Creating a list using a literal:

```python
vlans = [10, 20, 30, 50]
```

 

> **Info*:***
>
> *Literal is an expression that creates an object.*

 

Create a list using list() function:

```python
list1 = list('router')

print(list1)
```

> **Output**:

> ```python
> ['r', 'o', 'u', 't', 'e', 'r']
> ```
<br>
<br>


Since a list is an ordered data type just like a string, in lists you can refer to an item by number, make slices:

```python
list3 = [1, 20, 4.0, 'word']

print(list3[1])
print(list3[1::])
print(list3[-1])
print(list3[::-1])
```

> **Output**:

> ```python
> 20
> [20, 4.0, 'word']
> word
> ['word', 4.0, 20, 1]
> ```
<br>
<br>


You can reverse list by reverse method:

```python
vlans = ['10', '15', '20', '30', '100-200']
vlans.reverse()

print(vlans)
```

> **Output**:

> ```python
> ['100-200', '30', '20', '15', '10']
> ```
<br>
<br>


Since lists are mutable, list elements can be changed:

```python
list3 = [1, 20, 4.0, 'word']
list3[0] = 'test'

print(list3)
```

> **Output**

> ```python
> ['test', 20, 4.0, 'word']
> ```
<br>
<br>


You can also create a list of lists. As in a regular list you can refer to items in nested lists:

```python
interfaces = [['FastEthernet0/0', '15.0.15.1', 'YES', 'manual', 'up', 'up'],
['FastEthernet0/1', '10.0.1.1', 'YES', 'manual', 'up', 'up'],
['FastEthernet0/2', '10.0.2.1', 'YES', 'manual', 'up', 'down']]

print(interfaces[0][0])
print(interfaces[1][0])
print(interfaces[2][2])
```

> **Output**:

> ```python
> FastEthernet0/0
> FastEthernet0/1
> 10.0.2.1
> ```
<br>
<br>


The `len` function returns number of items in list:

```python
items = [1, 2, 3]

print(len(items))
```

>**Output**:

> ```python
> 3
> ```
<br>
<br>


And sorted function sorts list items in ascending order and returns a new list with sorted items:

```python
names = ['John', 'Michael', 'Antony']

print(sorted(names))
```

> **Output:**

> ```python
> ['Antony', 'John', 'Michael']
> ```


<br>
<br> 

## 2.3.1 List Methods

List is a mutable data type, so it is important to note that most list methods change a list in place without returning anything.


<br>
<br>

### join() Method

Method join collects a list of strings into one string with separator specified before join:

```python
vlans = ['10', '20', '30']

print(','.join(vlans))
print('#'.join(vlans))
```

> **Output**:

> ```python
> 10,20,30
> 10#20#30
> ```
<br>
<br>


> ***Info***:
>
> *Method join actually string method but since the value must be passed to it as a list, it is covered here.*


<br>


### append() Method

Method append adds specified item to the end of list:

```python
vlans = ['10', '20', '30', '100-200']
vlans.append('300')

print(vlans)
```

> **Output**:

> ```python
> ['10', '20', '30', '100-200', '300']
> ```

Method append changes list on spot and does not return anything.

<br>
<br>

### extend () Method

If you want to combine two lists you can use one of two methods: `extend` method or addition operation. These methods have an important difference: extend changes list to which method is applied and addition returns a new list that consists of two.

 

Method extend:

```python
vlans = ['10', '20', '30', '100-200']
vlans2 = ['300', '400', '500']
vlans.extend(vlans2)


print(vlans)
```

> **Output**:

> ```python
> ['10', '20', '30', '100-200', '300', '400', '500']
> ```
<br>
<br>




Addition operation:

```python
vlans = ['10', '20', '30', '100-200']
vlans2 = ['300', '400', '500']

print(vlans + vlans2)
```

> **Output**:

> ```python
> ['10', '20', '30', '100-200', '300', '400', '500']
> ```

<br>
<br>

### pop () Method

Method `pop` removes item that corresponds to specified number. Method returns this item:

```python
vlans = ['10', '20', '30', '100-200']
vlans.pop(-1)

print(vlans)
```

> **Output**:

> ```python
> ['10', '20', '30']
> ```

Without number specified the last item in list is deleted.

<br>
<br>

### remove () Method

Method `remove` removes specified item (remove does not return deleted item):

```python
vlans = ['10', '20', '30', '100-200']
vlans.remove('20')

print(vlans)
```

> **Output**:

> ```python
> ['10', '30', '100-200']
> ```
<br>
<br>




In `remove` you must specify item to be deleted, not its index. If item number is specified, error occurs:

```python
vlans = ['10', '20', '30', '100-200']
vlans.remove(2)

print(vlans)
```

> **Output**:

> ```python
> Traceback (most recent call last):
> File "test.py", line 2, in <module>  
> vlans.remove(2)
> ValueError: list.remove(x): x not in list
> ```


<br>
<br>

### index () Method

Method `index` returns the first index of the passed value:

```python
vlans = ['10', '20', '30', '100-200']

print(vlans.index('30'))
```

> **Output**:

> ```python
> 2
> ```

<br>
<br>

### insert () Method

Method `insert` allows to insert an item into a specific place in list:

```python
vlans = ['10', '20', '30', '100-200']
vlans.insert(1, '15')

print(vlans)
```

> **Output**:

> ```python
> ['10', '15', '20', '30', '100-200']
> ```

<br>
<br>

### sort () Method

Method `sort` sorts list in place:

```python
vlans = [1, 50, 10, 15]
vlans.sort()

print(vlans)
```

> **Output**:

> ```python
> [1, 10, 15, 50]
> ```
<br>
<br>

# 2.4 Dictionary

 

Dictionaries are mutable ordered data type:

- data in dictionary are pairs key: value
- values are accessible by key, not by number as in lists
- entries in dictionary stored in order they were added
- since dictionaries are mutable, dictionary items can be changed, added, removed
- key must be an immutable object: number, string, tuple
- value can be data of any type

 

> ***Info:***
>
> *In other programming languages a similar dictionary can be called an associative array, hash, or hash table.*

 

Example of dictionary:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}
```

 

You can write it down like this:

```python
ankara = {
  'id': 1,
  'name': 'Ankara',
  'it_vlan': 320,
  'user_vlan': 1010,
  'mngmt_vlan': 99,
  'to_name': None,
  'to_id': None,
  'port': 'G1/0/11'
}
```

 

In order to get a value from dictionary you have to refer to key in the same way as in lists, only key will be used instead of number:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya'}

print(ankara['name'])
print(ankara['location'])
```

Output:

```python
Ankara
Cankaya
```
<br>
<br>


Similarly, a new key-value pair could be added:

```python
ankara['vendor'] = 'Cisco'

print(ankara)
```

Output:

```python
{'vendor': 'Cisco', 'name': 'Ankara', 'location': 'Cankaya'}
```

 

Or rewritten:

```python
ankara['vendor'] = 'cisco ios'

print(ankara)
```

Output:

```python
{'vendor': 'cisco ios', 'name': 'Ankara', 'location': 'Cankaya'}
```
<br>
<br>


In dictionary you can use a dictionary as a value:

```python
ankara_devices = {
  'r1': {
'hostname': 'ankara_rtr1',
'location': 'Cankaya',
'vendor': 'Cisco',
'model': '4451',
'ios': '15.4',
'ip': '10.255.0.1'
  },

  'r2': {
'hostname': 'ankara_rtr2',
'location': 'Cankaya,
'vendor': 'Cisco',
'model': '4451',
'ios': '15.4',
'ip': '10.255.0.2'
  },

   'sw1': {
'hostname': 'ankara_sw1',
'location': 'Cankaya',
'vendor': 'Cisco',
'model': '3850',
'ios': '3.6.XE',
'ip': '10.255.0.101'
  }
}
```

 

You can get values from nested dictionary by:

```python
print(ankara_devices['r1']['ios'])
print(ankara_devices['r1']['model'])
print(ankara_devices ['sw1']['ip'])
```

Output:

```python
15.4
4451
10.255.0.101
```

<br>
<br>


Function sorted sorts dictionary keys in ascending order and returns a new list with sorted keys:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}

print(sorted(ankara))
```

> Output:

> ```python
> ['location', 'name', 'vendor']
> ```
<br>
<br>




## 2.4.1 Dictionary Methods

### clear() Method

Method clear allows to clear dictionary:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya'}
ankara.clear()

print(ankara)
```

> Output:

> ```python
> {}
> ```

 



### copy() Method

Method `copy` allows to create a full copy of dictionary.

If one dictionary is equal to other:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}
ankara2 = ankara

print(id(ankara))
print(id(ankara2))

ankara['vendor'] = 'Juniper'
print(ankara2['vendor'])
```

> Output:

> ```python
> 3050637299008
> 3050637299008
> Juniper
> ```

 

In this case `ankara2` is another name that refers to dictionary `ankara`. And when you change `ankara` dictionary, `ankara2` dictionary changes as well because it’s a link to the same object.

Therefore, if you want to make a copy of dictionary, use `copy` method:

 

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}
ankara2 = ankara.copy()

print(id(ankara))
print(id(ankara2))

ankara['vendor'] = 'Juniper'
print(ankara2['vendor'])
```

> Output:

> ```python
> 1612008262976
> 1612008263040
> Cisco
> ```

 



### get() Method

If you query a key that is not present in dictionary, an error occurs:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}

print(ankara['ios'])
```

> Output:

> ```python
> Traceback (most recent call last):
> File "test.py", line 3, in <module>
> print(ankara['ios'])
> KeyError: 'ios'
> ```

 

Method `get()` queries for key and if there is no key, returns None instead.

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}
print(ankara.get('ios'))
```

> Output:

> ```python
> None
> ```



Method `get()` also allows you to specify another value instead of None:

```python
print(ankara.get('ios', 'Ooops'))
```

> Output:

> ```python
> Ooops
> ```

 



### setdefault () Method

Method `setdefault` searches for key and if there is no key, instead of error it creates a key with None value.

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}
ios = ankara.setdefault('ios')

print(ios)
print(ankara)
```

> **Output:**

> ```python
> None
> {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco', 'ios': None}
> ```

 

If key is present, `setdefault` returns value that corresponds to it:

```python
ankara.setdefault('name')
```

 

The second argument allows to specify which value should correspond to key:

```python
model = ankara.setdefault('model', 'Cisco3580')

print(model)
print(ankara)
```

> **Output:**

> ```python
> Cisco3580
> {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco', 'model': 'Cisco3580'}
> ```

 



### keys(), values(), items()

Methods `keys`, `values`, `items`:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}

print(ankara.keys())
print(ankara.values())
print(ankara.items())
```

> **Output**:

> ```python
> dict_keys(['name', 'location', 'vendor'])
> dict_values(['Ankara', 'Cankaya', 'Cisco'])
> dict_items([('name', 'Ankara'), ('location', 'Cankaya'), ('vendor', 'Cisco')])
> ```

 

All three methods return special view objects that contains keys, values, and key-value pairs of dictionary, respectively.

A very important feature of view is that they change together with dictionary. And in fact, they just give you a way to look at objects, but they don’t make a copy of them.

Example of using keys:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}
keys = ankara.keys()

print(keys)
```

> **Output:**

> ```python
> dict_keys(['name', 'location', 'vendor'])
> ```

 

Now keys variable corresponds to view `dict_keys`, in which three keys: name, location and vendor.

But if we add another key-value pair to dictionary, keys object will also change:

```python
ankara['ip'] = '10.1.1.1'
print(keys)
```

> **Output:**

> ```python
> dict_keys(['name', 'location', 'vendor', 'ip'])
> ```

 

If you want to get a simple list of keys that will not be changed with dictionary changes, it is enough to convert view to list:

```python
list_keys = list(ankara.keys())

print(list_keys)
```

**Output:**

> ```python
> ['name', 'location', 'vendor', 'ip']
> ```

 



### del() Method

Remove key and value:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}
del ankara['name']

print(ankara)
```

> **Output**:

> ```python
> {'location': 'Cankaya', 'vendor': 'Cisco'}
> ```

 

 

### update() Method

Method update allows you to add contents of one dictionary to another dictionary:

```python
rtr1 = {'name': 'Ankara', 'location': 'Cankaya'}
rtr1.update({'vendor': 'Cisco', 'ios':'15.2'})

print(rtr1)
```

**Output:**

> ```python
> {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco', 'ios': '15.2'}
> ```

 

Values can be updated in the same way:

```python
rtr1.update({'name': 'ankara_rtr1', 'ios':'15.4'})
```

> **Output:**

> ```python
> {'name': 'ankara_rtr1', 'location': 'Cankaya', 'vendor': 'Cisco', 'ios': '15.4'}
> ```

 

 

## 2.4.2 Dictionary Creation Options

### Literal

A dictionary can be created with help of a literal:

```python
rtr1 = {'model': '4451', 'ios': '15.4'}
```

 



### dict

Construction `dict` allows you to create a dictionary in several ways.

If you use strings as keys you can use this option to create a dictionary:

```python
rtr1 = dict(model='4451', ios='15.4')

print(rtr1)
```

> **Output:**

> ```python
> {'model': '4451', 'ios': '15.4'}
> ```

 

The second option of creating a dictionary with `dict()`:

```python
rtr1 = dict([('model','4451'), ('ios','15.4')])

print(rtr1)
```

> **Output:**

> ```python
> {'model': '4451', 'ios': '15.4'}
> ```

 



### dict.fromkeys

In a situation where you need to create a dictionary with known keys but so far empty values (or identical values), `fromkeys` method is very convenient:

```python
d_keys = ['hostname', 'location', 'vendor', 'model', 'ios', 'ip']
rtr1 = dict.fromkeys(d_keys)

print(rtr1)
```

> **Output:**

> ```python
> {'hostname': None, 'location': None, 'vendor': None, 'model': None, 'ios': None, 'ip': None}
> ```

 

By default `fromkeys` sets `None` value. But you can also pass your own value:

```python
router_models = ['ISR2811', 'ISR2911', 'ISR2921', 'ASR9002']
models_count = dict.fromkeys(router_models, 0)

print(models_count)
```

> **Output:**

> ```python
> {'ISR2811': 0, 'ISR2911': 0, 'ISR2921': 0, 'ASR9002': 0}
> ```

 

This option of creating a dictionary is not suitable for all cases. For example, if you use a mutable data type in value, a reference to the same object will be created:

```python
router_models = ['ISR2811', 'ISR2911', 'ISR2921', 'ASR9002']
routers = dict.fromkeys(router_models, [])

print(routers)

routers['ASR9002'].append('london_r1')

print(routers)
```

> **Output:**

> ```python
> {'ISR2811': [], 'ISR2911': [], 'ISR2921': [], 'ASR9002': []}
> {'ISR2811': ['london_r1'], 'ISR2911': ['london_r1'], 'ISR2921': ['london_r1'], 'ASR9002': ['london_r1']}
> ```

# 2.5 Tuple

Tuple in Python is:

* a sequence of elements separated by a comma and enclosed in parentheses

* immutable ordered data type

Roughly speaking, a tuple is a list that can’t be changed. We can say that the tuple has read-only permissions. It could be a defense against accidental change.

Create an empty tuple:

```python
tuple1 = tuple()

print(tuple1)
```

> **Output**:

> ```python
> ()
> ```

 

Tuple with one element (note the comma):

```python
tuple2 = ('password',)
```

 

Tuple from list:

```python
list_keys = ['hostname', 'location', 'vendor', 'model', 'ios', 'ip']

tuple_keys = tuple(list_keys)

 

print(tuple_keys)
```

> **Output**:

> ```python
> ('hostname', 'location', 'vendor', 'model', 'ios', 'ip')
> ```

 

Objects in tuple can be accessed as well as objects in list, by order number:

```python
print(tuple_keys[0])
```

> Output:

> ```python
> hostname
> ```

 

But since tuple is immutable you cannot assign a new value:

```python
tuple_keys[1] = 'test_key'
```

> **Output**:

> ```python
> Traceback (most recent call last):
> File "test.py", line 4, in <module>
> 
> tuple_keys[1] = 'test_key'
> 
> TypeError: 'tuple' object does not support item assignment
> ```

 

Function sorted sorts tuple elements in ascending order and returns a new list with sorted elements:

```python
tuple_keys = ('hostname', 'location', 'vendor', 'model', 'ios', 'ip')

print(sorted(tuple_keys))
```

> **Output:**

> ```python
> ['hostname', 'ios', 'ip', 'location', 'model', 'vendor']
> ```

 

<br>

<br>