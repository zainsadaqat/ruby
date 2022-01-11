# Self in Ruby

> Everything is an object in ruby

`puts self`
=> main

`puts self.class`
=> Object

What behind the scene happening is: 
`main = Object.new`

## Self inside an instance method

```
class Dog
  def bark
    self
  end
end

d = Dog.new
puts d == d.bark //true
```

## Self inside of a class method

```
class Dog
  def self.bark
    self
  end
end

d = Dog.new
puts d == d.bark //true
```

## Create multiple class level methods

```
class Dog
  def << self
    def bark
    end
    def chew
    end
    def fetch
    end
  end
end
```
all methods inside of def << self are class-level methods




