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
- We can create arrays using literals. As everything is an object, this implies that an array can hold **objects of different types**:
```
a = ["number", 1, 2, 3.14]  # Array with 4 elements
puts a[0]                   #=> number
a[3] = nil                  # Set the last element to nil
puts a                      # Access and display entire array.
                            #=> number 1 2 nil
```

- We can also create an array by explicitly creating an Array object. Ruby allows us to specify array ranges, as in the example below:
```
myarray = [ 0, 1, 2, 3, 4, 5 ]
puts myarray[0]       #=> 0

                      # [i...j] from index i to j excluding j
puts myarray[1...3]   # Exclusive range => 1 2.

                      # [i..j] from index i to j including j
puts myarray[1..3]    # Inclusive range. => 1 2 3.
puts myarray[1,3]     # Range between 1st up to 3rd consecutive, inclusive.
                      #=> 2 3 4.
```
- Ruby allows a negative index, forcing the array to count from the end.
```
a = [ "pi", 3.14, "prime", 17 ]
puts a[-1]      #=> 17
```

### Associative arrays
- An **associative array** or **hash** is an **unordered collection of elements**.
- An element is a pair of 2 objects: a **value** and a **key** through which the value can be retrieved. The value can be an object of any type.
- To store an element in an associative array, we must supply both objects:
```
hashName = {"key" => "value",
             ...
           }
```
- We can subsequently retrieve the value by supplying the appropriate key:

`hashName["key"] => value`





