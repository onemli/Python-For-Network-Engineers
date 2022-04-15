# 1. Variables



Variables in Python do not require variable type declaration (since Python is a language with dynamic typing) and they are references to a memory area. Variable naming rules:

- Name of variable can consist only of letters, digits and an underscore

- Name cannot start with a digit

- Name cannot contain special characters @, $, %.




An example of creating variables in Python:

```python
vendor = 'Cisco'
founded = 1984
```

 

We can simplify the below creation:

```python
vendor, founded = 'Cisco', 1984
```

 

Variables are references to memory area. This can be demonstrated by using id() which shows object ID:

```python
vendor = company = brand = 'Cisco'

print(id(vendor))
print(id(company))
print(id(brand))
```

>  **Output:**
>

> ```python
> 2505311003056
> 2505311003056
> 2505311003056
> ```
>

 

In this example you can see that all three names refer to the same identifier, so it is the same object to which three references " vendor ", company" " and "brand" point. 

<br>
<br>

## 1.1   Variable Names

Variable names should not overlap with names of operators and modules or other reserved words. Python has recommendations for naming functions, classes and variables:

- Variable names are usually written in lowercase or in uppercase (e.g., DB_NAME, db_name)

- Function names are written in lowercase, with underline between words (for example get_interface_names)

- Class names are given with capital letters without spaces, it is called CamelCase (for example, CiscoSwitch)

<br>
<br>

# 2. Data Types

 

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
>

> ```python
> 3
> 3.0
> 6
> 8
> ```
>



Division int and float:

```python
print(10/3)
print(10/3.0)
```

> **Output:**
>

> ```python
> 3.3333333333333335
> 3.3333333333333335
> ```



The round() function - round a number to a given precision in decimal digits:

```python
print(round(10/3.0, 2))
print(round(10/3.0, 4))
```

> **Output:**
>

> ```python
> 3.33
> 3.3333
> ```



Remainder of division:

```python
print(10 % 3)
```

> **Output:**
>

> ```python
> 1
> ```
>



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
>

> ```python
> True
> False
> False
> True
> True
> True
> ```
>

 

The `int()` function allows converting to `int` type. The second argument can specify number system:

```python
founded = '1984'
print(int(founded))
```

> **Output:**

> ```python
> 1984
> ```
>

 

If you specify that string should be read as a binary number, the result is:

```python
a = '11'
print(int(a, 2))
```

> **Output:**

> ```python
> 3
> ```
>

 

Convert to int from float:

```python
print(int(3.333))


print(int(3.9))
```

> **Output:**
>

> ```python
> 3
> 3
> ```
>

 

The bin() function produces a binary representation of a number (note that the result is a string):

```python
print(bin(8))

print(bin(255))
```

> **Output:**
>

> ```python
> 0b1000
> 0b11111111
> ```
>

 

Similarly, function hex() produces a hexadecimal value:

```python
print(hex(10))
```

> **Output:**
>

> ```python
> 0xa
> ```
>

 

And, of course, you can do several changes at the same time:

```python
print(int('ff', 16))

print(bin(int('ff', 16)))
```

> **Output:**
>

> ```python
> 255
> 0b11111111
> ```
>


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
>



You can multiply a string by a number. In this case, string repeats specified number of times:

```python
print (50*'-')
```

> **Output:**

> ```python
> --------------------------------------------------
> ```
>



The fact that strings are an ordered data type allows to refer to characters in a string by a number starting from zero:

```py
interface = 'interface GigabitEthernet1/0'

print(interface[10])
```

> **Output:**

> ```python
> G
> ```
>



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
>



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
>



If no second number is specified, slice is until the end of string:

```python
print(interface[10:])
```

> **Output:**

> ```python
> GigabitEthernet1/0
> ```
>



Slice last three character of string:

```python
print(interface[-3:])
```

> **Output:**

> ```python
> 1/0
> ```
>



You can also specify a step in slice. For example, you can get odd numbers:

```python
numbers = '0123456789'

print(numbers[1::2])
```

> **Output:**

> ```python
> 13579
> ```
>



Or you can get all even numbers of string numbers:

```python
print(numbers[::2])
```

> **Output:**

> ```python
> 02468
> ```
>



Slices can also be used to get a string in reverse order:

```python
numbers = '0123456789'
print(numbers[::-1])
```

> **Output:**

> ```python
> 9876543210
> ```
>



The `len()` function allows you to get number of characters in a string:

```python
interface = 'interface GigabitEthernet1/0'
print(len(interface))
```

> **Output:**

> ```python
> 28
> ```
>


<br>
<br>

## 2.2.1 String Methods



When automating, very often it will be necessary to work with strings, since config file, command output and commands sent - are strings. Knowledge of various methods (actions) that can be applied to strings helps to work with them more efficiently.

 Strings are immutable data type, so all methods that convert string returns a new string and the original string remains unchanged.

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
>



It is very important to pay attention to the fact that methods often return the converted string. And, therefore, we must not forget to assign it to some variable (you can use the same).

```python
interface = interface.upper()
print(interface)
```

> **Output:**

> ```python
> INTERFACE GIGABITETHERNET1/0
> ```
>


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
>



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
>

> ***Info:***
>
> *If no match is found, find() method returns -1.*


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
>



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
>



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
>




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
>




Method `strip()` removes special characters at the beginning and at the end of the line. If you want to remove characters only on the left or only on the right, you can use `lstrip()` and `rstrip()`.


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
>




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
>




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
>




Method split has another good feature: by default, method splits a string not by one whitespace character, but by any number. For example, this will be very useful when processing show commands:

```python
sh_ip_int_br = "FastEthernet0/0    15.0.15.1  YES manual up     up"

print(sh_ip_int_br.split())
```

> **Output:**

> ```python
> ['FastEthernet0/0', '15.0.15.1', 'YES', 'manual', 'up', 'up']
> ```
>



 

And this is the same string when one space is used as the separator:

```python
sh_ip_int_br = "FastEthernet0/0    15.0.15.1  YES manual up     up"

print(sh_ip_int_br.split(' '))
```

> **Output:**

> ```python
> ['FastEthernet0/0', '', '', '', '', '', '', '15.0.15.1', '', '', '', 'YES', 'manual', 'up', '', '', '', '', '', '', '', '', 'up']
> ```
>

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

 

You can align result in columns by formatting strings. In string formatting, you can specify how many characters are selected for the data. If number of characters in the data is less than number of characters selected, the missing characters are filled with blanks.

 

For example, you can align data in columns of equal width of 15 characters with right side alignment:

```python
vlan, mac, intf = ['100', 'aabb.cc80.7000', 'Gi0/1']
print("{:>15} {:>15} {:>15}".format(vlan, mac, intf))
```

> **Output:**

> ```python
>       100 aabb.cc80.7000      Gi0/1
> ```

 

Alignment to the left:

```python
print("{:15} {:15} {:15}".format(vlan, mac, intf))
```

> **Output:**

> ```python
> 100       aabb.cc80.7000 Gi0/1
> ```

 

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

 

You can also use string formatting to change the display format of numbers.

 

For example, you can specify how many digits after the comma to show:

```python
print("{:.3f}".format(10.0/3))
```



> **Output:**

> ```python
> 3.333
> ```

 

Using string formatting, you can convert numbers to binary format:

```python
print('{:b} {:b} {:b} {:b}'.format(192, 100, 1, 1))
```

> **Output:**

> ```python
> 11000000 1100100 1 1
> ```

 

You can still specify additional parameters such as column width:

```python
print('{:8b} {:8b} {:8b} {:8b}'.format(192, 100, 1, 1))
```

> **Output:**

> ```python
> 11000000 1100100    1    1
> ```

 

You can also specify that numbers should be supplemented with zeros instead of spaces:

```python
print('{:08b} {:08b} {:08b} {:08b}'.format(192, 100, 1, 1))
```

> **Output:**

> ```python
> 11000000 01100100 00000001 00000001
> ```

 

 

You can enter names in curly braces. This makes it possible to pass arguments in any order and also makes template more understandable:

```python
print('{ip}/{mask}'.format(mask=24, ip='10.1.1.1'))
```

> **Output:**

> ```python
> 10.1.1.1\24
> ```

 

Another useful feature of string formatting is argument number specification:

```python
print('{1}/{0}'.format(24, '10.1.1.1'))
```

> **Output:**

> ```python
> 10.1.1.1/24
> ```

 

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
>  
> IP address:
> 192   100   1    1
> 11000000 01100100 00000001 00000001
> 
> ```

 


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
>

 

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
>

 

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
>

 

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
>

 

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
>

 

The `len` function returns number of items in list:

```python
items = [1, 2, 3]

print(len(items))
```

**Output**:

> ```python
> 3
> ```
>

 

And sorted function sorts list items in ascending order and returns a new list with sorted items:

```python
names = ['John', 'Michael', 'Antony']

print(sorted(names))
```

> **Output:**

> ```python
> ['Antony', 'John', 'Michael']
> ```
>


<br>
<br> 

## 2.3.1 List Methods

List is a mutable data type, so it is important to note that most list methods change a list in place without returning anything.


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
>

 

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
>

Method append changes list on spot and does not return anything.




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
>

 



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
>

 

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
>

Without number specified the last item in list is deleted.

 

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
>

 



In `remove` you must specify item to be deleted, not its index. If item number is specified, error occurs:

```python
vlans = ['10', '20', '30', '100-200']
vlans.remove(2)

print(vlans)
```

> **Output**:

> ```python
> Traceback (most recent call last):
>  File "test.py", line 2, in <module>  
>   vlans.remove(2)
> ValueError: list.remove(x): x not in list
> ```
>

 

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
>

 

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
>

 

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
>

 