# Python

wroking with and understanding python

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
## Loops
### While loop
code
     
     nums=[1,2,3,4,5]
      n=0
      x=0
      while (n<5):
          n+=1
          x=n+x
          print('when n is {},x is {}'.format(n,x))
          
          
output

      when n is 1,x is 1
      when n is 2,x is 3
      when n is 3,x is 6
      when n is 4,x is 10
      when n is 5,x is 15
### For loop
code

      nums=[1,2,3,4,5]
      n,m=0,0
      x=0
      for n in nums: #by default n+=1
          x=n+x

          print('when n is {},x is {}'.format(n,x))
      for m in nums:
          print(m)
 
 output
 
      when n is 1,x is 1
      when n is 2,x is 3
      when n is 3,x is 6
      when n is 4,x is 10
      when n is 5,x is 15
      1
      2
      3
      4
      5
      
code

      for x in range(0,10,2):
          print(x)

output

      0
      2
      4
      6
      8

## Functions
code

      def add(x,y):
          z=x+y
          return z
      add(100,45)

output

      145
      
      
code (check prime)

      #prime num check
      def prime(x):
          if x<=1:
              return False
          for i in range(2,x):
              if x % i == 0:
                  return False
          else:
              return True

      print(prime(67))

      print(prime(9))

      def listofprimes(x):
          for n in range(2,x):
          print('Following are all the primes till {}'.format(x))
              if prime(n) != False:
                  print(n)
        
            

      listofprimes(100)
  
  

output
      
      True
      False
      Following are all the primes till 100
      2
      3
      5
      7
      11
      13
      17
      19
      23
      29
      31
      37
      41
      43
      47
      53
      59
      61
      67
      71
      73
      79
      83
      89
      97
      

code


      def main():
          x=6
          print("ID of x ",id(x)) #ID of the object x that stores value 6

          dog(x)

      def dog(y):
          print("ID of y ",id(y)) #ID of the object y that also stores 6. x and y are the same objects
          y=7 #Intergers are immutable, after updating y, y become an object of its own
          print("New ID of y ",id(y)) #ID of object y
          print("bark")


      if __name__  is  '__main__': main() #Main body of the program starts here


output


      ID of x  140712643109424
      ID of y  140712643109424
      New ID of y  140712643109456
      bark


## Class and Objects
 
 code
 
       class dinner: #Class container 
          mainCourse= 'Indian Food'
          sweetDish= 'Ice-cream'

          def eat(self):
              print(self.mainCourse)
          def sweet(self):
              print(self.sweetDish)

      HappyMeal = dinner() #Happy Meal is now an object of the class dinner
      HappyMeal.eat()
      HappyMeal.sweet()
    
output

      Indian Food
      Ice-cream


## Types

code

      x=1
      print('x is {}'.format(x))
      print(type(x))
      y=1.0
      print('y is {}'.format(y))
      print(type(y))
      z='1.0'
      print('z is {}'.format(z))
      print(type(z))
      a={2,3,4,5}
      print('a is {}'.format(a))
      print(type(a))
      b=[1,2,3]
      print('b is {}'.format(b))
      print(type(b))
      c=(1,2)
      print('c is {}'.format(c))
      print(type(c))
      
output

      x is 1
      <class 'int'>
      y is 1.0
      <class 'float'>
      z is 1.0
      <class 'str'>
      a is {2, 3, 4, 5}
      <class 'set'>
      b is [1, 2, 3]
      <class 'list'>
      c is (1, 2)
      <class 'tuple'>
      
code

      from decimal import * #importing everything from decimal

      a =Decimal('.10')
      b=Decimal('.30')


      x=.10+.10+.10-.30
      y=a+a+a-b
      print(x, type(x))
      print(y, type(y))

output
float is not precise as it doesnt have a binary representation. hence the output is diferrent when using 'decimal'


      5.551115123125783e-17 <class 'float'>
      0.00 <class 'decimal.Decimal'>
      
### Bool
bool is logical values and expressions
code

      x=True
      print(type(x))
 
output

      <class 'bool'>
      
