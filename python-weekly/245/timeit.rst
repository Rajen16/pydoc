
timeit
===========

Benchmark:

A tool to measure execution time of small code snippets.

Useage

* command line interface
* python interface

Command-line interface
--------------------------

::

  python -m timeit [-n N] [-r N] [-s S] [-t] [-c] [-h] [statement ...]

i.e.
::
  python -m timeit '"-".join(str(n) for n in xrange(20))'
  # function "my_function()" has defined in simple_func.py
  python -m timeit "import simple_func; simple_func.my_function()" 
  
Python Interface
--------------------------

Generic useage

* timeit.Timer(stmt='pass', setup='pass', timer=<dafault_timer>, number=1000000).timeit()
* timeit.timeit(stmt='pass', setup='pass', timer=<dafault_timer>, number=1000000)

In addition, there is another useage, that:
::
  # repeat how many times of the timeit()
  timeit.repeat(stmt='pass', setup='pass', timer=<dafault_timer>, repeat=N, number=1000000)
  

Examples
----------

::

  def test():
    """Stupid test function"""
    L = []
    for i in range(100):
        L.append(i)

  if __name__ == '__main__':
    import timeit
    print(timeit.timeit("test()", setup="from __main__ import test"))


Reference
----------

[1]: http://python.usyiyi.cn/python_278/library/timeit.html

