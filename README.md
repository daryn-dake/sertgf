import time

def measure_time(func, *args):
    start_time = time.time()  
    result = func(*args)      
    end_time = time.time()    
    return result, end_time - start_time  

def slow_addition(a, b):
    time.sleep(1)  
    return a + b
def fast_exponentiation(base, exponent):
    return base ** exponent
def noop():
    pass
def test():
    result, time_taken = measure_time(slow_addition, 5, 7)
    print(result, time_taken)
    result, time_taken = measure_time(fast_exponentiation, 2, 10)
    print(result, time_taken)
    result, time_taken = measure_time(noop)
    print(result, time_taken)
test()
