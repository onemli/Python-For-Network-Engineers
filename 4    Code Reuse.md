# 4    Code Reuse

 

# 4.1    Functions

 

Function:

 

§ has a name to run this code block as many times as you want

o  launch of function code is called a function call

§ function parameters are usually defined when creating a function.

o  function parameters determine which arguments a function can accept

o  arguments can be passed to functions

o  function code will be executed taking into account the specified arguments

 

What are functions for?

 

Typically, problems that code solves are very similar and often have something in common. For example, when working with configuration files each time it is necessary to perform such actions:

 

§ file opening

§ deletion (or skipping) of lines starting with exclamation mark (for Cisco)

§ deleting (or skipping) empty lines

§ deleting new line characters at the end of lines

§ converting the result to a list

 

Beyond that, actions can vary depending on what needs to be done.

 

Often there’s a piece of code that repeats itself. Of course, you can copy it from one script to another. But this is very inconvenient because when you change code you have to update it in all files in which it is copied.

 

It is much easier and more accurate to put this code into a function (it can also be several functions). And then you will call this function - in this file or another one. This section discusses when a function is in the same file. And in 11. Modules we will see how to reuse objects that are in other scripts.

 



 

## 4.1.1   Creation of Functions

 

Creation of function:

 

§ functions are created with a reserved word def

§ def followed by function name and parentheses

§ parameters that function accepts inside parentheses

§ after parentheses goes colon and from a new line with indent there is a block of code that function executes

§ optionally, the first line can be docstring

§ function can use return operator

o  it is used to terminate and exit a function

o  most often return operator returns some value

 

Example of function:

```
def configure_intf(intf_name, ip, mask):

  print('interface', intf_name)

  print('ip address', ip, mask)
```

 

Function configure_intf creates an interface configuration with specified name and IP address. Function has three parameters: intf_name, ip, mask. When function is called the real data will replace these parameters.

 

> ***Info:***
>
> *When function is created, it does nothing yet. Actions listed in it will be executed only when you call function. This is something like ACL in network equipment: when creating ACL in configuration, it does nothing until it is applied.*

 

### 4.1.1.1   Function Call

 

When calling a function you must specify its name and pass arguments if necessary.

 

> ***Note:***
>
> *Parameters are variables that are used to create a function. Arguments are the actual values (data) that are passed to functions when called.*

 

Function configure_intf expects three values when called because it was created with three parameters:

```
configure_intf('F0/0', '10.1.1.1', '255.255.255.0')
```

 

> **Output**:

> ```
> interface F0/0
> 
> ip address 10.1.1.1 255.255.255.0
> ```

 

The current version of the configure_intf function prints commands to a standard output, commands can be seen but the result of function cannot be saved to a variable.

 



 

If you try to write the result of the configure_intf function to a variable, the value of the variable will be None:

```
result = configure_intf('Fa0/0', '10.1.1.1', '255.255.255.0') 

print(result)
```

 

> **Output**:

> ```
> interface Fa0/0
> 
> ip address 10.1.1.1 255.255.255.0
> 
> None
> 
>  
> 
> 
> ```

For a function to return a value, use return operator.

 

### 4.1.1.2   Operator Return

 

Operator return is used to return a value, and at the same time it exits the function. Function can return any Python object. By default, function always returns None.

 

In order for configure_intf function to return a value that can then be assigned to a variable, you must use return operator:

```
def configure_intf(intf_name, ip, mask):

  config = f'interface {intf_name}\nip address {ip} {mask}'

   return config

 

result = configure_intf('Fa0/0', '10.1.1.1', '255.255.255.0')

print(result)

 
```

> **Output:**

> ```
> interface Fa0/0
> 
> ip address 10.1.1.1 255.255.255.0
> ```

 

Now the result variable contains a line with commands to configure interface. In real life, function will almost always return some value.

 

Another important aspect of return operator is that after return the function closes, meaning that the expressions that follow return are not executed.

 

For example, in function below the line «Configuration is ready» will not be displayed because it stands after return:

```
def configure_intf(intf_name, ip, mask):

  config = f'interface {intf_name}\nip address {ip} {mask}'

  return config

  print('Configuration is ready')

 

print(configure_intf('Fa0/0', '10.1.1.1', '255.255.255.0'))
```

 

> **Output:**

> ```
> interface Fa0/0
> 
> ip address 10.1.1.1 255.255.255.0
> ```

 

Function can return multiple values. In this case, they are separated by a comma after return operator. In fact, function returns tuple:

```
def configure_intf(intf_name, ip, mask):

  config_intf = f'interface {intf_name}\n'

  config_ip = f'ip address {ip} {mask}'

  return config_intf, config_ip

 

result = configure_intf('Fa0/0', '10.1.1.1', '255.255.255.0')

 

print(result)

print(type(result))
```

 

> **Output:**

> ```
> ('interface Fa0/0\n', 'ip address 10.1.1.1 255.255.255.0')
> 
> <class 'tuple'>
> ```

 

# 4.2   Scope of Variables

 

Variables in Python have a scope. Depending on location in code where variable has been defined, scope is also defined, it determines where variable will be available.

 

When using variable names in a program, Python searches, creates or changes these names in the corresponding namespace each time. Namespace that is available at each moment depends on area in which code is located.

 

Python has a LEGB rule that it uses for variables search. For example, when accessing a variable within a function, Python searches for a variable in this order in scopes (before the first match):

 

§ L (local) - in local (within function)

§ E (enclosing) - in local area of outer functions (these are functions within which our function is located)

§ G (global) - in global (in script)

§ B (built-in) - in built-in (reserved Python values)

Accordingly, there are local and global variables:

 

§ local variables:

o  variables that are defined within function

o  these variables become unavailable after exit from function

§ global variables:

o  variables that are defined outside the function

o  these variables are ‘global’ only within a module

o  for example, to be available in another module they must be imported

Example of local intf_config:

```
def configure_intf(intf_name, ip, mask):

  intf_config = f'interface {intf_name}\nip address {ip} {mask}'

  return intf_config

  

print(intf_config)
```

 

 

> **Output:**

> ```
> Traceback (most recent call last):
> 
>  File "namespace.py", line 4, in <module>    
> 
>   print(intf_config)
> 
> NameError: name 'intf_config' is not defined
> ```



 

## 4.2.1   Function Parameter and Types

 

Parameters are variables that are used when creating a function. When creating a function you can specify which arguments must be passed and which must not. Accordingly, a function can be created with:

§ required parameters

§ optional parameters (with default values)

 

### 4.2.1.1   Required Parameters

 

Required parameters - determine which arguments must be passed to functions. At the same time, they need to be passed exactly as many as parameters of function are specified (you cannot specify more or less)

Function with mandatory parameters (func_params_types.py file):

```
def check_passwd(username, password):

  if len(password) < 8:

​    print('Password is too short')

​    return False

  elif username in password:

​    print('Password contains username')

​    return False

  else:

​    print(f'Password for user {username} has passed all checks')

​     return True
```

​    

Function check_passwd() expects two arguments: username and password.

 

Function checks password and returns False if checks fail and True if password passed all checks:

```
print(check_passwd('keremcan', '12345'))

print(check_passwd('keremcan', '12345lsdkjflskfdjskeremcan'))

print(check_passwd('keremcan', '12345lsdkjflskfdjs'))
```

 



 

### 4.2.1.2  Optional Parametes

 

When creating a function you can specify default value for parameter in this way: def check_passwd(username, password, min_length=8). In this case, min_length option is specified with default value and may not be passed when a function is called.

 

Example of a check_passwd function with default parameter (func_check_passwd_optional_param.py file):

```
def check_passwd(username, password, min_length=8):

  if len(password) < min_length:

​    print('Password is too short')

​    return False

  elif username in password:

​    print('Password contains username')

​    return False

  else:

​    print(f'Password for user {username} has passed all checks')

​    return True
```

 

Since min_length parameter has a default value the corresponding argument can be omitted when a function is called if default value fits you:

print(check_passwd('keremcan', '12345'))

 

> **Output:**

> ```
> Password is too short
> 
> False
> ```

 

If you want to change default value:

```
print(check_passwd('keremcan', '12345', 3))
```

 

> **Output:**

> ```
> Password for user keremcan has passed all checks
> 
> True
> ```

 

## 4.2.2   Function Argument Types

 

When a function is called the arguments can be passed in two ways:

 

as positional - passed in the same order in which they are defined at creation of function. That is, the order in which arguments are passed determines what value each argument will receive.

as keyword - passed with argument name and its value. In such a case, arguments can be stated in any order as their name is clearly indicated.

Positional and keyword arguments can be mixed when calling a function. That is, it is possible to use both methods when passing arguments of the same function. In this process, Positional arguments must be indicated before keyword arguments.

 

Look at different ways to pass arguments using check_passwd (func_check_check_passwd_optional_param.py file):

 

```
def check_passwd(username, password, min_length=8):

  if len(password) < min_length:

​    print('Password is too short')

​    return False

  elif username in password:

​    print('Password contains username')

​    return False

  else:

​    print(f'Password for user {username} has passed all checks')

​    return True
```

 

### 4.2.2.1   Positional Arguments

 

Positional arguments when calling a function must be passed in the correct order (therefore they are called positional arguments).

 

```
check_passwd('keremcan', '12345',4)
```

 

> **Output:**

> ```
> Password for user keremcan has passed all checks
> ```

 

### 4.2.2.2   Keyword Arguments

 

Keyword arguments:

§ are passed with name of argument

§ thus they can be passed in any order

If both arguments are keyword, they can be passed in any order:

```
check_passwd(password='12345', username='keremcan', min_length=4)
```

 

> ***Info:***
>
> *Please note that first there should always be positional arguments and then keyword arguments.*
>
>  
>

If you do the opposite, there’s an error:

```
check_passwd(password='12345', username='keremcan', 4)

 
```

> **Output:**

> ```
>  File "arguments.py", line 11
> 
>   check_passwd(password='12345', username='keremcan', 4)
> 
> ​                          ^
> 
> SyntaxError: positional argument follows keyword argument
> ```

 

But in that combination it works:

```
check_passwd('keremcan', password='12345', min_length=3)
```

 

> **Output:**

> ```
> Password for user keremcan has passed all checks
> ```

 

### 4.2.2.3   Variable Length Positional Arguments

 

Sometimes it is necessary to make function accept not a fixed number of arguments, but any number. For such a case, in Python it is possible to create a function with a special parameter that accepts variable length arguments. This parameter can be both keyword and positional.

 

Parameter that takes positional variable length arguments is created by adding an asterisk before parameter name. Parameter can have any name but by agreement *args is the most common name.

 

Example of a function:

```
def sum_arg(a, *args):

  print(a, args)

  return a + sum(args)

 

print(sum_arg(1, 10, 20, 30))
```

Function sum_arg is created with two parameters:

 

§ parameter a

o  if passed as positional argument, should be first

o  if passed as a keyword argument, the order does not matter

§ parameter *args - expects variable length arguments

o  all other arguments as a tuple

o  these arguments may be missed

Output:

1 (10, 20, 30)

61

 

You can also create such a function:

def sum_arg(*args):

  print(args)

  return sum(args)

 

> **Output:**

> ```
> (1, 10, 20, 30)
> 
> 61
> ```

 

### 4.2.2.4   Variable Length Keyword Arguments

 

Parameter that accepts keyword variable length arguments is created by adding two asterisk in front of parameter name. Name of parameter can be any but by agreement most commonly use name **kwargs (from keyword arguments).

 

Example of a function:

```
def sum_arg(a, **kwargs):

  print(a, kwargs)

  return a + sum(kwargs.values())
```

 

Function sum_arg is created with two parameters:

§ parameter a

o  if passed as positional argument, should be first

o  if passed as a keyword argument, the order does not matter

§ parameter **kwargs - expects keyword variable length arguments

o  all other keyword arguments as a dictionary

o  these arguments may be missed

Calling a function with different number of keyword arguments:

```
print(sum_arg(a=10, b=10, c=20, d=30))

 

print(sum_arg(b=10, c=20, d=30, a=10))
```

 

> **Output:**

> ```
> 10 {'b': 10, 'c': 20, 'd': 30}
> 
> 70
> 
>  
> 
> 10 {'b': 10, 'c': 20, 'd': 30}
> 
> 70
> ```

 

### 4.2.2.5   Unpacking Positional Arguments

 

In Python the expressions *args and **kwargs allow for another task - unpacking arguments.

 

So far we’ve called all functions manually. Hence, we passed on all relevant arguments.

 

In reality, it is usually necessary to pass data to function programmatically. And often data comes in the form of a Python object.

 

For example, when formatting strings you often need to pass multiple arguments to format method. And often these arguments are already in list or tuple. To pass them to format method you have to use indexes:

```
items = [1, 2, 3]

 

print('One: {}, Two: {}, Three: {}'.format(items[0], items[1], items[2]))
```

 

> **Output:**

> ```
> One: 1, Two: 2, Three: 3
> ```

 

Instead, you can take advantage of unpacking argument and do this:

```
items = [1, 2, 3]

 

print('One: {}, Two: {}, Three: {}'.format(*items))
```

 

> **Output:**

> ```
> One: 1, Two: 2, Three: 3
> ```

 



 

Another example is config_interface function:

```
def config_interface(intf_name, ip_address, mask):

  interface = f'interface {intf_name}'

  no_shut = 'no shutdown'

  ip_addr = f'ip address {ip_address} {mask}'

  result = [interface, no_shut, ip_addr]

  return result
```

 

Function expects such arguments:

 

§ intf_name - interface name

§ ip_address - IP address

§ mask - subnet mask

Function returns a list of strings to configure interface:

```
print(config_interface('Fa0/1', '10.0.1.1', '255.255.255.0'))

print(config_interface('Fa0/10', '10.255.4.1', '255.255.255.0'))
```

 

> **Output:**

> ```
> ['interface Fa0/1', 'no shutdown', 'ip address 10.0.1.1 255.255.255.0']
> 
> ['interface Fa0/10', 'no shutdown', 'ip address 10.255.4.1 255.255.255.0']
> ```

 

Suppose you call a function and pass it information that has been obtained from another source, for example from database. For example, interfaces_info list contains parameters for configuring interfaces:

```
interfaces_info = [

  ['Fa0/1', '10.0.1.1', '255.255.255.0'],

  ['Fa0/2', '10.0.2.1', '255.255.255.0'],

  ['Fa0/3', '10.0.3.1', '255.255.255.0'],

  ['Fa0/4', '10.0.4.1', '255.255.255.0'],

  ['Lo0', '10.0.0.1', '255.255.255.255']]
```

 

If you go through list in the loop and pass nested list as a function argument, an error will occur:

```
for info in interfaces_info:

  print(config_interface(info))
```

 

> **Output:**

> ```
>   print(config_interface(info))
> 
> TypeError: config_interface() missing 2 required positional arguments: 'ip_address' and 'mask'
> 
>  
> ```

Error is quite logical: function expects three arguments and it is given 1 argument - a list. In such a situation it is necessary to unpack arguments. Just add * before passing the list as an argument and there is no error anymore:

```
for info in interfaces_info:

  print(config_interface(*info))
```

 

> **Output:**

> ```
> ['interface Fa0/1', 'no shutdown', 'ip address 10.0.1.1 255.255.255.0']
> 
> ['interface Fa0/2', 'no shutdown', 'ip address 10.0.2.1 255.255.255.0']
> 
> ['interface Fa0/3', 'no shutdown', 'ip address 10.0.3.1 255.255.255.0']
> 
> ['interface Fa0/4', 'no shutdown', 'ip address 10.0.4.1 255.255.255.0']
> 
> ['interface Lo0', 'no shutdown', 'ip address 10.0.0.1 255.255.255.255']
> 
> 
> ```

 

### 4.2.2.6   Unpacking Keyword Arguments

 

Similarly, you can unpack dictionary to pass it as keyword arguments.

 

Check_passwd function:

```
def check_passwd(username, password, min_length=8, check_username=True):

  if len(password) < min_length:

​    print('Password is too short')

​    return False

  elif check_username and username in password:

​    print('Password contains username')

​    return False

  else:

​    print(f'Password for user {username} has passed all checks')

​    return True
```

 

List of dictionaries username_passwd where username and password are specified:

```
username_passwd = [{'username': 'cisco', 'password': 'cisco'},

​          {'username': 'keremcan', 'password': 'keremcanpass'},

​          {'username': 'user', 'password': '123456789'}]

 
```

If you pass dictionary to check_passwd function, there is an error:

```
for data in username_passwd:

  check_passwd(data)
```

 

> **Output:**

> ```
>   check_passwd(data)
> 
> TypeError: check_passwd() missing 1 required positional argument: 'password'
> ```

 

Error is because the function has taken dictionary as one argument and believes that it lacks only password argument.

 

If you add ** before passing a dictionary to function, function will work properly:

```
for data in username_passwd:

  check_passwd(**data)
```

 

> **Output:**

> ```
> Password is too short
> 
> Password contains username
> 
> Password for user user has passed all checks
> 
>  
> ```

Python unpacks dictionary and passes it to function as keyword arguments. The check_passwd(**data) is converted to a check_passwd(username='cisco', password='cisco').

 



 

