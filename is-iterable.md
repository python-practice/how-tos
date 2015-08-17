## How to check whether an object is an iterable?

Check whether it has the *\__iter\__* method. Doesn't work for strings
```
def is_iterable(obj):
    return hasattr(obj, '__iter__')
```
You can make an additional check is the object is a string
```
def is_iterable(obj):
    return isinstance(obj, str) or hasattr(obj, '__iter__')
```
Alternatively, you can try to see if it supports iteration. This would work with strings as well:
```
def is_iterable(obj):
    try:
        iter(obj)
        return True
    except TypeError as err:
        return False
```
