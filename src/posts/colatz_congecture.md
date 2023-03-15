# Collatz Conjecture
A small project I have done in rust is to make a caluclator that can calucalate the digits produces by performing the collatz conjecture on a number.

#### What is the collatz conjecture:
The collatz conjecture is a unsolved problem in math that states that for any positve integer, you can use two steps repeatedly to get it down to one.
The rules for the conjecture are:
- If the number is even, divide it by 2.
- If the number is odd, multiply it by 3 and add 1.

Now that you know what the collatz conjecture is, it is time to start desing, and coding.

## Creating the program!
To start lets make a quick main function to call anothor function to perform the collatz conjecture.
```rust
fn main(){
    let num: i32 = 12;
    conjecture(num);
}
```
This function will call the function to accutualy do the reduction. This functiona also sets the number that we want to do the reduction on. <br>
Next lets start work on a function to do the reduction!
```rust,editable
fn main(){
    let mut num: i32 = 12;
    conjecture(num)
}

fn conjecture(mut num: i32){
    println!("Number to perform the opperation on: {num}"); // Print out the starting 
    //number
    if num < 1{ // Check that the number isnt negative or zero
        println!("{num} is not a valid number");
    }

    let mut nums_list: Vec<i32> = Vec::new(); // Create a new vec 
    //to eventully hold all of the numbers that we got in the proccess
    
    while num > 1 { // check to make sure the num is greater than one
        if num % 2 == 0 { // if the number is even
            num = num / 2; // divide the number by 2
        } else { // if the number is odd
            num = 3 * num + 1; // multiply the number by 3 and add 1
        }
        nums_list.push(num); // push the number into the list  
    }
    println!("The collatz conjecture is: {:?}", nums_list); // Print out 
    //the list of numbers
}
```
Now that we have the code to do the logic and get the number down, try changing the num value and see what happens! <br>
Some questions to consider while changing the code:
- What would happen if the number was odd?
- Is there a limit on the size of the numbers?
- Is there more of a pattern in the numbers that get used? <br>
  
Now that we have a very basic implimentation of the collatz conjecture lets try to add more!
```rust 
fn main(){
    use std::time::Instant;
    let now = Instant::now();

    let mut num: i32 = 12;
    conjecture(num);

    let elapsed = now.elapsed();
    println!("Time elapsed: {:.2?}", elapsed); //print the time, 
    //and round it to the nearest thousandth
}
```
Now we have changed our main function to time the program. <br>
Now that we have a implimentation of the collatz conjecture and a basic understanding of how it works, I challange you to try some of these basic challanges:
- Recursivly call the main function with different numbers
- Visulize the numbers and the numbers in the reduction
- Count the total number of numbers in the reduction
  
On that note, thanks for reading! I hope you enjoyed this small post!