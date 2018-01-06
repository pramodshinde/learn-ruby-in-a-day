# Inheritance and Access Specifiers in Ruby
- Ruby allow only single class inheritance 
- Class is inherited using `<`
## Base class  
```ruby
class Vehicle

  def initialize(model)
    @model = model
  end

  def drive
    "I'm driving #{self.class}: #{@model}"
  end

  protected

  def calculate_price
    "In calculate_price #{self.class}: #{@model}"
  end
end
```
### Example
- `Car` class inheriting from `Vehicle`
```ruby
class Car < Vehicle
  def current_price
    calculate_price
  end
end

car = Car.new('X11')
p car.drive
p car.current_price
#=> "I'm driving Car: X11"
#=> "In calculate_price Car: X11"
```
## Overriding Methods 
### Example
- `Bike` in inheriting from `Vehicle` and overriding `drive` method
```ruby
class Bike < Vehicle
  def drive
    "I'm riding #{self.class}: #{@model}"
  end

  def current_price
    calculate_price
  end
end

bike = Bike.new('B11')
p bike.drive
p bike.current_price
#=> "I'm riding Bike: B11"
#=> "In calculate_price Bike: B11"
```

## Calling protected and private in child class 

```ruby
class Truck < Vehicle
  def current_price
    p calculate_price
    p sold_out?
    Bike.new('B11').calculate_price # calling protected method
    Bike.new('B11').sold_out? # calling private method raises error
  end
end

truck = Truck.new('T11')
p truck.drive
p truck.current_price
#=> "In calculate_price Truck: T11"
#=> "All trucks sold out!"
#=> private method `sold_out?' called for #<Bike:0x007fc3e596a798 @model="B11"> (NoMethodError)
```

