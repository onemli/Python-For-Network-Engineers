

This type of error can occur when converting data types:

```
print(int('a'))
```

Output:

```
Traceback (most recent call last):
 File "types_checking.py", line 3, in <module>    
  print(int('a'))
ValueError: invalid literal for int() with base 10: 'a'
```

 

Error is perfectly logical. We’re trying to convert string ‘a’ into decimal format. For example, this can be useful when you want to go through a list of strings and convert to a number the strings that contain numbers, you can get that error. To avoid error, it would be nice to be able to check what we’re working with.

 

#### isdigit()

Python has such methods. For example, `isdigit` method can be used to check whether a string consists only of digits:

```
print("a".isdigit())
print("a10".isdigit())
print("10".isdigit())
```

Output:

```
False
False
True
```

 



#### isalfa()

Method `isalpha` makes it possible to check whether a string consists only of letters:

```
print("a".isalpha())
print("a100".isalpha())
print("a-- ".isalpha())
print("a ".isalpha())
```

Output:

```
True
False
False
False
```

 



#### isalnum()

Method `isalnum` makes it possible to check whether a string consists of letters or numbers:

```
print("a".isalnum())
print("a10".isalnum())
```

Output:

```
True
True
```

 

#### type()

Sometimes, depending on the result, a library or function can return different types of objects. For example, if there is one object, string is returned. If several, tuple is returned. We have to construct the program in different ways, depending on whether a string or a tuple has been returned.

 

Method type function can help:

```
print(type("string"))
print(type("string") == str)
```

Output:

```
<class 'str'>
True
```

 

Similar to tuple (and other data types):

```
print(type((1, 2, 3)))
print(type((1, 2, 3)) == tuple)
print(type((1, 2, 3)) == list)
```

Output:

```
<class 'tuple'>
True
False
```

 