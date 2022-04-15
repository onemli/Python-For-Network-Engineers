# 2.4 Dictionary

 

Dictionaries are mutable ordered data type:

- data in dictionary are pairs key: value
- values are accessible by key, not by number as in lists
- entries in dictionary stored in order they were added
- since dictionaries are mutable, dictionary items can be changed, added, removed
- key must be an immutable object: number, string, tuple
- value can be data of any type

 

> ***Info:***
>
> *In other programming languages a similar dictionary can be called an associative array, hash, or hash table.*

 

Example of dictionary:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}
```

 

You can write it down like this:

```python
ankara = {
  'id': 1,
  'name': 'Ankara',
  'it_vlan': 320,
  'user_vlan': 1010,
  'mngmt_vlan': 99,
  'to_name': None,
  'to_id': None,
  'port': 'G1/0/11'
}
```

 

In order to get a value from dictionary you have to refer to key in the same way as in lists, only key will be used instead of number:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya'}

print(ankara['name'])
print(ankara['location'])
```

Output:

```python
Ankara
Cankaya
```

 

Similarly, a new key-value pair could be added:

```python
ankara['vendor'] = 'Cisco'

print(ankara)
```

Output:

```python
{'vendor': 'Cisco', 'name': 'Ankara', 'location': 'Cankaya'}
```

 

Or rewritten:

```python
ankara['vendor'] = 'cisco ios'

print(ankara)
```

Output:

```python
{'vendor': 'cisco ios', 'name': 'Ankara', 'location': 'Cankaya'}
```

 

In dictionary you can use a dictionary as a value:

```python
ankara_devices = {
  'r1': {
'hostname': 'ankara_rtr1',
'location': 'Cankaya',
'vendor': 'Cisco',
'model': '4451',
'ios': '15.4',
'ip': '10.255.0.1'
  },

  'r2': {
'hostname': 'ankara_rtr2',
'location': 'Cankaya,
'vendor': 'Cisco',
'model': '4451',
'ios': '15.4',
'ip': '10.255.0.2'
  },

   'sw1': {
'hostname': 'ankara_sw1',
'location': 'Cankaya',
'vendor': 'Cisco',
'model': '3850',
'ios': '3.6.XE',
'ip': '10.255.0.101'
  }
}
```

 

You can get values from nested dictionary by:

```python
print(ankara_devices['r1']['ios'])
print(ankara_devices['r1']['model'])
print(ankara_devices ['sw1']['ip'])
```

Output:

```python
15.4
4451
10.255.0.101
```

 

Function sorted sorts dictionary keys in ascending order and returns a new list with sorted keys:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}

print(sorted(ankara))
```

> Output:
>

> ```python
> ['location', 'name', 'vendor']
> ```
>

 



## 2.4.1 Dictionary Methods

### clear() Method

Method clear allows to clear dictionary:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya'}
ankara.clear()

print(ankara)
```

> Output:
>

> ```python
> {}
> ```
>

 



### copy() Method

Method `copy` allows to create a full copy of dictionary.

If one dictionary is equal to other:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}
ankara2 = ankara

print(id(ankara))
print(id(ankara2))

ankara['vendor'] = 'Juniper'
print(ankara2['vendor'])
```

> Output:
>

> ```python
> 3050637299008
> 3050637299008
> Juniper
> ```
>

 

In this case `ankara2` is another name that refers to dictionary `ankara`. And when you change `ankara` dictionary, `ankara2` dictionary changes as well because it’s a link to the same object.

Therefore, if you want to make a copy of dictionary, use `copy` method:

 

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}
ankara2 = ankara.copy()

print(id(ankara))
print(id(ankara2))

ankara['vendor'] = 'Juniper'
print(ankara2['vendor'])
```

> Output:
>

> ```python
> 1612008262976
> 1612008263040
> Cisco
> ```
>

 



### get() Method

If you query a key that is not present in dictionary, an error occurs:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}

print(ankara['ios'])
```

> Output:
>

> ```python
> Traceback (most recent call last):
>  File "test.py", line 3, in <module>
>   print(ankara['ios'])
> KeyError: 'ios'
> ```
>

 

Method `get()` queries for key and if there is no key, returns None instead.

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}
print(ankara.get('ios'))
```

> Output:
>

> ```python
> None
> ```
>



Method `get()` also allows you to specify another value instead of None:

```python
print(ankara.get('ios', 'Ooops'))
```

> Output:
>

> ```python
> Ooops
> ```
>

 



### setdefault () Method

Method `setdefault` searches for key and if there is no key, instead of error it creates a key with None value.

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}
ios = ankara.setdefault('ios')

print(ios)
print(ankara)
```

> **Output:**

> ```python
> None
> {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco', 'ios': None}
> ```
>

 

If key is present, `setdefault` returns value that corresponds to it:

```python
ankara.setdefault('name')
```

 

The second argument allows to specify which value should correspond to key:

```python
model = ankara.setdefault('model', 'Cisco3580')

print(model)
print(ankara)
```

> **Output:**

> ```python
> Cisco3580
> {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco', 'model': 'Cisco3580'}
> ```
>

 



### keys(), values(), items()

Methods `keys`, `values`, `items`:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}

print(ankara.keys())
print(ankara.values())
print(ankara.items())
```

> **Output**:

> ```python
> dict_keys(['name', 'location', 'vendor'])
> dict_values(['Ankara', 'Cankaya', 'Cisco'])
> dict_items([('name', 'Ankara'), ('location', 'Cankaya'), ('vendor', 'Cisco')])
> ```
>

 

All three methods return special view objects that contains keys, values, and key-value pairs of dictionary, respectively.

A very important feature of view is that they change together with dictionary. And in fact, they just give you a way to look at objects, but they don’t make a copy of them.

Example of using keys:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}
keys = ankara.keys()

print(keys)
```

> **Output:**

> ```python
> dict_keys(['name', 'location', 'vendor'])
> ```
>

 

Now keys variable corresponds to view `dict_keys`, in which three keys: name, location and vendor.

But if we add another key-value pair to dictionary, keys object will also change:

```python
ankara['ip'] = '10.1.1.1'
print(keys)
```

> **Output:**

> ```python
> dict_keys(['name', 'location', 'vendor', 'ip'])
> ```
>

 

If you want to get a simple list of keys that will not be changed with dictionary changes, it is enough to convert view to list:

```python
list_keys = list(ankara.keys())

print(list_keys)
```

**Output:**

> ```python
> ['name', 'location', 'vendor', 'ip']
> ```
>

 



### del() Method

Remove key and value:

```python
ankara = {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco'}
del ankara['name']

print(ankara)
```

> **Output**:

> ```python
> {'location': 'Cankaya', 'vendor': 'Cisco'}
> ```
>

 

 

### update() Method

Method update allows you to add contents of one dictionary to another dictionary:

```python
rtr1 = {'name': 'Ankara', 'location': 'Cankaya'}
rtr1.update({'vendor': 'Cisco', 'ios':'15.2'})

print(rtr1)
```

**Output:**

> ```python
> {'name': 'Ankara', 'location': 'Cankaya', 'vendor': 'Cisco', 'ios': '15.2'}
> ```
>

 

Values can be updated in the same way:

```python
rtr1.update({'name': 'ankara_rtr1', 'ios':'15.4'})
```

> **Output:**

> ```python
> {'name': 'ankara_rtr1', 'location': 'Cankaya', 'vendor': 'Cisco', 'ios': '15.4'}
> ```
>

 

 

## 2.4.2 Dictionary Creation Options

### Literal

A dictionary can be created with help of a literal:

```python
rtr1 = {'model': '4451', 'ios': '15.4'}
```

 



### dict

Construction `dict` allows you to create a dictionary in several ways.

If you use strings as keys you can use this option to create a dictionary:

```python
rtr1 = dict(model='4451', ios='15.4')

print(rtr1)
```

> **Output:**

> ```python
> {'model': '4451', 'ios': '15.4'}
> ```
>

 

The second option of creating a dictionary with `dict()`:

```python
rtr1 = dict([('model','4451'), ('ios','15.4')])

print(rtr1)
```

> **Output:**

> ```python
> {'model': '4451', 'ios': '15.4'}
> ```
>

 



### dict.fromkeys

In a situation where you need to create a dictionary with known keys but so far empty values (or identical values), `fromkeys` method is very convenient:

```python
d_keys = ['hostname', 'location', 'vendor', 'model', 'ios', 'ip']
rtr1 = dict.fromkeys(d_keys)

print(rtr1)
```

> **Output:**

> ```python
> {'hostname': None, 'location': None, 'vendor': None, 'model': None, 'ios': None, 'ip': None}
> ```
>

 

By default `fromkeys` sets `None` value. But you can also pass your own value:

```python
router_models = ['ISR2811', 'ISR2911', 'ISR2921', 'ASR9002']
models_count = dict.fromkeys(router_models, 0)

print(models_count)
```

> **Output:**

> ```python
> {'ISR2811': 0, 'ISR2911': 0, 'ISR2921': 0, 'ASR9002': 0}
> ```
>

 

This option of creating a dictionary is not suitable for all cases. For example, if you use a mutable data type in value, a reference to the same object will be created:

```python
router_models = ['ISR2811', 'ISR2911', 'ISR2921', 'ASR9002']
routers = dict.fromkeys(router_models, [])

print(routers)

routers['ASR9002'].append('london_r1')

print(routers)
```

> **Output:**

> ```python
> {'ISR2811': [], 'ISR2911': [], 'ISR2921': [], 'ASR9002': []}
> {'ISR2811': ['london_r1'], 'ISR2911': ['london_r1'], 'ISR2921': ['london_r1'], 'ASR9002': ['london_r1']}
> ```
>

 