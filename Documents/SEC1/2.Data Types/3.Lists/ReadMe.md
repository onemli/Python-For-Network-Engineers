# 3.  List

 

List in Python is:

- sequence of elements separated by comma and enclosed in square brackets
- mutable ordered data type

 

Examples of lists:

```
list1 = [10,20,30,77]
list2 = ['one', 'dog', 'seven']
list3 = [1, 20, 4.0, 'word']
```

 

Creating a list using a literal:

```
vlans = [10, 20, 30, 50]
```

 

> **Info*:***
>
> *Literal is an expression that creates an object.*

 

Create a list using list() function:

```
list1 = list('router')

print(list1)
```

> **Output**:

> ```
> ['r', 'o', 'u', 't', 'e', 'r']
> ```

 

Since a list is an ordered data type just like a string, in lists you can refer to an item by number, make slices:

```
list3 = [1, 20, 4.0, 'word']

print(list3[1])
print(list3[1::])
print(list3[-1])
print(list3[::-1])
```

> **Output**:

> ```
> 20
> [20, 4.0, 'word']
> word
> ['word', 4.0, 20, 1]
> ```

 

You can reverse list by reverse method:

```
vlans = ['10', '15', '20', '30', '100-200']
vlans.reverse()

print(vlans)
```

> **Output**:

> ```
> ['100-200', '30', '20', '15', '10']
> ```

 

Since lists are mutable, list elements can be changed:

```
list3 = [1, 20, 4.0, 'word']
list3[0] = 'test'

print(list3)
```

> **Output**

> ```
> ['test', 20, 4.0, 'word']
> ```

 

You can also create a list of lists. As in a regular list you can refer to items in nested lists:

```
interfaces = [['FastEthernet0/0', '15.0.15.1', 'YES', 'manual', 'up', 'up'],
['FastEthernet0/1', '10.0.1.1', 'YES', 'manual', 'up', 'up'],
['FastEthernet0/2', '10.0.2.1', 'YES', 'manual', 'up', 'down']]

print(interfaces[0][0])
print(interfaces[1][0])
print(interfaces[2][2])
```

> **Output**:

> ```
> FastEthernet0/0
> FastEthernet0/1
> 10.0.2.1
> ```

 

The `len` function returns number of items in list:

```
items = [1, 2, 3]

print(len(items))
```

**Output**:

> ```
> 3
> ```

 

And sorted function sorts list items in ascending order and returns a new list with sorted items:

```
names = ['John', 'Michael', 'Antony']

print(sorted(names))
```

> **Output:**

> ```
> ['Antony', 'John', 'Michael']
> ```


<br>
<br> 

## 3.1 List Methods

List is a mutable data type, so it is important to note that most list methods change a list in place without returning anything.


<br>

### join() Method

Method join collects a list of strings into one string with separator specified before join:

```
vlans = ['10', '20', '30']

print(','.join(vlans))
print('#'.join(vlans))
```

> **Output**:

> ```
> 10,20,30
> 10#20#30
> ```

 

> ***Info***:
>
> *Method join actually string method but since the value must be passed to it as a list, it is covered here.*


<br>


### append() Method

Method append adds specified item to the end of list:

```
vlans = ['10', '20', '30', '100-200']
vlans.append('300')

print(vlans)
```

> **Output**:

> ```
> ['10', '20', '30', '100-200', '300']
> ```

Method append changes list on spot and does not return anything.




<br>

### extend () Method

If you want to combine two lists you can use one of two methods: `extend` method or addition operation. These methods have an important difference: extend changes list to which method is applied and addition returns a new list that consists of two.

 

Method extend:

```
vlans = ['10', '20', '30', '100-200']
vlans2 = ['300', '400', '500']
vlans.extend(vlans2)


print(vlans)
```

> **Output**:

> ```
> ['10', '20', '30', '100-200', '300', '400', '500']
> ```

 



Addition operation:

```
vlans = ['10', '20', '30', '100-200']
vlans2 = ['300', '400', '500']

print(vlans + vlans2)
```

> **Output**:

> ```
> ['10', '20', '30', '100-200', '300', '400', '500']
> ```

 

<br>

### pop () Method

Method `pop` removes item that corresponds to specified number. Method returns this item:

```
vlans = ['10', '20', '30', '100-200']
vlans.pop(-1)

print(vlans)
```

> **Output**:

> ```
> ['10', '20', '30']
> ```

Without number specified the last item in list is deleted.

 

<br>

### remove () Method

Method `remove` removes specified item (remove does not return deleted item):

```
vlans = ['10', '20', '30', '100-200']
vlans.remove('20')

print(vlans)
```

> **Output**:

> ```
> ['10', '30', '100-200']
> ```

 



In `remove` you must specify item to be deleted, not its index. If item number is specified, error occurs:

```
vlans = ['10', '20', '30', '100-200']
vlans.remove(2)

print(vlans)
```

> **Output**:

> ```
> Traceback (most recent call last):
> File "test.py", line 2, in <module>  
> vlans.remove(2)
> ValueError: list.remove(x): x not in list
> ```

 

<br>

### index () Method

Method `index` returns the first index of the passed value:

```
vlans = ['10', '20', '30', '100-200']

print(vlans.index('30'))
```

> **Output**:

> ```
> 2
> ```

 

<br>

### insert () Method

Method `insert` allows to insert an item into a specific place in list:

```
vlans = ['10', '20', '30', '100-200']
vlans.insert(1, '15')

print(vlans)
```

> **Output**:

> ```
> ['10', '15', '20', '30', '100-200']
> ```

 

<br>

### sort () Method

Method `sort` sorts list in place:

```
vlans = [1, 50, 10, 15]
vlans.sort()

print(vlans)
```

> **Output**:

> ```
> [1, 10, 15, 50]
> ```

 