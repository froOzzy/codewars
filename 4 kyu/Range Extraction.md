## Task
A format for expressing an ordered list of integers is to use a comma separated list of either

- individual integers
- or a range of integers denoted by the starting integer separated from the end integer in the range by a dash, '-'. The range includes all integers in the interval including both endpoints. It is not considered a range unless it spans at least 3 numbers. For example "12,13,15-17"
Complete the solution so that it takes a list of integers in increasing order and returns a correctly formatted string in the range format.

Example:
```
solution([-6, -3, -2, -1, 0, 1, 3, 4, 5, 7, 8, 9, 10, 11, 14, 15, 17, 18, 19, 20])
# returns "-6,-3-1,3-5,7-11,14,15,17-20"
```

## Simple solution
```python
def get_next_index(elem, args):
    for index, item in enumerate(args):
        if item == elem + 1:
            elem += 1
            continue
        else:
            return index + 1
    
    return index + 2


def solution(args):
    current_index = 0
    len_args = len(args) - 1
    result = []
    for index, item in enumerate(args):
        if index != current_index:
            continue

        if index < len_args:
            next_index = get_next_index(item, args[index + 1:])
            if next_index - 2 > 0:
                current_index = next_index + index
                result.append('{}-{}'.format(item, args[current_index - 1]))
            else:
                current_index = index + 1
                result.append(str(item))
        else:
            result.append(str(item))
    
    return ','.join(result)
        
```
