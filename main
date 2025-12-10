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
