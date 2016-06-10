
Decorator
===========

useages
---------

Decorator without args
-----------------------
::

  @dec
  def function(arg1, arg2):
      pass
    
Example::

  # dec_no_arg.py
  def dec(function):
      def _inter_dec(arg1, arg2):
          arg2=arg1+arg2
          function(arg1, arg2)
      return _inter_dec
  
  @dec
  def function(arg1, arg2):
      print (arg1, arg2)
  
  function("arg1", "arg2")
  
  ## result
  ## root@node-233:/tmp# python dec_no_arg.py
  ## ('arg1', 'arg1arg2')

Decorator with args    
---------------------

::

  @dec(arg_dec)
  def function(arg1, arg2):
      pass
    
Example::

  # dec_with_arg.py
  def dec(arg_dec):
      def _inter_dec(function):
          def _inter_inter_dec(arg1, arg2):
              arg2=arg_dec+arg1+arg2
              arg1=arg_dec+arg1
              function(arg1, arg2)
          return _inter_inter_dec
      return _inter_dec
  
  @dec("pre_")
  def function(arg1, arg2):
      print (arg1, arg2)
  
  
  function("arg1", "arg2")
  
  ## result
  ## root@node-233:/tmp# python dec_with_arg.py
  ## ('pre_arg1', 'pre_arg1arg2')

