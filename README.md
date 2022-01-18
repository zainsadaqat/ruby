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

## First way to use Blocks

```
students = ["zain", "moaz", "leo", "ali"];

# One way to implement blocks
def each(array, &block) 
  i = 0;
  while i < array.length
    element = array[i]
    block.call(element) # one way
    i += 1
  end
end

each(students) do |student|
  puts "element == #{student}"
end
```

## Second way to use Blocks

```
students = ["zain", "moaz", "leo", "ali"];

# Second way to implement block is using yield
def each(array)
  i = 0
  while i < array.length
    element = array[i]
    yield element # second way
    i += 1
  end
end

each(students) do |student|
  puts "element == #{student}"
end
```




