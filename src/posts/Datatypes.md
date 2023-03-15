# Data Types in Rust
Data Types are an essential part of any programming language. When programming you may use many different data types without even knowing it! 

This article will cover the different data types specicially in rust, but the topics will aply to any programming language.

If you are a benginer programer or a person who has been programming for years this article will help you understand data types better.

## What are data types?
Data types are how the computer and programing language understands what you have typed. For example humans would say that 1 is a number, and "a" is a letter.

## Data Types:
Here is a list of the data types I will cover :
- [Integers](#integers)
- [Floats](#floats)
- [Booleans](#booleans)
- [chars](#chars)
- [Strings](#strings)
- [Tuples](#tuples)
- [Vectors/Arrays](#vectors)
- [Structs](#structs)
- [Enums](#enums)
- [Results](#results)
- [Optionals](#optionals)
- [Custom Data Types](#custom-data-types)

---

# Integers
Integers are any number positive or negative, that does not contain any decimals. 

### Examples:
Some examples of intergers would be 1, 2, -4, 5151515, etc. <br>
What integers are not are numbers with a decimal like 1.32, 1.0, -10.2, etc.

### In Depth Explanation:
Interges in rust can be repersented as bit values prfixed by an 'i' or 'u'. The bit value gives them an explicit size so they can only hold a certin range of numbers each. To see how the size is calculated based off the bit number see below. <br>
Valid bit values for signed or unsigned integers are:
- 8
- 16
- 32
- 64
- 128
- size: size will determine the bit size of your computer based on the archeture used. ex: isize will be the same as `i32` for a 32 bit computer, and usize will be the same as `u64` for a 64 bit computer.
  
Depending on wich prefix you use you will be able to store differnet numbers, with i being signed meinging it can hold numbers including the sign positive or negative, but u means unsigned meaning it can hold only numbers without a sign (postive numbers). If you use 'i' the size will be \\( \-2^{n-1} \\) to \\( 2^{n-1}-1 \\) where n repersents the number of bits specified. For example an `i8` holds numbers between \\( \-2^7 \\) and \\( 2^7-1 \\) or -128 to 127. On the other hand if you choose 'u' the size will be 0 to \\( 2^n-1 \\) where n again repersents the number of bits. For example a `u8` holds between 0 and \\(\ 2^8-1 \\) wich is 0 to 255. <br>
All integers are able to be added, subtracted, multiplied, and divided, as well as the remainder of division. <br>

### Interger Literals:
Integer literals are other ways to repersent integers. For example if you want to be able to read a large number such as 120764164 easier you can add underscores to the number like 120_764_164, since adding commas would produce an error. <br>
Another way you can use integer literals is to use intergers to repersent differnt things such as the following:
- Hex (Repersented by the term '0x' then the hex code)
- Octal(Repersented by the term '0o' then the octal code)
- Binary(Repersented by the term '0b' then the binary code)
- bytes (`u8s` only)(Repersented by b'byte')

### In-Code Examples:
Here are some examples of how you would perform integer opeartions in rust.
```rust
# fn main() {
  let five: i32 = 5; //Defines a variable of type i32 with a value of 5
  let large_num: i32 = -12_345_678; //Defines a variable of type i32
  
  println!("{}", five+large_num); //Adds two numbers together and prints the sum

  let a: u8 = 255; //Defines a variable of type u8
  // let b: u8 = -256;
  // ^ Error : `-256` is outside the range of a u8 (i.e. `0..=255`)
  let c: u32 = 1_131; //Defines a variable of type u32

  //println!("{}", a+c);
  // ^ Error: You can't add intereges of different sizes

  let bin: i32 = 0b1010; //Defines a binary value
  let hex: i32 = 0xFF; //Defines a hex value

  println!("{}, {}", bin, hex); //Prints the binary and hex values
# }
```

---

# Floats
Floats are positive or negative numbers that contain decimals. Floats are very similar to ints in the way they behave but have a few key differences.

## Examples:
Numbers that are floats would be 1.32, 1.0, -213.2, etc.
Numbers that arnt floats would be 1, 213, 23, 4, etc.

## In Depth Explanation:
Floats in rust can be repersented as a bit value prefixed by an 'f'. The bit value gives them their size just like integers. Unlike integers floats are all signed and dont have an unsigned version.
Valid bit values for floats are:
- 32
- 64

Floats with a size of 32 will have less percision then floats with a size of 64. `f64`'s  have about double the percision of `f32`'s with very little performance loss. <br>
Just like integers floats can have the same operations performed on them.

## In-Code Examples:
Here are some examples of float operations in rust.
```rust
# fn main(){
    let five: f32 = 5.2; //Defines a variable of type f32 with a value of 5.0
    let six = 6.0; // When defineing a float the value will defult to f32
    let seven: f64 = 7.2313; // Defines a variable of type f64 with a value of 7.0

    println!("{}", five+six); //Adds two numbers together and prints the sum
    //println!("{}", five+seven);
    // ^ Error: Cannot add floats of different sizes
# }
```

---

# Boolens
Booleans are values that are either true or false.