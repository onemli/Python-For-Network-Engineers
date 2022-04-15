 

When sorting data like list of lists or list of tuples, sorted sorts by the first element of nested lists (tuples), and if the first element is the same, on the second:

```
data = [[1, 100, 1000], [2, 2, 2], [1, 2, 3], [4, 100, 3]]
print(sorted)
```

 

Output:

```
[[1, 2, 3], [1, 100, 1000], [2, 2, 2], [4, 100, 3]]
```

 

If the sort is done for a list of numbers that are written as strings, the sort will be lexicographic, not natural, and the order will be:

```
vlans = ['1', '30', '11', '3', '10', '20', '30', '100']
print(sorted(vlans))
```

 

Output:

```
['1', '10', '100', '11', '20', '3', '30', '30']
```

 

For the sorting to be “correct” it is necessary to convert vlans to numbers.

 

The same problem appears, for example, with IP addresses:

```
ip_list = ["10.1.1.1", "10.1.10.1", "10.1.2.1", "10.1.11.1"]
print(sorted(ip_list))
```

Output:

```
['10.1.1.1', '10.1.10.1', '10.1.11.1', '10.1.2.1']
```

 