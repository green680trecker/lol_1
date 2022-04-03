def print_log(func):

    def wrapper(x, y):
        print("some_func была выполнена")
        result = func(x, y)
        return result
    return wrapper
@print_log
def some_func(x, y):
    return x * y

print(some_func(2, 5))
