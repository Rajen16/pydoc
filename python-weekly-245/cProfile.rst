
>>> import cProfile
>>> cProfile.run("[x for x in range(1500)]")
         3 function calls in 0.000 seconds

   Ordered by: standard name

   ncalls  tottime  percall  cumtime  percall filename:lineno(function)
        1    0.000    0.000    0.000    0.000 <string>:1(<module>)
        1    0.000    0.000    0.000    0.000 {method 'disable' of '_lsprof.Profiler' objects}
        1    0.000    0.000    0.000    0.000 {range}

* ncalls is the number of calls made.
* tottime is a total of the time spent in the given function.
* percall refers to the quotient of tottime divided by ncalls
* cumtime is the cumulative time spent in this and all subfunctions. It’s even accurate for recursive functions!
* The second percall column is the quotient of cumtime divided by primitive calls
* filename:lineno(function) provides the respective data of each function
