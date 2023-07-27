# Caching Project

## Background

In this project, you will learn about different caching algorithms and implement them in Python. The goal is to create a caching system that stores frequently accessed data in a faster-accessible storage (cache), thereby improving overall system performance.

## Learning Objectives

By the end of this project, you will be able to explain the following concepts without the help of external resources:

- What a caching system is
- FIFO (First In, First Out) cache replacement policy
- LIFO (Last In, First Out) cache replacement policy
- LRU (Least Recently Used) cache replacement policy
- MRU (Most Recently Used) cache replacement policy
- LFU (Least Frequently Used) cache replacement policy
- The purpose of a caching system
- The limitations of a caching system

## Requirements

### Python Scripts

- All Python files will be interpreted/compiled on Ubuntu 18.04 LTS using Python 3 (version 3.7).
- All Python files should end with a new line.
- The first line of all Python files should be `#!/usr/bin/env python3`.
- Your code should follow the `pycodestyle` style guide (version 2.5).
- All Python files must be executable.
- The length of your files will be tested using `wc`.
- All modules, classes, and functions should have appropriate documentation.

### BaseCaching Class

All cache classes must inherit from the `BaseCaching` class defined below:

```python
class BaseCaching():
    """ BaseCaching defines:
      - constants of your caching system
      - where your data are stored (in a dictionary)
    """
    MAX_ITEMS = 4

    def __init__(self):
        """ Initialize the caching system
        """
        self.cache_data = {}

    def print_cache(self):
        """ Print the contents of the cache
        """
        print("Current cache:")
        for key in sorted(self.cache_data.keys()):
            print("{}: {}".format(key, self.cache_data.get(key)))

    def put(self, key, item):
        """ Add an item to the cache
        """
        raise NotImplementedError("put must be implemented in your cache class")

    def get(self, key):
        """ Get an item from the cache by key
        """
        raise NotImplementedError("get must be implemented in your cache class")

