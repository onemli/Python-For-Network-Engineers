String in Python is:

- sequence of characters enclosed in quotes
- immutable ordered data type

Examples of strings:

```
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

```
intf = 'interface'
gi = 'GigabitEthernet'

print (intf + ' ' +gi + ' 0/0')
```

**Output:**

```
interface GigabitEthernet 0/0
```


You can multiply a string by a number. In this case, string repeats specified number of times:

```
print (50*'-')
```

**Output:**

```
--------------------------------------------------
```


The fact that strings are an ordered data type allows to refer to characters in a string by a number starting from zero:

```
interface = 'interface GigabitEthernet1/0'

print(interface[10])
```

**Output:**

```
G
```


All characters in a string are numbered from zero. But if you need to refer to a character from the end, you can specify negative values (this time with 1).

```
print(interface[1])
print(interface[-1])
```

**Output:**

```
n
0
```


In addition to referring to a specific character you can make string slices by specifying a number range. Slicing starts with first number (included) and ends at second number (excluded):

```
print(interface[0:9])
print(interface[10:25])
```

**Output:**

```
interface
GigabitEthernet
```


If no second number is specified, slice is until the end of string:

```
print(interface[10:])
```

**Output:**

```
GigabitEthernet1/0
```


Slice last three character of string:

```
print(interface[-3:])
```

**Output:**

```
1/0
```


You can also specify a step in slice. For example, you can get odd numbers:

```
numbers = '0123456789'

print(numbers[1::2])
```

**Output:**

```
13579
```


Or you can get all even numbers of string numbers:

```
print(numbers[::2])
```

**Output:**

```
02468
```


Slices can also be used to get a string in reverse order:

```
numbers = '0123456789'
print(numbers[::-1])
```


**Output:**

```
9876543210
```



The `len()` function allows you to get number of characters in a string:

```
interface = 'interface GigabitEthernet1/0'
print(len(interface))
```

**Output:**

```
28
```

