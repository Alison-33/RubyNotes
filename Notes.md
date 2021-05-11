# Ruby notes

### Message passing
```
puts "The Ruby language".length #=> 17
puts "Ruby".index("y")          #=> 3
puts -7.abs                     #=> 7
puts 10.49.round                #=> 10
puts 2.next                     #=> 3
puts 97.chr                     #=> "a"
```

### Variables and aliasing
- Multiple variables referencing the same object is called aliasing.
```
person1 = "Tony"
person2 = person1
```
- The assignment of person1 to person2 does not create an object.
- It assigns the object reference of person1 to person2, so that both variables now would refer to the same object.
- We can avoid aliasing with **dup**, which creates a new object with identical contents.
```
person3 = person1.dup
person1[0] = "R"
puts person1 #=> "Rony"
puts person2 #=> "Rony"
puts person3 #=> "Tony"
```

### Chaining assignment statements
- An assignment statement sets the value of a variable on its left hand side to the **value of the expression** on its right hand side.
- Ruby supports chaining of assignments. It also allows one to perform assignments in some unexpected places.
```
a = b = 1 + 2 + 3
puts a #=> 6
puts b #=> 6
a = (b = 1 + 2) + 3
puts a #=> 6
puts b #=> 3
```


### Parallel assignment statements
```
a = 1
b = 2
a, b = b, a
puts a #=> 2
puts b #=> 1
x = 0
a, b, c = x, (x += 1), (x += 1)
puts a #=> 0
puts b #=> 1
puts c #=> 2
puts x #=> 2
```


### Arrays
- An array is an ordered collection of elements, where each element is identified by an **integer index**.





