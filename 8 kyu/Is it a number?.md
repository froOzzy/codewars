## Task
Given a string s, write a method (function) that will return true if its a valid single integer or floating number or false if its not.

Valid examples, should return true:
```python
isDigit("3")
isDigit("  3  ")
isDigit("-3.23")
```
should return false:
```python
isDigit("3-4")
isDigit("  3   5")
isDigit("3 5")
isDigit("zero")
```

## Sample solution
```python
def isDigit(string):
  try:
    float(string)
  except:
    return False
  
  return True
```
