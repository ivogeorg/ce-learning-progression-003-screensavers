# CPE 1040 - Fall 2020

This is learning progression 003 for the Fall 2020 installment of the course CPE 1040: Introduction to Computer Engineering at MSU Denver.

Table of Contents
=================

* [CPE 1040 \- Fall 2020](#cpe-1040---fall-2020)
  * [Learning Progression 003: Screensavers](#learning-progression-003-screensavers)
    * [1\. Arrays revisited](#1-arrays-revisited)
      * [1\. Study](#1-study)
        * [Arrays](#arrays)
        * [Array methods](#array-methods)
        * [Multi\-dimensional arrays](#multi-dimensional-arrays)
      * [2\. Apply](#2-apply)
      * [3\. Present](#3-present)
    * [2\. Screensavers](#2-screensavers)
      * [1\. Study](#1-study-1)
      * [2\. Apply](#2-apply-1)
      * [3\. Present](#3-present-1)
    * [3\. Program structure](#3-program-structure)
      * [1\. Study](#1-study-2)
      * [2\. Apply](#2-apply-2)
      * [3\. Present](#3-present-2)
    * [4\. Divide &amp; conquer: program decomposition](#4-divide--conquer-program-decomposition)
      * [1\. Study](#1-study-3)
      * [2\. Apply](#2-apply-3)
      * [3\. Present](#3-present-3)
    * [5\. Randomized behavior](#5-randomized-behavior)
      * [1\. Study](#1-study-4)
      * [2\. Apply](#2-apply-4)
      * [3\. Present](#3-present-4)
    * [6\. Encapsulation](#6-encapsulation)
      * [1\. Study](#1-study-5)
      * [2\. Apply](#2-apply-5)
      * [3\. Present](#3-present-5)
    * [7\. Functions revisited](#7-functions-revisited)
      * [1\. Study](#1-study-6)
      * [2\. Apply](#2-apply-6)
      * [3\. Present](#3-present-6)
    * [8\. Classes revisited](#8-classes-revisited)
      * [1\. Study](#1-study-7)
      * [2\. Apply](#2-apply-7)
      * [3\. Present](#3-present-7)
    * [9\. Code reading](#9-code-reading)
      * [1\. Study](#1-study-8)
      * [2\. Apply](#2-apply-8)
      * [3\. Present](#3-present-8)
    * [10\. Iterative development with Github](#10-iterative-development-with-github)
      * [1\. Study](#1-study-9)
      * [2\. Apply](#2-apply-9)
      * [3\. Present](#3-present-9)
    * [11\. Reactive system](#11-reactive-system)
      * [1\. Study](#1-study-10)
      * [2\. Apply](#2-apply-10)
      * [3\. Present](#3-present-10)
    * [12\. Matrix dynamics](#12-matrix-dynamics)
      * [1\. Study](#1-study-11)
      * [2\. Apply](#2-apply-11)
      * [3\. Present](#3-present-11)

## Learning Progression 003: Screensavers
[[toc](#table-of-contents)]

This progression is the culmination of the first part of the course, in which we program the bear-bones micro:bit without any extenral circuitry attached and without communication features. We pull together all the programming language features and best practices that we introduced in the previous two learning progressions, to write a significantly larger target program over 12 steps. This will present the opportunity to learn about some of the design considerations a programmer makes when approaching a larger project. The progression is also going to dig a bit deeper into the _softare stack_ of the micro:bit, and uncover the ways it affects these considerations.

### 1. Arrays revisited  
[[toc](#table-of-contents)]

#### 1. Study  
[[toc](#table-of-contents)]

##### Arrays
[[toc](#table-of-contents)]

`[<lernact-rd>]`We have already seen how versatile and powerful arrays can be in a program, allowing us to achieve complex program behavior far more easily than if arrays weren't available to the programming language. Let's quickly review what arrays are. An `[<cept>]`_array_ is an _ordered sequence_ of elements _of the same type_. Because it holds more than one piece of data, it is also called a `[<cept>]`[_data structure_](https://en.wikipedia.org/wiki/Data_structure). Like any other variable and function, an array has a _name_. This name can be used to refer not only to the whole array, but to individual elements of the array. Because they are ordered, they can be referenced by `[<cept>]`_index_, that is, by their place in the order, using the `[<cept>]`_selection operator_ `[]` (opening and closing square bracket). Let's take a look:
```javascript
// Example 1.1.1

let firstPrimes : number[] = [1, 3, 5, 7, 11, 13, 17, 19, 23, 31]

let favoritePrime : number = firstPrimes[3]  // selects 7

for (let i = 0; i < firstPrimes.length; i ++) {
    if (firstPrimes[i] != favoritePrime) {
        basic.showNumber(firstPrimes[i])
    } else {
        basic.showString("My favorite prime is " + favoritePrime.toString() + "!")
    }
}
```
As we can see, the `[]` operator is used heavily with arrays. In fact, that's how you can spot array variables in a program even if you are not looking at the array declaration. Let's enumerate its uses:
1. In `let firstPrimes...`, it indicates an array data type by attaching to the right of the `[<cept>]`_base type_. We are declaring an array of numbers, so the base time is `number`, and the type of the array variable `firstPrimes` is `number[]`. The single pair of brackets `[]` also indicates that this is `[<cept>]`_unidimensional_ array.  
2. In `let favoritePrime...`, it selects a particular element of the array, in this case the one with index 3, making it the forth element. Note that the array index always starts at 0.  
3. In `firstPrimes[i]`, it picks out the element, the index of which is equal to the current value of the loop variable `i`. So, the `[]` operator admits `[<cept>]`_expressions_ between the brackets, as long as they evaluate to an `[<cept>]`_integer_ value. That is, the result of evaluating the expression has to be a whole number. In addition, the integer has to be in the index `[<cept>]`_range_ of the array. That is, the number between the brackets has to be among the valid indices of the array. In our case, the range is [0, 9].  

##### Array methods
[[toc](#table-of-contents)]

`[<lernact-rd>]`The usefulness of the arrays doesn't stop with the ability to keep a collection of data together. Arrays come with many useful `[<cept>]`_methods_ and `[<cept>]`_properties_ for manipulating the elements of the collection or the whole collection itself. In Example 1.1.1, we already encountered the `length` property. The best way to explore methods in MakeCode is to declare an array variable, invoke the dropdown by using the `.` selection operator to pick a method or property, 

<img src="images/method-dropdown.png" alt="MakeCode editor method dropdown" width="400"/>  

and then hover over the name to invoke the documentation popup.

<img src="images/doc-popup.png" alt="MakeCode editor method dropdown" width="400"/>  

Before we review the array methods, we need to point out what the difference is between methods and properties. Looking back at the material on classes in the previous learning progression, we can see that the array methods look like class methods and the `length` property as a `[<cept>]`_class field_, that is, a data point. The actual implementation is a bit more complicated, due to the need for MakeCode to support devices other than the micro:bit, but from our purposes, we can think of these methods and property as defined in the class `Array`. _Methods_ are called like functions, with parentheses `()`, as in `arr.reverse()`, while _properties_ are called like data fields, without parentheses, as in `arr.length`.

Use the following functions to look at the contents of arrays in the next examples:
```javascript
// Example 1.1.2

function showNumericArray(a : number[]) {
   for (let i=0; i<a.length; i++) {
      basic.showNumber(a[i])
   }
}

function showStringArray(a : string[]) {
   for (let i=0; i<a.length; i++) {
      basic.showString(a[i])
   }
}
```

Now, let's look at the available methods systematically, grouping them by general function:
1. Content methods insert, remove, and replace elements of the array, changing its contents. These are (Note: Arguments, if any, are omitted for brevity.):
   - `push()`, also known as _"append"_, adds an element at the end of the array.    
   - `pop()` removes the last element and returns it.  
   - `insertAt()` inserts an element at an index.  
   - `removeAt()` removes an element at an index.    
   - `set()` sets the value of an element at an index.  
   - `removeElement()` removes the first occurrence of an element.    
   - `fill()` Read the JS documentation on its [usage](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fill).)  
   - `shift()` remove an element from the beginning of the array and return the new length.  
   - `unshift()` add an element at the beginning of the array and return the new length.  
   - `splice()` removes a number of elements from an array, starting at an index.  
   ```javascript
   // Example 1.1.3
   let a : number[] = [5, 8, 12, 91, 41, 0, 22]
   a.push(13)
   showNumericArray(a)
   
   basic.showNumber(a.pop())
   
   a.insertAt(2, 56)
   showNumericArray(a)

   basic.showNumber(a.removeAt(1))
   
   a.set(0, 22)
   showNumericArray(a)
   
   if (a.removeElement(22)) {
       basic.showString("Successfully removed!") 
       showNumericArray(a)
   }

   a.fill(87, 2, 4)
   showNumericArray(a)
   ```
2. Accessor methods:
   - `get()` return the value of the element at an index. `a.get(5)` is equivalent to `a[5]`.  
   - `indexOf()` returns the index of an element, if found, or `-1`, if not found.  
   - `find()` returns the value of the first element in the array that satisfies the boolean criterion function passed as argument.  
   - `slice()` returns a section of an array between two indices as another array.  
   ```javascript
   // Example 1.1.4
   let a : number[] = [5, 8, 12, 91, 41, 0, 22]
   basic.showNumber(a.indexOf(91))  // returns 3
   
   basic.showNumber(a.indexOf(87))  // returns -1 (no 87 in the array)
   
   function odd(a : number, index : number) { return a % 2 == 1 }  // the second parameter is required though not used
   basic.showNumber(a.find(odd))
   
   let c = a.slice(2, 5)  // the end index, here 5, is not included
   showNumericArray(c)
   ```
3. Order methods, which change the order of the elements:
   - `reverse()` permanently reverses the order of the elements of the array on which it was called.  
   - `sort()` returns the array sorted `[<cept>]`_in place_, meaning the array remains sorted after the call. `reverse()` is also in-place.    
   ```javascript
   // Example 1.1.5
   
   let a : number[] = [5, 8, 12, 91, 41, 0, 22]
   a.reverse()
   showNumericArray(a)
   showNumericArray(a.sort())  // note that the array a is now sorted
   ```
4. Methods on two arrays:
   - `concat()` returns a new array with the argument array concatenated (that is, appended) to the array on which it was called.  
   ```javascript
   // Example 1.1.6
   
   let a : number[] = [5, 8, 12]
   let b : number[] = a.concat([91, 41, 0, 22])
   showNumericArray(b)
   ```
5. String-specific methods:
   - `join()`, for `string` arrays, concatenates the elements, delimited by a `[<cept>]`_separator_.  
   ```javascript
   // Example 1.1.7

   let a : string[] = ["Learning", "progression", "003"]
   showStringArray(b)
   basic.showString(a.join(" "))  // the separator is a space (that is, " ")
   ```
6. Boolean methods:
   - `every()` tests of all elements satisfy a criterion specified as a funciton.   
   - `some()` tests of all elements satisfy a criterion specified as a funciton.  
   ```javascript
   // Example 1.1.8

   let a : number[] = [5, 8, 12]

   function odd(a : number, index : number) { return a % 2 == 1 }  // the second parameter is required though not used
   function even(a : number, index : number) { return a % 2 == 0 }  // the second parameter is required though not used

   if (a.every(odd))
      basic.showString("All odd!")
   else if (a.every(even))
      basic.showString("All even!")
   else
      basic.showString("Even and odd!")
   ```
7. General methods applying a `[<cept>]` callback function on every element. (Notice that `find()`, `every()`, and `some()` also take callbacks as arguments, but they have very specific function.)
   - `map()` applies a callback function to each element of an array and returns the resulting array. The original array is not modified.  
   - `forEach()` applies a callback function to each element of an array.  The original array is not modified.  
   - `reduce()` applies a callback function to each element, while aggregating the result.  
   ```javascript
   // Example 1.1.9
   let words : string[] = ["HIPY", "PAPY", "BTHUTHDTH", "THUTHDA", "BTHUTHDY"]

   showStringArray(words.map(function (value: string, index: number) {
       return value.toLowerCase()
   }))

   let shortWords : string[] = ["hop", "baby", "nose", "scat", "grog"]

   shortWords.forEach(function (value: string, index: number) {
       let numeral : string
       switch (index) {
           case 0:
           numeral = "first"
           break
           case 1:
           numeral = "second"
           break
           case 2:
           numeral = "third"
           break
           default:
           numeral = `${ index + 1 }th`
           break
       }
       basic.showString(`The ${ numeral }th element is ${ value }.`)
   })
   
   let a : number[] = [4, 9, 2, 4]

   basic.showString(`The sum of array elements is ${ 
       a.reduce(
           function (previousValue: number, currentValue: number, currentIndex: number) {
               return previousValue + currentValue
           }, 
           null) 
   }`)
   ```
##### Multi-dimensional arrays
[[toc](#table-of-contents)]

`[<lernact-rd>]`Multi-dimensional arrays are _arrays of arrays_. In other words, the base type of multi-dimensional array is also a (multi-dimensional) array. The number of dimensions is indicated by the number of `[]` pairs after the base type of the innermost array, as in `let threeDimensionalGrid : number[][][]`. The indexing of elements works by level, from the outermost to the innermost, as in `threeDimensionalGrid[5][4][10]` references the value of _the element of index 10 of the element of index 4 of the element of index 5_. This is a lot easier to understand with an example:
```javascript
// Example 1.1.10

let path = [
    [0, 0], [1, 0], [2, 0], [3, 0], [4, 0], // top row to the right
    [4, 1], [4, 2], [4, 3], [4, 4],         // right column down
    [3, 4], [2, 4], [1, 4], [0, 4],         // bottom row to the left
    [0, 3], [0, 2], [0, 1],                 // left column up
    [1, 1], [2, 1], [3, 1],                 // top but 1 row to the right (remaining headitions)
    [3, 2], [3, 3],                         // right but 1 column down (remaining headitions)
    [2, 3], [1, 3],                         // bottom but 1 row to the left (rem head)
    [1, 2],                                 // left but 1 col up (rem head)
    [2, 2]                                  // center
]

const SNAKE_LEN: number = 7                 // snake length parameter
let snake: number[] = []                    // snake represented by trajectory indices
for (let i = - SNAKE_LEN; i < 0; i++)
    snake.push(i)                           // populate snake array

// the snake goes back and forth along the path
basic.forever(function () {
    let head: number = 0
    let tail: number
    while (head < 25) {
        led.plot(path[head][0], path[head][1])
        snake.push(head++)
        tail = snake.removeAt(0)
        if (tail >= 0)
            led.unplot(path[tail][0], path[tail][1])
        basic.pause(200)
    }

    // reverse the snake "in place"
    head = tail
    tail = 24
    while (tail > 0) {
        if (head >= 0)
            led.plot(path[head][0], path[head][1])
        snake.insertAt(0, head--)
        tail = snake.pop()
        led.unplot(path[tail][0], path[tail][1])
        basic.pause(200)
    }
})
```
Things to notice here:
1. The `path` variable is a two-dimensional array representing the trajectory of the snake. It contains 25 (x, y) positions on the 5x5 grid, which are so arranged that the `snake` travels along a tightening spiral, touching every position in the grid.  
2. The `snake` itself is a one-dimensional array of 7 consecutive indices into the the `path` array. `head` is the index of the snake's front, and `tail` is the index of the snake's back. The snake travels head forward. So, to show the snake, we use calls to `led.plot()` with coordinates `path[head][0]` for the x parameter and `path[head][1]` for the y parameter.  
3. Because the snake is moving, we advance the `head` and remove at the `tail`.
    
#### 2. Apply  
[[toc](#table-of-contents)]

1. `[<lernact-prac>]`Create an array of the numbers 1 to 100, inclusive. Do not waste your time typing the numbers. Write a loop and use the appropriate array method to add elements. In a separate loop, display the last 17 numbers.  
2. `[<lernact-prac>]`Using the method of the [Sieve of Eratosthenes](https://www.smartickmethod.com/blog/math/operations-and-algebraic-thinking/divisibility/prime-numbers-sieve-eratosthenes/), update your program from 1.2.1 to go through the array and leave only the prime numbers. Show the remaining numbers in a loop.  
3. `[<lernact-prac>]`Modify the program from Example 1.1.10 so that the snake appears from the center, goes to the top left corner and returns back.

#### 3. Present  
[[toc](#table-of-contents)]

In the [programs](programs) directory:
1. Add your program from 1.2.1 with filename `microbit-program-1-2-1.js`.  
2. Add your program from 1.2.2 with filename `microbit-program-1-2-2.js`.  
3. Add your program from 1.2.3 with filename `microbit-program-1-2-3.js`.  

In the [Lab Notebook](README.md):
1. Link to the program from 1.2.1.  
2. Link to a demo video showing the execution of the program from 1.2.1.  
3. Link to the program from 1.2.2.  
4. Link to a demo video showing the execution of the program from 1.2.2.  
5. Link to the program from 1.2.3.  
6. Link to a demo video showing the execution of the program from 1.2.3.  


### 2. Screensavers   
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

   - code writing simulation in work mode  
     - note: scroll up the already written text, adding one line at a time, except the first 4  
   - "rain" (Ivo)  
     - challenge: rain at 45°
   - [fireworks](https://github.com/Introduction-to-Computer-Engineering/screensavers-for-the-micro-bit-AKA-turtle/blob/master/screensaver.js) (Dwight)  
     - TODO:
       - simplify code  
       - have radial burst with dynamics  
     - challenge: pre-explosion arc  
   - bouncy ball (Dwight)  
     - should add horizontal motion? => too short a path, unless we bounce off the walls  
     - challenge: change the "bouncing" coefficient of the ball  
   - [snake](https://github.com/iconoptic/snake-microbit/blob/master/snake.js) (Brendan)  
     - TODO:
       - simplify logic & code  
       - relate to LP002 snake  
   - frequency bar (Ivo)
     - challenge: smooth out, as in a real piece of music    
   - (CHALLENGE) pond ripples  
     - TODO:
       - fading away from drop splash point  
       - interference patterns with brightness  
     - challenge: reflection and further fading at the walls  
     
#### 2. Apply
[[toc](#table-of-contents)]

#### 3. Present
[[toc](#table-of-contents)]

### 3. Program structure  
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

   - global vars  
   - function and class declarations  
   - event handlers  
   - forever loops  
   - proper indentation and style guide

#### 2. Apply
[[toc](#table-of-contents)]
#### 3. Present
[[toc](#table-of-contents)]
   
### 4. Divide & conquer: program decomposition  
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

   - high-level program structure:  
     - 2 "modes": working and asleep  
     - code writing in working mode  
     - 5 gestures for five screensavers in asleep mode  
   - analysis and decomposition of target programs   
     - using arrays to match gestures and ss functions  

#### 2. Apply
[[toc](#table-of-contents)]
#### 3. Present
[[toc](#table-of-contents)]
   
### 5. Randomized behavior  
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

    - dimensions of randomization  
    - the family of random functions  (`random`, `randint`, `randomBoolean()`, etc.)   
    - write your own custom randomization routines  
    - the bouncing-ball randomization (multiple dimensions)  

#### 2. Apply
[[toc](#table-of-contents)]
#### 3. Present
[[toc](#table-of-contents)]
   

### 6. Encapsulation    
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

   - the benefits of encapsulation  
   - functions
   - classes   
   - namespaces (`basic`, `input`, `game`, etc.)    

#### 2. Apply
[[toc](#table-of-contents)]
#### 3. Present
[[toc](#table-of-contents)]
   
### 7. Functions revisited  
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

   - Pass by value, pass by reference  
     ```javascript
     let arr : number[] = [1, 2, 3]

     function double(a : number[]) {
         for (let i = 0; i < arr.length; i ++)
             a[i] *= 2
     }

     double(arr)

     arr.forEach(function (value: number, index: number) {
         basic.showNumber(value)    
     })
     ```  
   - Function signatures & usage  
     - return a value  
     - return a modified argument  
     - change in place  

#### 2. Apply
[[toc](#table-of-contents)]
#### 3. Present
[[toc](#table-of-contents)]
   
### 8. Classes revisited    
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

   - object properties  
   - object literals: objects as dictionaries  
   - in JS, [classes are functions under the hood](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)  
   - TODO  
     - [Static TS](https://www.microsoft.com/en-us/research/publication/static-typescript/) implementation  
     - prototypes (too much)  
     - JS vs TS  

#### 2. Apply
[[toc](#table-of-contents)]
#### 3. Present
[[toc](#table-of-contents)]
   
### 9. Code reading
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

[`game.ts`](https://github.com/microsoft/pxt-microbit/blob/master/libs/core/game.ts)  
   - export  
   - functions (`createSprite`)  
   - classes (`LedSprite`)  
   - namespaces (`game`)  
   - use of variables  
   - TODO:
     - micro:bit [tech docs](https://makecode.com/docs)  
     - TS [namespaces](https://www.typescriptlang.org/docs/handbook/namespaces.html)  

#### 2. Apply
[[toc](#table-of-contents)]

#### 3. Present
[[toc](#table-of-contents)]

   
### 10. Iterative development with Github  
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

   - status, add, commit, pull, push  
   - remote & local (git SCM)  
   - Github workflow (pull requests, Github Classroom **Feedback**)  
   - informative commit messages  
   - releases & tags  
   - incremental development example

#### 2. Apply
[[toc](#table-of-contents)]
#### 3. Present
[[toc](#table-of-contents)]
   
### 11. Reactive system  
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

`forever` function vs `while` loop  
feature | `forever` | `while`
-- | -- | --
condition | no | yes
`break` | no | yes
scheduling | yes | no
simulator fidelity | yes | no

    - [reactive system](https://makecode.microbit.org/device/reactive)  
    - Why you shouldn't have event handling in a `forever` loop  
    - How is `pause` executed and what is affected (e.g. other repeated behavior, event handling, etc.)  
      - `pause()` should be avoided, especially with multiple `forever()` loops  
    - Advanced material: [software stack](https://mattwarren.org/2017/11/28/Exploring-the-BBC-microbit-Software-Stack/)  
      - threads, fibers, and the [fiber scheduler](https://lancaster-university.github.io/microbit-docs/advanced/)  
      - issues of speed, memory, etc.  
      - (Brendan) Does a time slice have to end for event handling to proceed?  

#### 2. Apply
[[toc](#table-of-contents)]
#### 3. Present
[[toc](#table-of-contents)]
   
### 12. Matrix dynamics  
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

    - can use out-of-bound coordinates in `plot()` and `unplot()`  
    - don't use `pause()`, `show*()` for smooth graphics 
    - `clearScreen()` is often necessary but it's fast, so no problem  
    - why do we need `pause()` after `clearScreen()`?
      ```javascript
      while (true) {
          if (isHeart)                                             
              basic.showIcon(IconNames.Heart)
          else
              basic.showIcon(IconNames.Butterfly)
          basic.pause(100)
          basic.clearScreen()
          basic.pause(100)                             // THIS IS REQUIRED TO SEE THE ICON BLINK
      }
      ```
    - _frame_-based display for speed and smoothness  
    - mod-based timing  
      - simulator vs device  
      - fine-tuning

#### 2. Apply
[[toc](#table-of-contents)]
#### 3. Present
[[toc](#table-of-contents)]
   

