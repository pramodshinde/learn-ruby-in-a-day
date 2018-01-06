# Access Specifiers in Ruby
- Ruby has `public`, `private` and `protected` access specifiers 
## Public Methods 
- By default all methods in class are public 
- Can be called from outside of the class 
- Gets inherited in child class
### Example
```ruby
class Car
  def initialize(model)
    @model = model
    @price = nil
  end

  def current_price
    "Current price of #{@model} is #{rand(2000) * 2}"
  end
end

p car = Car.new('X11')
p car.current_price #calling public method 
#=> #<Car:0x007fbb7585b8c0 @model="X11", @price=nil>
#=> "Currert price of X11 is 1804"
```
## Private Methods 
- By default `initialize` and all instance(`@...`) variables are private in class. 
- Written using `private` keyword
- Cannot be called from outside of the class. 
- Gets inherited in child classes but can be called implicitly only (current objects context only).
- Cannot be called with explicit receiver.
### Example
```ruby
class Car
  def initialize(model)
    @model = model
    @price = nil
  end

  def current_price
    "Current price of #{@model} is #{calculate_current_price}"
  end

  private
  def calculate_current_price
    @price = rand(2000) * 2
  end
end

p car = Car.new('X11')
p car.current_price # calling public method
p car.calculate_current_price # calling private method
#=> #<Car:0x007fbb7585afd8 @model="X11", @price=nil>
#=> "Currert price of X11 is 2546"
#=> private method `calculate_current_price' called for #<Car:0x007fbb7585afd8 @model="X11", @price=2546> (NoMethodError)
```

## Protected Methods 
- Written using `protected` keyword
- Cannot be called from outside of the class. 
- Gets inherited in child classes, can be called implicitly and explicitly (current objects context only).
- Can call a protected method with an explicit receiver as long as this receiver is `self` or an object of the same class as self

### Example
```ruby
class Car
  def initialize(model)
    @model = model
    @price = nil
  end

  def current_price
    "Current price of #{@model} is #{self.calculate_current_price}"
  end

  protected
  
  def calculate_current_price
    @price = rand(2000) * 2
  end
end

p car = Car.new('X11')
p car.current_price # calling public method
p car.calculate_current_price # calling private method
#=> #<Car:0x007fbb7585afd8 @model="X11", @price=nil>
#=> "Currert price of X11 is 2546"
#=> protected method `calculate_current_price' called for #<Car:0x007fbb7585afd8 @model="X11", @price=2546> (NoMethodError)
```
## Assignment 
1. How to call private methods from outside the class in Ruby?
