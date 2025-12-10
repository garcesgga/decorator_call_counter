A decorator in Python is used to **add extra behavior to a function without changing its original code**, like wrapping it with logging, timing, or access control.

# Call Counter Decorator
A simple Python decorator that counts how many times a function has been called and logs the count.

# Example
```python
def call_counter(func):
    counter = 0
    def wrapper(*args, **kwargs):
        nonlocal counter
        counter += 1
        if counter == 1:
            print(f"[INFO] Function {func.__name__} called {counter} time")
        else:
            print(f"[INFO] Function {func.__name__} called {counter} times")
        return func(*args, **kwargs)
    return wrapper

@call_counter
def sum(a, b):
    return a + b

(sum(2, 3))
(sum(5, 7))
