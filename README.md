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
## Conditionals
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
      print("didn't print the above as the condition wasn't true") 
      
output
  
      hello
      prints as the condition is true
      400
      300
      didn't print the above as the condition wasn't true
     
code
 
      x=1
      y=2

      if x>y:
          print('{} is greater than {}'.format(x,y))
      elif x<y: #can have multiple elif
          print('{} is less than {}'.format(x,y))
      else:
          print('{} and {} are equal'.format(x,y))

output

      1 is less than 2
      
code

      x=10
      y=2
      z=x+y

      if z==10:
          print('z is 10')
      elif z==15:
          print('z is 15')
      elif z==11:
          print('z is 11')
      elif z==(x+y):
          if x<y: #condition within condition
              print('y is greater')
          else:
              print('x is greater')
          print('x+y is {}'.format(z))
          
 output

      x is greater
      x+y is 12
