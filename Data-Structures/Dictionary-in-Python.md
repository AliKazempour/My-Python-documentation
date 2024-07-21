# Python Dictionary Documentation

A dictionary in Python is an unordered collection of items. Each item is a key-value pair, where each key is unique.

## Creating a Dictionary

```python
# Empty dictionary
my_dict = {}

# Dictionary with integer keys
my_dict = {1: 'apple', 2: 'orange'}

# Dictionary with mixed keys
my_dict = {'name': 'John', 1: [2, 4, 3]}

# Using the dict() method
my_dict = dict({1: 'apple', 2: 'orange'})

# Using the dict() method with pairs
my_dict = dict([(1, 'apple'), (2, 'orange')])
```

## Accessing Elements

```python
# Accessing values using keys
my_dict = {'name': 'Ali', 'age': 20}

print(my_dict['name'])  # Output: Ali
print(my_dict.get('age'))  # Output: 20
```

## Adding and Modifying Elements

```python
# Adding a new key-value pair
my_dict['address'] = 'Pirouzi'

# Modifying an existing key-value pair
my_dict['age'] = 19

print(my_dict)   # Output : {'name': 'Ali', 'age': 19, 'address': 'Pirouzi'}

```

## Removing Elements

```python
# Using pop() to remove an item by key
my_dict.pop('age')  # Output: 19

# Using popitem() to remove the last item
my_dict.popitem()  # Output: ('address', 'Pirouzi')


# Using del to remove a key-value pair
del my_dict['name']

# Using clear() to remove all items
my_dict.clear()
```

## Dictionary Methods

- `dict.clear()`: Removes all items from the dictionary.
- `dict.copy()`: Returns a shallow copy of the dictionary.
- `dict.fromkeys(seq[, v])`: Creates a new dictionary with keys from `seq` and values set to `v`.
- `dict.get(key[, default])`: Returns the value for `key` if `key` is in the dictionary, else `default`.
- `dict.items()`: Returns a view object of dictionary's (key, value) tuple pairs.
- `dict.keys()`: Returns a view object of dictionary's keys.
- `dict.pop(key[, default])`: Removes the item with `key` and returns its value or `default` if `key` is not found.
- `dict.popitem()`: Removes and returns a (key, value) pair from the dictionary.
- `dict.setdefault(key[, default])`: Returns the value of `key`. If `key` does not exist, insert `key` with a value of `default`.
- `dict.update([other])`: Updates the dictionary with elements from another dictionary object or from an iterable of key-value pairs.
- `dict.values()`: Returns a view object of dictionary's values.

## Example Usage

```python
# Creating a dictionary
my_dict = {'name': 'Ali', 'age': 25, 'job': 'Engineer'}

# Accessing elements
print(my_dict['name'])  # Output: Ali

# Adding and modifying elements
my_dict['age'] = 26
my_dict['city'] = 'New York'

# Removing elements
my_dict.pop('job')

# Dictionary methods
keys = my_dict.keys()  # Output: dict_keys(['name', 'age', 'city'])
values = my_dict.values()  # Output: dict_values(['Ali', 26, 'New York'])
items = my_dict.items()  # Output: dict_items([('name', 'Ali'), ('age', 26), ('city', 'New York')])

# Copying a dictionary
new_dict = my_dict.copy()

# Clearing a dictionary
my_dict.clear()
```
