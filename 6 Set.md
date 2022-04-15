# 2.6     Set

 Set is a mutable unordered data type. Set always contains only unique elements. Set in Python is a sequence of elements that are separated by a comma and placed in curly braces.

Set can easily remove repetitive elements:

```python
vlans = [10, 20, 30, 40, 100, 10]

print(set(vlans))
```

> **Output**:

> ```python
> {100, 40, 10, 20, 30}
> ```
>

 

## 2.6.1 Set Methods

### add() Method

Method add adds an item to set:

```python
set1 = {10,20,30,40}
set1.add(50)

print(set1)
```

> **Output**:
>

> ```python
> {40, 10, 50, 20, 30}
> ```
>

<br>
<br>

### discard() Method

Method discard allows deleting elements without showing an error if there is no element in set:

```python
print(set1)
set1.discard(55)
print(set1)
set1.discard(50)
print(set1)
```

> **Output**:

> ```python
> {40, 10, 50, 20, 30}
> {40, 10, 50, 20, 30}
> {40, 10, 20, 30}
> ```
>

<br>
<br> 

### clear() Method

Method clear empties set:

```python
set1 = {10,20,30,40}
set1.clear()

print(set1)
```

> **Output**:

> ```python
> set()
> ```
>

<br>
<br>

## 2.6.2 Operation with sets

Sets are useful in performing different operations such as finding union of sets, intersection and so on.

Union of sets can be obtained by union or operator `|`:

```python
vlans1 = {10,20,30,50,100}
vlans2 = {100,101,102,102,200}

print(vlans1.union(vlans2))
print(vlans1 | vlans2)
```

> **Output**:

> ```python
> {100, 101, 102, 200, 10, 50, 20, 30}
> {100, 101, 102, 200, 10, 50, 20, 30}
> ```
>

<br>
<br>


Intersection of sets can be obtained by intersection or operator &:

```python
vlans1 = {10,20,30,50,100}
vlans2 = {100,101,102,102,200}

print(vlans1.intersection(vlans2))
print(vlans1 & vlans2)
```

> **Output**:

> ```python
> {100}
> {100}
> ```
>

<br>
<br>


## 2.6.3 Options for set Creation

You cannot create an empty set using a literal set (in this case it will not be a set but a dictionary):

```python
set1 = {}

print(type(set1))
```

> **Output**:

> ```python
> <class 'dict'>
> ```
>

<br>
<br>


But an empty set can be created in this way:

```python
set2 = set()

print(type(set2))
```

> **Output**:

> ```python
> <class 'set'>
> ```
>

<br>
<br> 

Set from string:

```python
set3 = set('long long long long string')

print(type(set3))
print(set3)
```

> **Output**:

> ```python
> {'l', ' ', 'r', 'o', 'g', 'i', 't', 'n', 's'}
> <class 'set'>
> ```
>

<br>
<br> 

Set from list:

```python
set4 = set([10, 20, 30, 10, 10, 30])

print(type(set4))
print(set4)
```

> **Output**:

> ```python
> set4 = set([10, 20, 30, 10, 10, 30])
> 
> print(type(set4))
> print(set4)
> ```
>

 