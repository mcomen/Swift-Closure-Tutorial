# Swift-Closure-Tutorial

A short introduction to closures in practical usage.

# Objectives

Understand what a closure is
Identify closures used commonly in UIKit
Write closures yourself
Create system that makes paractical use of a closure

# Lesson

## Outline 

---
mins    activity    description
5       Intro       What is a closure?
5       Discussion  Spot closures in example
10      Practice    Write some closures 
??
??      Discussion  Closing discussion questions
---

## Intro

Closures are self-contained blocks of functionality. Sometimes closures are called "blocks".
If you are familiar with functions than you should understand closures with little effort.
In Swift functions are a special case of closure. 

In a nustshell closures are functions with the added bonus that they can be treated as a value type.
Closures can be:

- Passed as values
- Assigned to variables
- Closures can capture (or __enclose__) variables from the surrounding context (more on this later)

**Question:**

- Thoughts on closures? 
- Give me some use cases?

## What do Closures look like in Swift?

Closures Example: 

Playground: [Closures1.playground](Closures1.playground.zip)

Activity: Closures in the Wild. Download and open the project below. Find the closures in the sample project. 
How many did you find?

Project: [ClosuresExample1](https://github.com/soggybag/ClosuresExample1)

The closures used in this project might be referred to as "callbacks". A callback is a block of code passed to another 
part of your program to execute at a more convenient time. 

Closures are values. Take a look at the callback in presentViewController(). 
A quick look at the signature of a function. 

## Exercise 

Add a new UIAlertAction. The handler parameter is a closure! Write the code block to set the background color to 
red when this button is tapped. (Don't forget to add your alert action to the alert!)

Further challenges: 

- When closing the alert show the user name in the label
- Make the new action show a view or label that slides up from the bottom of the screen. 
- Make the new action display second alert dialog with three text fields. 

## Discussion Questions 

- What do the closures do here? 
- Does `presentViewController()` use a closure? 
- Can you compare closures to the delegate pattern? 
 
### Closure Features

- Closures can be assigned to variables 
- Closures can be passed as parameters to methods 
- Closures can be returned from a method 

### Closure Types

Closures are **values** and as such they have a type. The Type of a closures is it's signature. The signature is 
the parameters it accepts, and the value it returns.

var a = {(Int) -> Int in /* do stuff */} // This clsoure is type: (Int) -> (Int)

You could declare a var of this type: 

var f = (Int) -> (Int) 

**Exercise:** 

Write the function types for the closures in the example, do this with a partner. Write the types for: 

- UIAlertAction( ... handler:) (the handler param)
- presentViewController(... completion:) (The completion param)

## Use cases closures

Closures are useful when you want to add functionality to something, or need the flexibility to decide functionality
as convenient. 

In the case of presentViewController "completion" might be referred to as a "callback" since it's execution is
asynchronous. The animation must complete before the aniamtion is finished.

- Why does UIKit use closures for UIAlertAction and presentViewController()?
- Why do you have to use self in closures?

## MSButtonNode

The MSButtonNode class is another use case for closures. The selectedHandler is a class property the 
value of which is a funtion that takes no parameters and returns nothing. 

Project file: [Closure example 2](https://github.com/soggybag/ClosuresExample2)

Exercise: Write a closure to make the button do something. 

Challenge: Make an alternative to the ButtonNode class call it: ToggleButtonNode. Toggle button will display two states 
like a switch or a check box. It will change states with each tap and execute one of two closures alternating. 

## Passing Values to a Closure

In the previous example you made use of UIKit objects and methods that make use of closures. 
In this example you will add a closure to an existing class. 

The Joystick class is used with SpriteKit. It creates a virtual joystick that appears on the screen. 
Your goal is to add a new property to this class that will take two parameters: x and y. 
Joystick should invoke this closure passing it's xValue, and yValue. Use the closure to move the box. 

Project files: [Closure Example 3](https://github.com/soggybag/ClosuresExample3)

## Capturing Values

Closures can capture variables that exist outside their local scope. 
You could say a closure __encloses__ these values. Which might explain the name?. 

Example Files: [Closures2.playground](https://github.com/soggybag/ClosuresExample2)

Quick discussion: 

- Where does that value of count come from? 
- What are the implications? 

Exercise: Iterator! Make an iterator. This will be a function that takes an array as a parameter, and 
returns a closure that will iterate the contents of the array. See the notes in the playground for 
details. 

## Conclusion

- Name some differences between traditional functions and closures?
- Closures in the examples were used to handle 


# Vocabulary

Here are some terms used when talking about closures

## Function literal 

A function/closure assigned to variable. This is sometimes called a "function literal"

var a = {(Int) -> Int in /* do stuff */}

## Higher order Functions 

A higher order function is a function that takes another function as a parameter. 

## Callback

A closure passed to an object. Usually executed Asynchronously.

## Handler 

A closure executed by another object, usually in response to an action, like a tap or swipe. 

## Function 

Another name for a Closure ([In swift Functions are a special case of closure](https://developer.apple.com/library/mac/documentation/Swift/Conceptual/Swift_Programming_Language/Closures.html))

## Block 

Another name for closure. 



