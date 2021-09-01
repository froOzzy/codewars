## Task
In this little assignment you are given a string of space separated numbers, and have to return the highest and lowest number.

Example:
```python
high_and_low("1 2 3 4 5")  # return "5 1"
high_and_low("1 2 -3 4 5") # return "5 -3"
high_and_low("1 9 3 4 -5") # return "9 -5"
```
Notes:

- All numbers are valid Int32, no need to validate them.
- There will always be at least one number in the input string.
- Output string must be two numbers separated by a single space, and highest number is first.

## Simple solution
```python
def high_and_low(numbers):
    list_numbers = [int(item) for item in numbers.split()]
    return '{} {}'.format(max(list_numbers), min(list_numbers))
```
