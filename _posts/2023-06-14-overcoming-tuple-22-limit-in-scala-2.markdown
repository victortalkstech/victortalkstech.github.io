---
layout: post
title:  "Overcoming Tuple 22 Limit in Scala 2"
date:   2023-06-14 22:39:29 +0100
categories: scala
---

## Introduction

Scala's language design has many interesting aspects that are unique or not common in other languages. One of these is the tuple, a data structure that can contain different types of data, similar to a list or an array. However, there's a limitation: Scala only supports tuples up to 22 elements.

This restriction is due to the way the tuple classes are defined in the Scala library. Each tuple class from Tuple1 to Tuple22 is defined separately, meaning there is no generic Tuple class that can take an arbitrary number of elements. For most practical purposes, tuples of size 22 are usually sufficient. However, when you hit that limit, it can be frustrating.

In this article, we will explore a few ways of overcoming this limitation, with specific code examples.

## Using Case Classes

One way to handle the limit is by using case classes, which can contain more than 22 elements. Case classes provide a way to define multiple fields in one class, and they come with several useful features automatically, such as equals and hashCode methods.

```scala
case class BigTuple(
  _1: Int, _2: Int, _3: Int, _4: Int, _5: Int, _6: Int, _7: Int, _8: Int, _9: Int, _10: Int,
  _11: Int, _12: Int, _13: Int, _14: Int, _15: Int, _16: Int, _17: Int, _18: Int, _19: Int, _20: Int,
  _21: Int, _22: Int, _23: Int, _24: Int, _25: Int, _26: Int, _27: Int, _28: Int, _29: Int, _30: Int
)
```

## Using Heterogeneous Lists (HLists)

Another solution is to use a Heterogeneous List, or HList, a data structure that can hold arbitrary types and arbitrary number of elements. The Shapeless library provides a powerful implementation of HLists in Scala.

Here's an example of how you can use HLists:

```scala
import shapeless._

val hlist = 1 :: "Hello" :: true :: HNil
```

To overcome the tuple limit, you can just keep adding elements to your HList:

```scala
val bigHList = 1 :: "Hello" :: true :: 2.0 :: 'c' :: HNil // and so on...
```

HLists can also be converted back to case classes:

```scala
case class Person(name: String, age: Int)

val personHList = "John" :: 30 :: HNil

val person = Generic[Person].from(personHList)  // Person("John", 30)
```

## Using Shapeless' Sized

Shapeless also offers a Sized data structure which represents collections with a statically known size. This can be an alternative if you need more than 22 elements and all of them are of the same type:

```scala
import shapeless._
import nat._
import Sized._

val sized = Sized[Vector](1, 2, 3) // Sized[Vector[_3], Int] with elements 1, 2, 3

val bigSized = sized :+ 4 :+ 5 // You can append elements and Scala will track the size at compile time
```

## Conclusion

In conclusion, while Scala's native tuples have a limitation of 22 elements, there are several other options available for working with larger data structures. Using these alternatives will also help make your code more readable and maintainable.
