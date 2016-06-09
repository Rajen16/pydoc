

with ... as ...
================

A Context Manager.

Generic Usage
----------------
::

  with EXPRESSION [ as VARIABLE] WITH-BLOCK
  

The `EXPRESSION` object must include two methods:

* __enter__()
* __exit__()

::
  
  After `EXPRESSION` is handled, it will call the `__enter__()` method
  and return the result to the variable next to `as` .
  When the code block is executed, it will call the `__exit__()` method.
  
Example
---------------

Creating a Timer Context Manager

::

  import random
  import time

  class MyTimer():
      
      def __init__(self):
          self.start = time.time()
          
      def __enter__(self):
          return self
          
      def __exit__(self):
          end = time.time()
          long_time = end - self.start
          print ("The function hold %s time" %long_time)
          
  def long_run():
      for x in range(5):
          time_sleep = random.choice(range(1,10))
          time.sleep(time_sleep)
  
  with MyTimer():
      long_run()
