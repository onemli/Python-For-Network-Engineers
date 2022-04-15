# 2. Numbers

 

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

## 2.1   Numbers

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

<img src="C:\Users\ONEMLI\Dessk\SVG\assets\logo.svg" alt="drawing" width="100"/>