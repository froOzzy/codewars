## Task
Write a function named `repeater()` that takes two arguments (a string and a number), and returns a new string where the input string is repeated that many times.

## Example
```python
Repeater.repeat("a", 5)
```
should return
```python
"aaaaa"
```

## Sample solution
```python
def repeater(string, n):
    return string * n
```
