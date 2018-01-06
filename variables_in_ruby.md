# Variables in Ruby
## Local Variables
+ `var` a local variable.
+ begin with a lowercase letter or _.
+ local scope class, module, method,  
+ When an uninitialized local variable is referenced, it is interpreted as a call to a method that has no arguments.
```ruby
x=5
```
## Instance variables
+ `@var` is an instance variable.
+ Instance variables begin with @. 
+ Uninitialized instance variables have the value nil.
+ scope inside the class

```ruby
class Car
  def initialize(model)
    @model = model
  end
end
```

## Class Variables
+ `@@var` is class variables
+ Begin with @@
+ Must be initialized before they can be used in method definitions
+ Referencing an uninitialized class variable produces an error.
+ Class variables are shared among descendants of the class or module in which the class variables are defined.

```ruby
class Car
  @@no_of_cars = 0
  def initialize(model)
    @model = model
  end

  def total_number_of_cars
    @@no_of_cars += 1
     puts "Total number of cars: #@@no_of_cars"
  end
end
car1 = Car.new('X1')
car2 = Car.new('X2')
car1.total_number_of_cars
=> Total number of cars: 1
car2.total_number_of_cars
=> Total number of cars: 2
```
## Global variables
+ `$var` is a global variable.
+ begin with $
+ Uninitialized global variables have the value `nil`

```ruby
$global_variable = 10
class Car1
   def print_global
      puts "Global variable in Car1 is #{$global_variable}"
   end
end
class Car2
   def print_global
      puts "Global variable in Car2 is #{$global_variable}"
   end
end

c1 = Car1.new
c1.print_global
=> Global variable in Car1 is 10
c2 = Car2.new
c2.print_global
=> Global variable in Car2 is 10
```
