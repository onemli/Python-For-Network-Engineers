### 2.2.3     Boolean

 

Boolean values in Python are two constants True and False.

In Python, not only True and False are considered True and False values.

True value:

- any non-zero number
- any non-empty string
- any non-empty object
- False value:
- 0
- None
- empty string
- empty object

Other True and False values tend to follow the condition logically.

 

To check boolean value of object you can use bool:

```
empty_list = []
non_empty_list = [1, 2, 3]

print(bool(empty_list))
print(bool(non_empty_list))
print(bool(0))
print(bool(1))
```

Output:

```
False
True
False
True
```

 