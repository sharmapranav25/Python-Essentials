# Python-Essentials
Essential Knowledge to work with python

## Print Function
code
      
      #The Print Function
       print("hello world")
       print('hi world')
output

    hello world
    hi world
  
code

    a=2
    b=4
    c=a+b
    print('{}'.format(a))
    print('' + str(b)) #str(b) converts int to string form

    print(c) 
    
output

    2
    4
    6
## Import

    import platform
    print('this is pythonn version {}'.format(platform.python_version()))
    
output

    this is pythonn version 3.7.6
## IF condition
code

      x=300
      y=400

      if x<y:
          print('hello')
          print("prints as the condition is true")


      z=x
      x=y
      y=z #swapped x and y

      print(x); print(y) #';' can be used to write multiple statements in the same line

      if x<y:
          print('hello')
          print("prints as the condition is true")
      print("didn't prrint the above as the condition wasn't true") 
      
  output
  
      hello
      prints as the condition is true
      400
      300
      didn't prrint the above as the condition wasn't true
