---
layout: post
title:  "Functional Programming in Scala vs Rust"
date:   2023-06-29 16:00:00 +0100
categories: scala
---

## Introduction

Functional programming is a paradigm that treats computation as the evaluation of mathematical functions and avoids changing state and mutable data. In the context of software development, functional programming is essential for developing programs that are safe, modular, and maintainable. This article compares the functional programming capabilities of two popular programming languages: Scala and Rust. Both these languages have rich functional programming features, but they employ different approaches due to their differing goals and foundational principles.

## Overview of Scala and Rust

Scala is a statically-typed language designed to express common programming patterns in a concise, elegant, and type-safe way. It smoothly integrates features of object-oriented and functional languages, making it a scalable language in both small scripts and large systems.

Rust, on the other hand, is a systems programming language that aims to provide memory safety, concurrency, and performance with a focus on zero-cost abstractions, minimal runtime, and improved productivity. It offers many features from the functional programming paradigm, but its primary selling point is its ability to provide high performance and memory safety guarantees.

## Functional Programming in Scala

Scala has extensive support for functional programming. It allows functions to be first-class citizens, supports higher-order functions, and provides a rich library for working with immutable data structures.

### Code Example: Higher-Order Functions in Scala

```scala
def applyFuncTwice(f: Int => Int, x: Int): Int = f(f(x))

val addTwo = (x: Int) => x + 2
println(applyFuncTwice(addTwo, 10)) // prints 14
```

In the above example, `applyFuncTwice` is a higher-order function that takes a function `f` and an integer `x` as arguments. It applies `f` twice to `x` and returns the result.

### Pattern Matching and Case Classes

Scala offers powerful pattern matching capabilities. Pattern matching in Scala works like switch statements in other languages, but it's much more powerful due to its ability to work with case classes.

```scala
abstract class Animal
case class Dog(name: String) extends Animal
case class Cat(name: String) extends Animal

def printAnimal(a: Animal): Unit = a match {
  case Dog(name) => println(s"This is a dog named $name.")
  case Cat(name) => println(s"This is a cat named $name.")
}

printAnimal(Dog("Rex")) // prints "This is a dog named Rex."
```

## Functional Programming in Rust

Rust also has first-class functions, higher-order functions, and other functional features, but it's not a functional language in the same sense as Scala. Rust focuses more on the ownership, borrowing, and lifetime concepts, which are crucial for systems programming.

### Code Example: Higher-Order Functions in Rust

```rust
fn apply_func_twice(f: &dyn Fn(i32) -> i32, x: i32) -> i32 {
    f(f(x))
}

let add_two = |x: i32| x + 2;
println!("{}", apply_func_twice(&add_two, 10)); // prints 14
```

The above example demonstrates the use of a higher-order function in Rust. The function apply_func_twice takes a function f and an integer x as arguments, applies f twice to x, and returns the result.

### Pattern Matching in Rust

Rust also supports pattern matching, which can be used with its Enum types for elegant and safe code.

```rust
enum Animal {
    Dog(String),
    Cat(String),
}

fn print_animal(a: Animal) {
    match a {
        Animal::Dog(name) => println!("This is a dog named {}.", name),
        Animal::Dog(name) => println!("This is a dog named {}.", name),
        Animal::Cat(name) => println!("This is a cat named {}.", name)
    }
}

print_animal(Animal::Dog(String::from("Rex"))); // prints "This is a dog named Rex."
```

The above example demonstrates the use of pattern matching in Rust. The `print_animal` function takes an `Animal` enum as an argument and uses a match statement to determine what to print.

## Conclusion

Scala and Rust both offer significant support for functional programming, but their different focus areas lead to different approaches. Scala, with its blend of object-oriented and functional programming, provides more comprehensive support for functional programming patterns. It has a rich set of library functions that makes functional programming more straightforward and expressive. Rust, while supporting many functional programming concepts, primarily emphasizes safety and performance. Its functional features are somewhat more limited, but they are well-integrated into its unique systems programming model, which focuses on ownership and borrowing.

When it comes to choosing between Scala and Rust for functional programming, the decision should be based on the specific requirements of your project. If you are building a large, complex system where you need to balance object-oriented and functional programming, Scala may be a better choice. On the other hand, if you are developing a system where performance and memory safety are critical, Rust would be more suitable, even if it means working with a more limited set of functional programming features.
