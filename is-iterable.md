## How to check whether an object is an iterable?

Check whether it has the *\__iter\__* method. 
```
def is_iterable(obj):
    return hasattr(obj, '__iter__')
```
However, this approach doesn't work for strings.
But you can make an additional check. Like so:
```
def is_iterable(obj):
    return isinstance(obj, str) or hasattr(obj, '__iter__')
```
Alternatively, you can try and see if it does support iteration. This would work for strings as well:
```
def is_iterable(obj):
    try:
        iter(obj)
        return True
    except TypeError as err:
        return False
```
