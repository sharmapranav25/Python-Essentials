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
  
code 2

    a=2
    b=4
    c=a+b
    print('{}'.format(a))
    print('' + str(b)) #str(b) converts int to string form

    print(c) 
    
output 2

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
     
code 2
 
      x=1
      y=2

      if x>y:
          print('{} is greater than {}'.format(x,y))
      elif x<y: #can have multiple elif
          print('{} is less than {}'.format(x,y))
      else:
          print('{} and {} are equal'.format(x,y))

output 2

      1 is less than 2
      
code 3

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
          
 output 3

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
      
code 2

      for x in range(0,10,2):
          print(x)

output 2

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
      
      
code 2 (check prime)

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
  
  

output 2
      
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
      

code 3


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


output 3


      ID of x  140712643109424
      ID of y  140712643109424
      New ID of y  140712643109456
      bark



code 4


      def main():
          x=("cute",'paw','good boi')
          dog(*x)

      def dog(*args):
          if len(args):
              for i in args:
                  print(i)
          else:
              print('bark')
    
      if __name__ is '__main__': main()


output 4

      cute
      paw
      good boi
      
      
code 5
 
      def main():
          x=dict(cute='doggo',doggo='paw',who ='is a good boi')
          dog(**x)

      def dog(**kwargs):
          if len(kwargs):
              for k in kwargs:
                  print("{} {}".format(k,kwargs[k]))
          else:
              print('barl')

      if __name__ is '__main__': main()
      
      
      
output 5


      cute doggo
      doggo paw
      who is a good boi

### Genertor
code:


      #inclusive range
      def main():
          for i  in inclusive_range(100,60,4,):
                  print(i, end=' ') #prints in one line
                  
          print()
              


      def inclusive_range(*args):
          numargs = len(args)
          start=0
          step=1

          if numargs < 1:
              raise TypeError('error: need atleast one argument, got {}'.format(numargs))

          elif numargs == 1:
              stop=args[0]

          elif numargs == 2:
              (start,stop) = args

          elif numargs == 3:
              (start,stop,step)=args

          else:
              raise TypeError('error: atmost three arguments, got {}'.format(numargs))


          # Generator
          x=start
          if x< stop:
              while x <= stop:
                  yield x #yield in generators give out a stream of values
                  x += step
          else:
              while x >= stop:
                  yield x 
                  x -= step



      if __name__ is "__main__" : main()
      
      
      
      
output:


      100 96 92 88 84 80 76 72 68 64 60
### Decorators

code:

      #decorator
      def f1(x):
          def f2():
              print("before")
              x()
              print("after")
          return f2
      @f1 # the function directly below the decorator becomes the argument of the function called in the decorators
      def f3():
          print("this is f3")

      f3()
      
output:

      before
      this is f3
      after



### Recursion

code 

      #recursion
      def loop(x):
          if x==0:
              raise TypeError('Cant loop Zero Times!')
          elif x==1:
              print('loop 1')
              print('loop complete')
          else:
              print(f'loop {x}')
              loop(x-1)

      loop(10)


output 


      loop 10
      loop 9
      loop 8
      loop 7
      loop 6
      loop 5
      loop 4
      loop 3
      loop 2
      loop 1
      loop complete

code 2

      #power
      def power(num ,pwr):
          if pwr==0:
              return 1
          else:
              return num * power(num, pwr-1)
    
      power(2,3)

output 2

      8     
      
code 3

#factorial
      def fac(num):
          if num ==0:
              return 1
          else:
              return num * fac(num-1)

      fac(8)
      
outout:

      40320
      

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

code #2

      class animals:
          def __init__(self, **kwargs):
              self._type= kwargs['Type']
              self._name= kwargs['name']
              self._sound=kwargs['sound']


          def type(self, t=None):
              if t:self._type =t
              return self._type

          def name(self, n=None):
              if n: self._name= n
              return self._name

          def sound(self, s=None):
              if s: self._sound= s
              return self._sound

          def __str__(self):
              return f'The {self.type()} that makes the sound {self.sound()} is named {self.name()}'


      def print_animal(o):
          if not isinstance(o, animals):
              raise TypeError("print_animal(): requires an animal")
          print('The {} that makes sound {} is named {}'.format(o.type(), o.sound(), o.name()))


      def main():
          object1= animals( Type = 'lion', sound = 'roar', name = 'Fluffy') 
          print_animal(animals( Type = 'dog', sound= 'bark', name= 'Scooby')) #using def print_animal()
          print(object1) #using just the class animals
      if __name__ is '__main__' :main()
      

output #2:
      
      
      The dog that makes sound bark is named Scooby
      The lion that makes the sound roar is named Fluffy


### Inheritance
code

      class animals:
          def __init__(self, **kwargs):
              if 'Type' in kwargs: self._type= kwargs['Type']
              if 'name' in kwargs: self._name= kwargs['name']
              if 'sound' in kwargs: self._sound=kwargs['sound']

          def type(self, t=None):
              if t:self._type =t
              try: return self._type
              except AttributeError: return None

          def name(self, n=None):
              if n: self._name= n
              try: return self._name
              except AttributeError: return None

          def sound(self, s=None):
              if s: self._sound= s
              try: return self._sound
              except AttributeError: return None
          def __str__(self):
              return f'The {self.type()} that makes the sound {self.sound()} is named {self.name()}'
      #Inheritance
      class lions(animals): #parent class animals
          def __init__(self, **kwargs):
              self._type='lion'
              if 'Type' in kwargs: del kwargs['Type']
              super().__init__(**kwargs) #super() funtion to inherit lions()
          def kill(self ,s):
              print( f'{self.name()} will now kill all {s}')
      def main():
          o1= lions(sound = 'roar', name = 'Fluffy') 
          o1.kill('humans')
      if __name__ is '__main__' :main()

output:

      Fluffy will now kill all humans

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
      
code #2

      from decimal import * #importing everything from decimal

      a =Decimal('.10')
      b=Decimal('.30')


      x=.10+.10+.10-.30
      y=a+a+a-b
      print(x, type(x))
      print(y, type(y))

output #2
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
      
      
    
## Databases

code

      import sqlite3

      def main():
          print('connect')
          db = sqlite3.connect('db-api.db')
          cur = db.cursor()
          print('create')
          cur.execute("DROP TABLE IF EXISTS test")
          cur.execute("""
              CREATE TABLE test (
                  id INTEGER PRIMARY KEY, string TEXT, number INTEGER
              )
              """)
          print('insert row')
          cur.execute("""
              INSERT INTO test (string, number) VALUES ('one', 1)
              """)
          print('insert row')
          cur.execute("""
              INSERT INTO test (string, number) VALUES ('two', 2)
              """)
          print('insert row')
          cur.execute("""
              INSERT INTO test (string, number) VALUES ('three', 3)
              """)
          print('commit')
          db.commit()
          print('count')
          cur.execute("SELECT COUNT(*) FROM test")
          count = cur.fetchone()[0]
          print(f'there are {count} rows in the table.')
          print('read')
          for row in cur.execute("SELECT * FROM test"):
              print(row)
          print('drop')
          cur.execute("DROP TABLE test")
          print('close')
          db.close()

      if __name__ == '__main__': main()

output

      connect
      create
      insert row
      insert row
      insert row
      commit
      count
      there are 3 rows in the table.
      read
      (1, 'one', 1)
      (2, 'two', 2)
      (3, 'three', 3)
      drop
      close

