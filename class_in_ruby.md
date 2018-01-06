# Class in Ruby
## Simple class 
- `initialize` is constructor 
- `@model` is instance variable 

```ruby
class Car
  def initialize(model)
    @model = model
  end
end

p car = Car.new('X11')
#=> #<Car:0x007fb4ee82abb8 @model="X11">
```
## Class with getter and setter 
- `get_model` is getter 
- `set_model=(...)` is setter
```ruby
class Car
  def initialize(model)
    @model = model
  end

  def get_model
    @model
  end

  def set_model=(model)
    @model = model
  end
end

p car = Car.new('X11')
p car.set_model = 'X22'
p car.get_model
#=> #<Car:0x007fb4ee829e20 @model="X11">
#=> "X22"
#=> "X22"
```
## class with `attr_accessor`
- Removing get_model and set_model by adding attr_accessor.
- Ruby gives getters and setters with same name as instance variable.
```ruby
class Car
  #Removing get_model and set_model by adding attr_accessor
  attr_accessor :model

  def initialize(model)
    @model = model
  end
end

p car = Car.new('X11')
p car.model = 'X22'
p car.model
#=> #<Car:0x007fb4ee829e20 @model="X11">
#=> "X22"
#=> "X22"
```

## Class method and Instance method

### Class method 
- Called using class itself.
- Defined using `self` keyword or `class << self...end`

###  Example
```ruby
class Car
   @@total = 0
   def initialize(model)
    @model = model
    @@total += 1
  end

  def self.total_cars_1
    @@total
  end

  class << self
    def total_cars_2
      @@total
    end
  end
end

Car.new('X11')
Car.new('X22')
p Car.total_cars_1
p Car.total_cars_2
#=> 2
#=> 2
```

Assignment: 
1. What is `new`, from where it comes, What is relation between `new` and `initialize`?
2. How can we add only getters/setters for instance variables in Ruby?
