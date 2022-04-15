### 2.2.3     Tuple

 

Tuple in Python is:

- a sequence of elements separated by a comma and enclosed in parentheses

- immutable ordered data type

Roughly speaking, a tuple is a list that can’t be changed. We can say that the tuple has read-only permissions. It could be a defense against accidental change.

 

Create an empty tuple:

```
tuple1 = tuple()

print(tuple1)
```

Output:

```
()
```

 

Tuple with one element (note the comma):

```
tuple2 = ('password',)
```

 

Tuple from list:

```
list_keys = ['hostname', 'location', 'vendor', 'model', 'ios', 'ip']
tuple_keys = tuple(list_keys)

print(tuple_keys)
```

Output:

```
('hostname', 'location', 'vendor', 'model', 'ios', 'ip')
```

 

Objects in tuple can be accessed as well as objects in list, by order number:

```
print(tuple_keys[0])
```

Output:

```
hostname
```

 

But since tuple is immutable you cannot assign a new value:

```
tuple_keys[1] = 'test_key'
```

Output:

```
Traceback (most recent call last):
 File "test.py", line 4, in <module>
  tuple_keys[1] = 'test_key'
TypeError: 'tuple' object does not support item assignment
```

 

Function sorted sorts tuple elements in ascending order and returns a new list with sorted elements:

```
tuple_keys = ('hostname', 'location', 'vendor', 'model', 'ios', 'ip')

print(sorted(tuple_keys))
```

Output:

```
['hostname', 'ios', 'ip', 'location', 'model', 'vendor']
```

 



 