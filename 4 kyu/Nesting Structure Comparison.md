# Task
Complete the function/method (depending on the language) to return `true`/`True` when its argument is an array that has the same nesting structures and same corresponding length of nested arrays as the first array.

For example:
```python
# should return True
same_structure_as([ 1, 1, 1 ], [ 2, 2, 2 ] )
same_structure_as([ 1, [ 1, 1 ] ], [ 2, [ 2, 2 ] ] )

# should return False 
same_structure_as([ 1, [ 1, 1 ] ], [ [ 2, 2 ], 2 ] )
same_structure_as([ 1, [ 1, 1 ] ], [ [ 2 ], 2 ] )

# should return True
same_structure_as([ [ [ ], [ ] ] ], [ [ [ ], [ ] ] ] )

# should return False
same_structure_as([ [ [ ], [ ] ] ], [ [ 1, 1 ] ] )
```

# Simple solution
```python
import re


def same_structure_as(original,other):
    pattern = r'([-]*\w+|\'[-\w\[\]]+\')'
    if re.sub(pattern, '', str(original)) != re.sub(pattern, '', str(other)):
        return False
    
    return True
```
