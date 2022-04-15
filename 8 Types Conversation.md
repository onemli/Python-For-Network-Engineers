### 2.2.3     Types Conversation

 

Python has several useful built-in features that allow data to be converted from one type to another.

 

#### int

`int` converts a `string` to `int`:

```
int("10")
```

Using `int` function you can convert a binary number into a decimal number (binary number must be written as a string)

```
print(int("11111111", 2))
```

Output:

```
255
```

 

#### bin

You can convert a decimal number to binary format with `bin`:

```
print(bin(10))

print(bin(255))
```

Output:

```
0b1010

0b11111111
```

 

#### hex

A similar function exists for conversion to hexadecimal format:

```
print(hex(10))

print(hex(255))
```

Output:

```
0xa

0xff
```

 

#### list

Function `list` converts an argument to a list:

```
print(list("buraya bakarlar"))

print(list({1,2,3}))

print(list((1,2,3,4)))
```

Output:

```
['b', 'u', 'r', 'a', 'y', 'a', ' ', 'b', 'a', 'k', 'a', 'r', 'l', 'a', 'r']

[1, 2, 3]

[1, 2, 3, 4]
```

 

#### set

Function `set` converts an argument into a set:

```
print(set([1,2,3,3,4,4,4,4]))

print(set((1, 2, 3, 3, 4, 4, 4, 4)))

print(set("string string"))
```

Output:

```
{1, 2, 3, 4}

{1, 2, 3, 4}

{'i', 'g', 'n', ' ', 's', 't', 'r'}
```

 

INFO:

This function is very useful when you need to get unique elements in a sequence.

 

#### tuple

Function `tuple` converts argument into a tuple:

```
print(tuple([1,2,3,4]))

print(tuple({1,2,3,4}))

print(tuple("buraya bakarlar"))
```

Output:

```
(1, 2, 3, 4)

(1, 2, 3, 4)

('b', 'u', 'r', 'a', 's', 'y', 'a', ' ', 'b', 'a', 'k', 'a', 'r', 'l', 'a', 'r')
```

 

INFO:

This can be useful if you want an immutable object.

 

#### str

Function `str` converts an argument into a string:

```
print(type(str(10)))
```

Output:

```
<class 'str'>
```

 