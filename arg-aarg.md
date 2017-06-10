# Explaining the arg & kwargs argument in Python


In Python, when we pass arguments into a method, there are two native arguments called \*args & \**kwargs

Writing \*args & \**kargs is just a convention, technically we just need to define the asterisks, the variable name can be anything

### \*args

\*args is used when we want to pass an *unknown* amount of **un-named** variables after the initial variable. Since we don't know how many arguments the user will eventually pass to the function, we use \*args then any arguments that come after that gets passed in

```Python
def test_var_args(f_arg, *argv):
    print "first normal arg:", f_arg
    for arg in argv:
        print "another arg through *argv :", arg

test_var_args('yasoob','python','eggs','test')

RESULT:

first normal arg: yasoob
another arg through *argv : python
another arg through *argv : eggs
another arg through *argv : test

```
### \**kargs

\**kargs is used when we want to pass **named** variables such as list or dictionary into the function.

```python
def greet_me(**kwargs):
    if kwargs is not None:
        for key, value in kwargs.iteritems():
            print "%s == %s" %(key,value)

>>> greet_me(name="yasoob")
name == yasoob
```

### Using \*args & \**kargs in function call

We can also call \*args or \**kargs in function calls when we have variables that comply to the amount of arguments defined in the function definition

```python

# first with *args
>>> args = ("two", 3,5)
>>> test_args_kwargs(*args)
arg1: two
arg2: 3
arg3: 5

# now with **kwargs:
>>> kwargs = {"arg3": 3, "arg2": "two","arg1":5}
>>> test_args_kwargs(**kwargs)
arg1: 5
arg2: two
arg3: 3

```
