# Multi line to mel in Python

## If we use multi line string format in Python, We may get redundant space in left, for example

```python
def foo(*args, **kwargs):
    result = \ 
    r'''
        string $selections[] = `ls -sl`;
        for ( $select in $selections )
        {
            print($select + "\n");
        }
    '''
    return result

receive = foo()
print receive
```

## It will print below

```python
        string $selection[] = `ls -sl`;
        for ( $select in $selections )
        {
            print($select + "\n");
        }
```

## Got 8 spaces(2tabs) ! although could'nt affect syntax in MEL

---

## We could be use textwrap module

```python
import textwrap

def foo(*args, **kwargs):
    result = \ 
    r'''
        string $selections[] = `ls -sl`;
        for ( $select in $selections )
        {
            print($select + "\n");
        }
    '''
    # Call textwrap.dedent method
    return textwrap.dedent(result)
```

## Solve this problem!