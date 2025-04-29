## Screen Printing

```rust
//this is the main function. Every Rust program starts here.
fn main() {
    // this line prints the text "Hello, world!" to the screen.
    print!("Hello, world!");

    println!("Hello, world!"); //new line
}
```

---

## Variables
variables are immutables by default unless you specify the "mut" keyword.

```rust
fn main() {
    //let for declare a variable
    let x = 5;
    x = 6; // error, the variable is immutable

    let mut y = 5;
    y = 6; // value changed correctly

    //costant
    const PI: u32 = 3.14;
}
```

**Primitive types**
```rust
fn main() {
    let int_val: i32 = 42; // signed 32-bit integer
    let float_val: f64 = 3.14; //64-bit floating point
    let is_active: bool = true; //Boolean
    let char_val: char = "A"; //character
}
```

**Concatenation**
```rust
fn main() {
    let name = "RykerWilder";
    let age = 1024;

    // concatenation using {} to format string
    print!("My name is {name} and i am {age} years old.");
}
```

## Mathematical Operators

```rust
fn main() {
    let a = 5;
    let b = 10;

    //arithmetic operators
    let sum = a + b;
    let difference = b - a;
    let product = a * b;
    let quotient = b / a;
    let remainder = b % a;

    //logical operators
    let is_equal = a == b;
    let is_greater = a > b;
    let is_less = a < b;
}
```

## Conditions

**if-else**
```rust

fn main() {
    let number = 7;

    if number < 5 {
        print!("condition is true");
    } else if number == 5{
        println!("number is exactly 5!");
    } else {
        println!("condition is false");
    }
}
```

**match**
```rust
fn main() {
    let number = 3;

    match number {
        1 => println!("One"),
        2 => println!("Two"),
        3 => println!("Three"),
        _ => println!("other number") // default case
    }
}
```