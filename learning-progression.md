# CPE 1040

This is Learning Progression 003 of the course CPE 1040: Introduction to Computer Engineering at MSU Denver.

Table of Contents
=================

* [CPE 1040](#cpe-1040)
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
        * [Overview](#overview)
        * [Code writing](#code-writing)
        * [Rain](#rain)
        * [Frequency bar](#frequency-bar)
      * [2\. Apply](#2-apply-1)
      * [3\. Present](#3-present-1)
    * [3\. Program structure](#3-program-structure)
      * [1\. Study](#1-study-2)
        * [Overall program structure](#overall-program-structure)
        * [Global variables](#global-variables)
        * [Function and class declarations](#function-and-class-declarations)
        * [Event handler registrants](#event-handler-registrants)
        * [Main program (forever loop)](#main-program-forever-loop)
        * [Proper indentation](#proper-indentation)
      * [2\. Apply](#2-apply-2)
      * [3\. Present](#3-present-2)
    * [4\. Divide &amp; conquer: program decomposition](#4-divide--conquer-program-decomposition)
      * [1\. Study](#1-study-3)
        * [Two modes: working &amp; asleep](#two-modes-working--asleep)
        * [Sub\-programs](#sub-programs)
        * [Matching gestures and screensavers](#matching-gestures-and-screensavers)
      * [2\. Apply](#2-apply-3)
      * [3\. Present](#3-present-3)
    * [5\. Randomized behavior](#5-randomized-behavior)
      * [1\. Study](#1-study-4)
        * [Importance of randomization](#importance-of-randomization)
        * [Pseudorandom numbers](#pseudorandom-numbers)
        * [Random functions](#random-functions)
        * [Randomization in the target program](#randomization-in-the-target-program)
        * [Bouncing marbles](#bouncing-marbles)
        * [Simulator infidelity](#simulator-infidelity)
        * [Thread unsafety](#thread-unsafety)
      * [2\. Apply](#2-apply-4)
      * [3\. Present](#3-present-4)
    * [6\. Encapsulation](#6-encapsulation)
      * [1\. Study](#1-study-5)
        * [Benefits of encapsulation](#benefits-of-encapsulation)
        * [Functions](#functions)
        * [Classes](#classes)
        * [Namespaces](#namespaces)
      * [2\. Apply](#2-apply-5)
      * [3\. Present](#3-present-5)
    * [7\. Functions revisited](#7-functions-revisited)
      * [1\. Study](#1-study-6)
        * [Input\-output contract](#input-output-contract)
        * [Pass by value vs pass by reference](#pass-by-value-vs-pass-by-reference)
        * [Function naming](#function-naming)
        * [Recursive functions](#recursive-functions)
      * [2\. Apply](#2-apply-6)
      * [3\. Present](#3-present-6)
    * [8\. Classes revisited](#8-classes-revisited)
      * [1\. Study](#1-study-7)
        * [Classes are type definitions](#classes-are-type-definitions)
        * [Exceptions](#exceptions)
        * [Objects are dictionaries](#objects-are-dictionaries)
        * [Getters and setters](#getters-and-setters)
      * [2\. Apply](#2-apply-7)
      * [3\. Present](#3-present-7)
    * [9\. Code reading](#9-code-reading)
      * [1\. Study](#1-study-8)
        * [game\.ts](#gamets)
        * [enum types](#enum-types)
        * [Namespace game](#namespace-game)
        * [Exported functions](#exported-functions)
        * [Class LedSprite](#class-ledsprite)
      * [2\. Apply](#2-apply-8)
      * [3\. Present](#3-present-8)
    * [10\. Iterative development with Github](#10-iterative-development-with-github)
      * [1\. Study](#1-study-9)
        * [Git command line](#git-command-line)
        * [Git remote and local](#git-remote-and-local)
        * [Git commands](#git-commands)
        * [Git branch and merge](#git-branch-and-merge)
        * [Github workflow](#github-workflow)
        * [Incremental development](#incremental-development)
      * [2\. Apply](#2-apply-9)
      * [3\. Present](#3-present-9)
    * [11\. Reactive system](#11-reactive-system)
      * [1\. Study](#1-study-10)
        * [Software stack](#software-stack)
        * [Fiber scheduling](#fiber-scheduling)
        * [Events revisited](#events-revisited)
        * [forever vs while](#forever-vs-while)
      * [2\. Apply](#2-apply-10)
      * [3\. Present](#3-present-10)
    * [12\. Matrix dynamics](#12-matrix-dynamics)
      * [1\. Study](#1-study-11)
        * [Out\-of\-bound coordinates](#out-of-bound-coordinates)
        * [Smooth graphics](#smooth-graphics)
        * [Speed and scheduling](#speed-and-scheduling)
        * [Mod\-based timing](#mod-based-timing)
        * [Frame\-based display](#frame-based-display)
        * [Simulator fidelity revisited](#simulator-fidelity-revisited)
      * [2\. Apply](#2-apply-11)
      * [3\. Present](#3-present-11)
  * [Resources](#resources)


## Learning Progression 003: Screensavers
[[toc](#table-of-contents)]

This progression is the culmination of the first part of the course, in which we program the bear-bones micro:bit without any extenral circuitry attached and without communication features. We pull together all the programming language features and best practices that we introduced in the previous two learning progressions, to write a significantly larger target program over 12 steps. This will present the opportunity to learn about some of the design considerations a programmer makes when approaching a larger project. The progression is also going to dig a bit deeper into the _softare stack_ of the micro:bit, and uncover the ways it affects these considerations.

### 1. Arrays revisited  
[[toc](#table-of-contents)]

#### 1. Study  
[[toc](#table-of-contents)]

##### Arrays
[[toc](#table-of-contents)]

We have already seen how versatile and powerful arrays can be in a program, allowing us to achieve complex program behavior far more easily than if arrays weren't available to the programming language. Let's quickly review what arrays are. An _array_ is an _ordered sequence_ of elements _of the same type_. Because it holds more than one piece of data, it is also called a [_data structure_](https://en.wikipedia.org/wiki/Data_structure). Like any other variable and function, an array has a _name_. This name can be used to refer not only to the whole array, but to individual elements of the array. Because they are ordered, they can be referenced by _index_, that is, by their place in the order, using the _selection operator_ `[]` (opening and closing square bracket). Let's take a look:
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
1. In `let firstPrimes...`, it indicates an array data type by attaching to the right of the _base type_. We are declaring an array of numbers, so the base time is `number`, and the type of the array variable `firstPrimes` is `number[]`. The single pair of brackets `[]` also indicates that this is _unidimensional_ array.  
2. In `let favoritePrime...`, it selects a particular element of the array, in this case the one with index 3, making it the forth element. Note that the array index always starts at 0.  
3. In `firstPrimes[i]`, it picks out the element, the index of which is equal to the current value of the loop variable `i`. So, the `[]` operator admits _expressions_ between the brackets, as long as they evaluate to an _integer_ value. That is, the result of evaluating the expression has to be a whole number. In addition, the integer has to be in the index _range_ of the array. That is, the number between the brackets has to be among the valid indices of the array. In our case, the range is [0, 9].  

##### Array methods
[[toc](#table-of-contents)]

The usefulness of the arrays doesn't stop with the ability to keep a collection of data together. Arrays come with many useful _methods_ and _properties_ for manipulating the elements of the collection or the whole collection itself. In Example 1.1.1, we already encountered the `length` property. The best way to explore methods in MakeCode is to declare an array variable, invoke the dropdown by using the `.` selection operator to pick a method or property, 

<img src="images/method-dropdown.png" alt="MakeCode editor method dropdown" width="400"/>  

and then hover over the name to invoke the documentation popup.

<img src="images/doc-popup.png" alt="MakeCode editor method dropdown" width="400"/>  

Before we review the array methods, we need to point out what the difference is between methods and properties. Looking back at the material on classes in the previous learning progression, we can see that the array methods look like class methods and the `length` property as a _class field_, that is, a data point. The actual implementation is a bit more complicated, due to the need for MakeCode to support devices other than the micro:bit, but from our purposes, we can think of these methods and property as defined in the class `Array`. _Methods_ are called like functions, with parentheses `()`, as in `arr.reverse()`, while _properties_ are called like data fields, without parentheses, as in `arr.length`.

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
   - `sort()` returns the array sorted _in place_, meaning the array remains sorted after the call. `reverse()` is also in-place.    
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
   - `join()`, for `string` arrays, concatenates the elements, delimited by a _separator_.  
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
7. General methods applying a  callback function on every element. (Notice that `find()`, `every()`, and `some()` also take callbacks as arguments, but they have very specific function.)
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

Multi-dimensional arrays are _arrays of arrays_. In other words, the base type of multi-dimensional array is also a (multi-dimensional) array. The number of dimensions is indicated by the number of `[]` pairs after the base type of the innermost array, as in `let threeDimensionalGrid : number[][][]`. The indexing of elements works by level, from the outermost to the innermost, as in `threeDimensionalGrid[5][4][10]` references the value of _the element of index 10 of the element of index 4 of the element of index 5_. This is a lot easier to understand with an example:
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

1. Create an array of the numbers 1 to 100, inclusive. Do not waste your time typing the numbers. Write a loop and use the appropriate array method to add elements. In a separate loop, display the last 17 numbers.  
2. Using the method of the [Sieve of Eratosthenes](https://www.smartickmethod.com/blog/math/operations-and-algebraic-thinking/divisibility/prime-numbers-sieve-eratosthenes/), update your program from 1.2.1 to go through the array and leave only the prime numbers. Show the remaining numbers in a loop.  
3. Modify the program from Example 1.1.10 so that the snake appears from the center, goes to the top left corner and returns back.

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

##### Overview

This progression has a significant target program as an end goal. This allows us to visit programming topics that would otherwise not arise in a sequence of small few-line example programs. Some of these topics concern programming as a process (e.g. program decomposition, encapsulation, program structure), others have to do with computer resources (e.g. efficient coding, achieving desired behavior within the memory and processor speed limitations of the target device), and still others address user interface design (e.g. responsiveness, intuitive dynamics). The details of the implementation of the computer's software stack may bear directly on any of these topics. Exploring these is the point of this progression, and thus it is the culmination of the first part of the course, in which we only program the bear micro:bit, without any external circuitry.

The target program consists of several smaller sub-programs, which jointly simpulate a computer, on which a programmer codes, and on which various screensavers display when the computer is "asleep". See this overview [video of the overall program operation](https://msudenver.yuja.com/Dashboard/Permalink?authCode=1778867948&b=1761370&linkType=video), including the coding simulation in work mode and two sceensavers, one simulating rain and the other a frequency bar.

##### Code writing

Here is a longer [video of the code-writing simulation](https://msudenver.yuja.com/Dashboard/Permalink?authCode=5150693&b=1799587&linkType=video). Notice the scrolling after the first page is exhausted.

##### Rain

Here is a longer [video of the rain simulation screensaver](https://msudenver.yuja.com/Dashboard/Permalink?authCode=1875257468&b=1799524&linkType=video). Notice how the "farther" (dimmer) raindrops, which look like they are falling in the background, are falling _faster_. Similarly, the ones at the forefront, are brightest and fall slowest. This is what you would see if you are looking at rain.

##### Frequency bar

Here is a longer [video of the frequency bar simulation screensaver](https://msudenver.yuja.com/Dashboard/Permalink?authCode=45885861&b=1799554&linkType=video). Notice how the highest point to which a frequency column rises in a single beat lingers lit up until the column fades down completely. This is common behavior of frequency bars, in which the overall frequency envelope of the music signal is displayed.
     
#### 2. Apply
[[toc](#table-of-contents)]

1. Write a standalone program to simulate the code writing sub-program. Guidelines and hints:
   1. First, write a program that can draw 5 "program lines" of different lengths, from left to right.  
   2. Notice that at all times, there are _at most_ 5 lines on the screen. Does that perhaps suggest an array of line lengths? How would you add and remove lines to keep it at most 5-element long?  
   3. Finally, notice that while writing the "first page" of the program, there is no scrolling until the fifth line is reached. How would you modify your program to achieve this?  
   
2. Write a standalone program to simulate rain for one of the screensavers. Guidelines and hints:
   1. First, write a program to have LED "raindrops" fall from top to bottom, and disappear at the bottom of the screen.  
   2. Now make them vary in brightness.  
   3. Now think how you can have some of the go faster than others, and match that with the brightness. _You don't have to get this right in this step, but it will help to think about it and generate some ideas._
   
3. Write a standalone program to simulate a frequency bar for one of the screensavers. Guidelines and hints:
   1. First, write a program that can plot LED columns _from botton to top_ and back. _Note the vertical coordinate grows from top to bottom, so you will need to invert it._    
   2. Randomize the height the way you randomized the line length in the code-writing simulation, and make the highest point show at highest brightness. _Can you see another application of an array of highest point vertial coordinates?_    
   3. How would you make the column retreat down while the highest point stays until the columns is gone, and only then turns off?  

#### 3. Present
[[toc](#table-of-contents)]

In the [programs](programs) directory:
1. Add your program from 2.2.1 with filename `microbit-program-2-2-1.js`.  
2. Add your program from 2.2.2 with filename `microbit-program-2-2-2.js`.  
3. Add your program from 2.2.3 with filename `microbit-program-2-2-3.js`.  

In the [Lab Notebook](README.md):
1. Link to the program from 2.2.1.  
2. Link to a demo video showing the execution of the program from 2.2.1.  
3. Link to the program from 2.2.2.  
4. Link to a demo video showing the execution of the program from 2.2.2.  
5. Link to the program from 2.2.3.  
6. Link to a demo video showing the execution of the program from 2.2.3.  


### 3. Program structure  
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

##### Overall program structure

In a large program, proper structure is essential. While the particular structure is somewhat arbitrary, general guidelines and conventions are quick to appear in any programming domain. One important factor in coming up with a good structure for a large program is whether the program can contain multiple files or just a single one. The MakeCode micro:bit environment allows for only one user-defined source file at a time, with all the rest of the functionality (language runtime, device runtime, MakeCode and user-defined packages) all come precompiled and are not modifiable from inside the user program. For our single-file micro:bit programs, the following structure has emerged:

```
 _____ _       _           _                   _       _     _            
|  __ \ |     | |         | |                 (_)     | |   | |           
| |  \/ | ___ | |__   __ _| | __   ____ _ _ __ _  __ _| |__ | | ___  ___  
| | __| |/ _ \| '_ \ / _` | | \ \ / / _` | '__| |/ _` | '_ \| |/ _ \/ __| 
| |_\ \ | (_) | |_) | (_| | |  \ V / (_| | |  | | (_| | |_) | |  __/\__ \ 
 \____/_|\___/|_.__/ \__,_|_|   \_/ \__,_|_|  |_|\__,_|_.__/|_|\___||___/ 
                                                                          
 __________________________________________________________________________________________________________________ 
/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/ 
                                                                          


  ______                _   _                               _        _                     _           _                 _   _                 
 |  ____|              | | (_)                             | |      | |                   | |         | |               | | (_)                
 | |__ _   _ _ __   ___| |_ _  ___  _ __     __ _ _ __   __| |   ___| | __ _ ___ ___    __| | ___  ___| | __ _ _ __ __ _| |_ _  ___  _ __  ___ 
 |  __| | | | '_ \ / __| __| |/ _ \| '_ \   / _` | '_ \ / _` |  / __| |/ _` / __/ __|  / _` |/ _ \/ __| |/ _` | '__/ _` | __| |/ _ \| '_ \/ __|
 | |  | |_| | | | | (__| |_| | (_) | | | | | (_| | | | | (_| | | (__| | (_| \__ \__ \ | (_| |  __/ (__| | (_| | | | (_| | |_| | (_) | | | \__ \
 |_|   \__,_|_| |_|\___|\__|_|\___/|_| |_|  \__,_|_| |_|\__,_|  \___|_|\__,_|___/___/  \__,_|\___|\___|_|\__,_|_|  \__,_|\__|_|\___/|_| |_|___/
                                                                                                                                               
                                                                                                                                               
 __________________________________________________________________________________________________________________ 
/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/ 
                                                                          

  ______               _          _                     _ _                            _     _                   _       
 |  ____|             | |        | |                   | | |                          (_)   | |                 | |      
 | |____   _____ _ __ | |_ ______| |__   __ _ _ __   __| | | ___ _ __   _ __ ___  __ _ _ ___| |_ _ __ __ _ _ __ | |_ ___ 
 |  __\ \ / / _ \ '_ \| __|______| '_ \ / _` | '_ \ / _` | |/ _ \ '__| | '__/ _ \/ _` | / __| __| '__/ _` | '_ \| __/ __|
 | |___\ V /  __/ | | | |_       | | | | (_| | | | | (_| | |  __/ |    | | |  __/ (_| | \__ \ |_| | | (_| | | | | |_\__ \
 |______\_/ \___|_| |_|\__|      |_| |_|\__,_|_| |_|\__,_|_|\___|_|    |_|  \___|\__, |_|___/\__|_|  \__,_|_| |_|\__|___/
                                                                                  __/ |                                  
                                                                                 |___/                                   
 __________________________________________________________________________________________________________________ 
/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/_____/ 
                                                                          

  __  __       _                                                      ____                                _                 __  
 |  \/  |     (_)                                                    / / _|                              | |                \ \ 
 | \  / | __ _ _ _ __    _ __  _ __ ___   __ _ _ __ __ _ _ __ ___   | | |_ ___  _ __ _____   _____ _ __  | | ___   ___  _ __ | |
 | |\/| |/ _` | | '_ \  | '_ \| '__/ _ \ / _` | '__/ _` | '_ ` _ \  | |  _/ _ \| '__/ _ \ \ / / _ \ '__| | |/ _ \ / _ \| '_ \| |
 | |  | | (_| | | | | | | |_) | | | (_) | (_| | | | (_| | | | | | | | | || (_) | | |  __/\ V /  __/ |    | | (_) | (_) | |_) | |
 |_|  |_|\__,_|_|_| |_| | .__/|_|  \___/ \__, |_|  \__,_|_| |_| |_| | |_| \___/|_|  \___| \_/ \___|_|    |_|\___/ \___/| .__/| |
                        | |               __/ |                      \_\                                               | |  /_/ 
                        |_|              |___/                                                                         |_|      
```
ASCII art acknowledgement: [taag](http://patorjk.com/software/taag/#p=display&f=Big&t=Type%20something)

In the rest of the sections, we'll briefly explain each of these program regions. All examples are assembled in the program in Example 3.1.1 at the end of the Study section.

##### Global variables

Global variables are variables that are in the top-level scope of the program, and are thus visible to all the program's components, including functions and classes. They are the main _program data_ (aka _program state_). In general, there should be a minimal number of global variables, thought the single-file environment mitigates most of the risks. Nevertheless, it makes good sense to put the at the very top of the program. This makes them easy to find, helps avoid duplication, and gives a brief overview of the program to a new reader. In Example 3.1.1, our global variable, against which all program operations are performed, is the `balls` array.

##### Function and class declarations

Functions and classes are _named_ encapsulation structures, which help modularize the program code and prevent duplication of code. Functions have input and output, and can have local data needed for their operation. Functions are _called_ by invoking their name and specifying the necessary arguments, if any, between parentheses. While not all functions have _parameters_ (meaning the declarations of the _arguments_), a function call **requires** the parentheses `()`. In Example 3.1.1, we have two functions, `createBalls()` and `bounceBalls()`. Note that they have distinct functionality, properly communicated by their names.

Classes are the backbone of the object-oriented programming paradigm, allowing programmers to define their own types, known as _user-defined types_, by encapsulating complex data and determiniting the exact set of computational operations that can be performed on them. Classes are thus the templates for the creation of user-type entities, called _objects_.

Keeping functions and classes clustered together follows the _library_ (aka _application programming interface (API)_) paradigm, in which all the functions and user data types available to the programmer are presented in an exhaustive and descriptive list.

##### Event handler registrants

Events are phenomena, internal or external to the computer's processor, that the processor has to be informed of. There are two ways to communicate events to the processor: _interrupts_, which are signals sent by the event originator to the processor and which the processor inteprets and acts on, and _polling_, which is a process of cyclic interrogation of the possible originators by the processor. The micro:bit actually uses a hybrid method, where on the hardware level interrupts are used, but the device and language runtimes actually implement polling. The MakeCode packages which are involved in, among other thigns, various event detection and response are `input`, `pins`, `radio`, `conrol`, and `serial`. The way the processor and/or runtime responds to an event is by assigning an _event-handler_ function to each event. In MakeCode, this is done by event-handler _registrants_, which are themselves functions, which take the event-handler functions as one of their arguments. In Example 3.1.1, we have a `Gesture` event-handler registrant, called `input.onGesture`. It takes two arguments: the name of the gesture, in this case `Shake`, and the event-handler to be executed upon detection of the shake-gesture event, namely `function () { balls = createBalls(); }`.

Due to the way they are executed, event handlers should not be put inside loops, functions, or classes, but at the top level of the program, and clustered together so that it is easy to see at a glance what events the program is listening to. More on this in a later step.

##### Main program (forever loop)

The main program contains the main program loop, in the case of MakeCode micro:bit, most often a `basic. forever()` loop function. It is best to keep the contents of the loop short and descriptive, usually by encapsulating the details away into functions and classes. In Example 3.1.1, the only function that the main program loop is calling is `bounceBalls()`, and nothing else, making the intent of the program exceedingly obvious and setting firm expectations of the program behavior that may be observed.

##### Proper indentation

Lastly, proper program structure can be easily defeated if the proper language-specific indentation style is not adopted. In general, the rules are as follows:
1. Top-level constructs (e.g. declarations) start at column 0 (that is, flush against the left-hand edge of the editor).  
2. Each encapsulation (aka scope) nesting (e.g. function block/body, conditional statement block/body, and the full contents of a class) are started **4 characters in**.  
3. Whether the opening brace `{` of a block is at the end of the preceding line, like
```javascript
function foo() {
    // function body
}
```
or at the start of the new line, 
```javascript
function foo() 
{
    // function body
}
```

is a matter of personal style, but it should be _consistent_.

Notice how the proper indentation and consistent style in Example 3.1.1 makes the program easy to read and comprehend at a glance.

```javascript
// Example 3.1.1

/* *** Global variables *** */
let balls : game.LedSprite[] = []

/* *** Function declarations *** */
function createBalls() {
    for (let i = 0; i < 3; i ++) {
        let ball = game.createSprite(Math.randomRange(0, 4),
                                     Math.randomRange(0, 4))
        if (Math.randomBoolean()) {
            if (Math.randomBoolean()) {
                ball.turnLeft(45)
            } else {
                ball.turnRight(45)
            }
        }
        balls.push(ball)
    }
    return balls
}

function bounceBalls() {
    if (balls.length > 0) {
        for (let i = 0; i < 20; i ++) {
            for (let b = 0; b < balls.length; b ++) {
                balls[b].move(1)
                basic.pause(50)
                balls[b].ifOnEdgeBounce()
            }
        }
        for (let b = 0; b < balls.length; b ++)
            balls[b].delete()
    }    
}

/* *** Event-handler registrants *** */
input.onGesture(Gesture.Shake, function () {
    balls = createBalls()
})

/* *** Main program (forever loop) *** */
basic.forever(function () {
    bounceBalls()
})
```

#### 2. Apply
[[toc](#table-of-contents)]

1. Rewrite your program from 2.2.1 to follow the structure presented in this step. Requirements:
   1. The code for the coding simulation should be encapsulated in a funciton, called `coding`.  
   2. The `basic.forever` loop should only call `coding()` and nothing else.  
   
2. Rewrite your program from 2.2.2 to follow the structure presented in this step. Requirements:
   1. The functionality for a raindrop should be encapsulated in a class, called `Raindrop`. You may or may not subclass from `game.LedSprite`, as you wish. Refer to LP002-[9-11] for an example.  
   2. The actual rain should be encapsulated in a function, called `rain`.  
   3. The `basic.forever` loop should only call `rain()` and nothing else.  
   
3. Rewrite your program from 2.2.3 to follow the structure presented in this step. Requirements:  
   1. The code for the coding simulation should be encapsulated in a funciton, called `freqBars`.  
   2. The `basic.forever` loop should only call `freqBars()` and nothing else.  


#### 3. Present
[[toc](#table-of-contents)]
   
In the [programs](programs) directory:
1. Add your program from 3.2.1 with filename `microbit-program-3-2-1.js`.  
2. Add your program from 3.2.2 with filename `microbit-program-3-2-2.js`.  
3. Add your program from 3.2.3 with filename `microbit-program-3-2-3.js`.  

In the [Lab Notebook](README.md):
1. Link to the program from 3.2.1.  
2. Link to a demo video showing the execution of the program from 3.2.1.  
3. Link to the program from 3.2.2.  
4. Link to a demo video showing the execution of the program from 3.2.2.  
5. Link to the program from 3.2.3.  
6. Link to a demo video showing the execution of the program from 3.2.3.  


### 4. Divide & conquer: program decomposition  
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

##### Two modes: working & asleep

It is good to create a development plan for a program that is expected to be large. The most powerful technique is _decomposition_, the breaking up of a large task into smaller pieces, each one of them as independent from the others as possible. In a previous Step, we saw some sub-programs of the large target program, namely the `coding()`, `rain()`, and `freqBars()` functions, each encapsulating an independent simulation. So, we have actually already made steps toward decomposing the large program, specifically by taking a _bottom-up_ approach, in which we first build the small consituent pieces, which we will put together later. 

From the opposite direction, in what we can call _top-down_ approach, the high-level structure of the program is that it has _two mutually exclusive modes_, "working" and "asleep", which have no program behavior in common. Such a case is ideal for a small `enum` class, which creates a type of _named_ elements, as in the following example:
```javascript
// Example 4.1.1

enum Mode { Asleep = 0, Working }

let mode : Mode = Mode.Asleep
```
This is helpful because it maintains maximum _"self-describability"_ of the program. We don't need excessive comments, if the program itself reads like a narrative.

In mode `Working`, we call the `coding()` sub-program, while in mode `Asleep`, we call whichever sub-program corresponds to the last gesture detected (or the default). We can accomplish this easily within a single `basic.forever() {}` loop, which is ideal for our overall program structure.

##### Sub-programs

The most important aspects of the sub-programs `coding()`, `rain()`, and `freqBars()` is that they are _independent of each other_ and are _similarly encapsulated_. Towards the first aspect, only one of these programs is running at a time, and no other program is running _in the background_ to compete for computing resources or perturb the timing of the program currently executing. Toward the second aspect, all of these sub-programs are encapsulated as functions with the same signature, namely no parameters and no return type, as in `function foo() : void {}`. This makes them easy to call from the same place, in our case the `basic.forever()` loop.

We have only looked at 2 screensavers (meaning the programs running in `Asleep` mode) so far, but now that we have a solid program structure, both bottom-up and top-down, we can easily go about developing and adding other screensavers. Just wrap them into a `void` function with no parameters, whether the internal implementation is a function or a class, and add it to the options for the `Asleep` mode. We see two important properties of well-structured programs: _implementation hiding_, which dictates that the implementation details for a certain independent program component need not be visible (in other words, at the top level of the program, we don't care about how a particular screensaver sub-programs is implemented), and _extensibility_, which allows for seamless extension of the functionality of the large program by just adding more options, without changing the overall design and structure.

##### Matching gestures and screensavers

Here, we will also see how the encapsulation, implementation hiding, and extensibility of our structured program design will help us with keeping the main program simple. In particular, how do we match gestures and screensaver programs? Do we use `if...else` cascades, a `switch` statement, or some other construct. Actually, we will use the marvelous property of JavaScript (and, hence TypeScript) that it has _first-class functions_. Let's look at an example:
```javascript
// Example 4.1.2

let gesture : Gesture = Gesture.TiltLeft
let gestures : Gesture[] = [Gesture.TiltLeft, Gesture.TiltRight]

let screensavers = [rain, freqBars]
```
Notice how we have created to parallel arrays, one with gestures, one with screensavers. Notice also that, if we want to add more screensavers and matching gestures, we can just add to these global arrays. How exactly we do the matching is shown in the next example:
```javascript
// Example 4.1.3

basic.forever(function () {
    screensavers[gestures.indexOf(gesture)]()
})
```
Let's unpack this:
1. We can call a function, which is an array element, by combinging the element selection syntax for arrays and the function call syntax, as in `screensavers[0]()`, where `screensavers[0]` is just the function `rain`, and the parentheses `()` at the end end off a proper function call.  
2. Assuming that we have constructed the parallel arrays so that the gestures and screensavers match _by index_, we can use the `indexOf` method to get the index of the last gesture stored in the variable `gesture` in the `gestures` array and then apply this index in the selector for the corresponding screensaver, as we san in (1).  

#### 2. Apply
[[toc](#table-of-contents)]

1. Write a program with two modes, `Working` and `Asleep`. Requirements:
   1. A global variable `mode` of time `Mode` holds he latest gesture detected.  
   2. Mode `Working` is default.  
   3. In mode `Working`, display the single character `W`.  
   4. In mode `Asleep`, display the single character `Z`.  
   5. Button `A` sets the mode to `Asleep`.  
   6. Button `B` sets the mode to `Working`. 

2. Write a program which recognizes two gestures, `TiltLeft` and `TiltRight`. Requirements:
   1. A global variable `gesture` of type `Gesture` holds he latest gesture detected.  
   2. Gesture `TiltLeft` is default.  
   3. When gesture `TiltLeft` is detected, display the single character `L`.  
   4. When gesture `TiltRight` is detected, display the single character `R`.  
   
3. Combine the two programs. Requirements:
   1. In `Working` mode, keep calling `coding()`.  
   2. In `Asleep` mode, keep calling the screensaver function which corresponds to the last gesture detected, or the default.  
      1. `rain()` for `TiltLeft`.  
      2. `freqBars()` for `TiltRight`.  

#### 3. Present
[[toc](#table-of-contents)]
   
In the [programs](programs) directory:
1. Add your program from 4.2.1 with filename `microbit-program-4-2-1.js`.  
2. Add your program from 4.2.2 with filename `microbit-program-4-2-2.js`.  
3. Add your program from 4.2.3 with filename `microbit-program-4-2-3.js`.  

In the [Lab Notebook](README.md):
1. Link to the program from 4.2.1.  
2. Link to a demo video showing the execution of the program from 4.2.1.  
3. Link to the program from 4.2.2.  
4. Link to a demo video showing the execution of the program from 4.2.2.  
5. Link to the program from 4.2.3.  
6. Link to a demo video showing the execution of the program from 4.2.3.  

### 5. Randomized behavior  
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

##### Importance of randomization

We have used _randomization_ in fairly inconsequential ways so far, mostly to have somewhat unpredictable behavior of the output on the micro:bit 5 x 5 matrix. However, randomization is extremely important in science and engineering. Among other things, it allows generating important variation in test and diagnostics programs, achieving nearly-even coverage in probability distribution sampling, and good spreading in hash table storage. The full significance of randomization is well beyond the scope of this course.

##### Pseudorandom numbers

The numbers that the `random` functions return are actually [_pseudorandom_](https://en.wikipedia.org/wiki/Pseudorandom_number_generator), which means that an algorithm generates them in an extremely long evenly spread-out sequence. The number of elements in the whole sequence is so large, that in any specific location along it, there appears to be no relationship between nearby elements. Truly random functions are usually only achieved based on [random physical phenomena](https://www.random.org/randomness/).

##### Random functions

In MakeCode, we have access to three randomization functions:
1. `Math.random()` returns a pseudorandom floating-point (that is, a (possibly _truncated_) real number) number between 0 and 1. _Note that the value of 1 is [not included](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random)._  
2. `Math.randomBoolean()` returns `true` or `false` with the evenness of a pseudorandom generator. This is akin to a _coin toss_. Just like a coin toss, you cannot expect any kind of _alternation_ of `true` and `false`. They are evenly distributed (that is, there is an approximately even number of `true` and `false` value) only in the _limit_ of _infinite_ trials.  
3. `randint(min, max)` is provided as a convenience function in MakeCode and is not usually part of the canonical JavaScript library. It returns _signed integers_, that is the values of the numbers it returns are whole numbers, which can be negative, positive, and/or zero. Curiously, the ordering of the arguments is not enforced. That is, `randint(0, 4)` is functionally equivalent to `randint(4, 0)`. _Note that both min and max are included in the range from which pseudorandom integers are returned._  

Using these functions, you can write your own randomization routines, to fit your purposes.

##### Randomization in the target program

Let's review the randomizations we have used so far in this progression, along with some implementation pointers:
1. `coding()` has a very simple randomization, namely the length of the "code lines", which can be achieved with a straightforward use of `randint(0, 5)` or `randint(1, 5)`, depending on whether we want to have empty lines or not.  
2. `freqBars()` also has a similarly simple randomization, namely the height of the bars. Again, this can be achieved with the use of `randint(0, 4)`. _Note, however, that the vertical coordinate of the LED matrix grows from 0 at the top down to 4 at the bottom, so you need to subtract the number you get from the maximum height. And you may also have to plot LEDs in an inverted `for` loop._  
3. `rain()` has a little more elaborate randomization, namely that it adopts an internal concept of _distance_ in order to move the "raindrops" differently depending on how far they are from the viewer. In particular, there are 5 levels of depth, with 0 being the "closest" and 4 being the "farthest". The raindrops are brighter in the foreground than in the background, and are moving faster across the screen in the foreground than in the background. This kind of randomization requires something other than `basic.pause()` to achieve, because `basic.pause()` causes the processor to idle, regardless of what else might also be running on it. `distance` is used in two ways:
   - first, initialized with `Math.randomRange(0, 4)`, to pick the brightness of the raindrop from the array `brightLevels: number[] = [240, 180, 60, 30, 1]`, and  
   - second, combined with another field called `time_step` (which is initialized to zero in the constructor and also upon reset), to pick how often to let the raindrop fall, in the `fall()` method of the `Raindrop` class:
     ```javascript
     // Example 5.1.1
     
     fall() {
         this.setBrightness(this.brightLevels[this.distance])
         if (this.time_step == this.distance) {                       // let the raindrop fall only when it matches its distance (see last line)
             this.hide()
             this.y = this.y + 1
             this.show()
         }
         this.time_step = (this.time_step + 1) % (this.distance + 1)  // advance time_step modulo the distance (indexed starting at 1, not 0)
     }
     ```
   The rain simulation creates a certain number of raindrops and reuses them when they fall off the bottom, resetting them to a random distance and a random column and wrapping them around to the top. The rain is just an array `let rainfall: Raindrop[] = []` that a `rain()` function cycles through indefinitely. This makes the simulation appear random, rather than a repeating pattern.

Here is one more [video](https://msudenver.yuja.com/Dashboard/Permalink?authCode=1520695895&b=1815435&linkType=video) or the rain, this one with more pronounced variation in brightness.

##### Bouncing marbles

This section introduces a new screensaver, called Bouncing Marbles. Here is a [video](https://msudenver.yuja.com/Dashboard/Permalink?authCode=879279461&b=1815473&linkType=video).

This screensaver probably has the most complex randomization of all that we have seen so far. Just like `rain()`, which used a modulo mechanism to space out the calls to `fall()` for `Raindrop` objects, `bouncing_marbles` uses a modulo mechanism to (i) follow a trajectory with steps spaced at uneven intervals, and (ii) "release" a group of marbles at random intervals, so that they don't all fall together in parallel.

For reference, here is the `trajectory` array, which you may use yourself or modify, as you wish (you _will_ have to modify it for one of the **Optional challenges** below):
```javascript
// Example 5.1.2

enum Falling { Down = 0, Up }
enum Target { Simulator = 0, Microbit }
enum Trajectory { Vertical = 0, Duration, Heading }

this.trajectory = [                  // Heading not necessary but left in for readibility
            [0,  50, Falling.Down],
            [1, 120, Falling.Down],
            [2,  80, Falling.Down],
            [3,  30, Falling.Down],
            [4,  10, Falling.Up],
            [3,  40, Falling.Up],
            [2, 100, Falling.Up],
            [1, 160, Falling.Down],
            [2, 100, Falling.Down],
            [3,  50, Falling.Down],
            [4,  20, Falling.Up],
            [3,  70, Falling.Up],
            [2, 120, Falling.Down],
            [3,  90, Falling.Down],
            [4,  50, Falling.Up],
            [3, 120, Falling.Down],
            [4, 100, Falling.Up],
            [4, 120, Falling.Down]
        ]
```
Please, understand that the numbers in the second column are **not** milliseconds. They only make sense _relative to each other_, and then **only** if other program execution timing factors don't break the proportionality (e.g. extra computation for 5 marbles in comparison to fewer marbles).

Here is a code snippet (not an executable program) from the `move()` method of the `Marble` class:
```javascript
// Example 5.1.3

        if (this.counter % this.trajectory[this.step][Trajectory.Duration] == 0) {
            led.unplot(this.x, this.y)
            this.step ++
            this.counter = 0
            if (this.step == this.trajectory.length) {
                this.active = false
            } else {
                this.y = this.trajectory[this.step][Trajectory.Vertical]
                led.plotBrightness(this.x, this.y, this.y == 4 ? 255 : this.brightness)
            }
        }

        this.counter ++
```
This snippet should help with understanding the function of the `Duration` column times.

Finally, the randomization of the falling marble sets (1 marble, 2 marbles, etc) in the main loop of the `bouncing_marbles` function has four main steps:
1. First, a `numMarbles` is assigned a random number by `randint(1, 5)`. This randomizes the number of marbles that will be released together.    
2. Second, the `numMarbles` are arranged in that many columns. This can be done with an array. This randomizes in which columns each of the number of picked marbles will be bouncing.  
3. Third, in a loop with a modulus mechanism, `numMarbles` `Marble` objects are created with random brightness and specing. This creates the impression that the marbles are _"realeased"_ at differen times.  
4. Fourth, the marble objects, which are themselves kept in an array, have their `move()` method called repeatedly in a round-robin fashion until they are done with their trajectories, at which time they are deleted.

##### Simulator infidelity

You may notice that when `while` loops instead of `basic.forever` for the main loop of your program, you may experience vast difference in execution speed between the micro:bit simulator in MakeCode and the micro:bit device. Usually the `while` loop is much faster than the `basic.forever`. More on this in a later step, but for the `bouncing_marbles()` program, because of having to cycle through multiple ball trajectories and the increased burden of the randomization, the simulator runs about 100 times faster than the device. If you want to use the simulator for development, while still being sure that it will run in a reasonable amount of time on the device, you may need to use a 100 multiplier for the `Duration` column of the `trajectory` array for the simulator, to slow it down relative to the device.

##### Thread unsafety

While we will cover _threads_ (that is, _execution threads_), _multithreading_, and _thread safety_ in a later step, we need to mention that you may encounter the [micro:bit error code](https://makecode.microbit.org/device/error-codes) 980 (`undefined`) when all of a sudden the program tries to call the `move()` method on a `null` (that is, undefined) `Marble` object. _(Error codes are shown on the LED matrix by first showing a `IconNames.Sad` and then scrolling the error number.)_ This is most likely caused by the _"thread unsafety"_ of the micro:bit and is not your fault. In short, the micro:bit has a task scheduler which breaks up longer code blocks into smaller portions to execute, alternating among several so broken-up code sequences. The ordering is somewhat random, which may cause portions of your program to run in the wrong order, relative to the order that you designed them to run in per your program structure.

#### 2. Apply
[[toc](#table-of-contents)]

1. Write a function `randomPrime` that generates random primes in the range [1, 1000]. _How many primes are there in this range?_ Write a small program to demonstrate the operation. _Hint: In a previous Step, you wrote a program to leave only the prime numbers in an array originally filled with the numbers [1, 100]. Extend this program to work for an array filled with the numbers [1, 1000]._    
2. Add depth (aka distance) to your rain simulation, with more distant raindrops appearing dimmer and moving more slowly.  
3. Implement the `bouncing_marbles()` screensaver function and add it to your screensavers program matched to the `Shake` gesture.  
4. **[Optional challenge, max 3 extra step points]** Modify your `rain()` function to show the raindrops falling at 45° to the right.  
5. **[Optional challenge, max 3 extra step points]** Modify your `bouncing_marbles()` to be able to show balls of different trajectories, simulating different elasticity coefficients of the marble material (think steel vs glass vs rubber resin).  

#### 3. Present
[[toc](#table-of-contents)]

In the [programs](programs) directory:
1. Add your program from 5.2.1 with filename `microbit-program-5-2-1.js`.  
2. Add your program from 5.2.2 with filename `microbit-program-5-2-2.js`.  
3. Add your program from 5.2.3 with filename `microbit-program-5-2-3.js`.  
4. Add your program from 5.2.4 with filename `microbit-program-5-2-4.js`.  
5. Add your program from 5.2.5 with filename `microbit-program-5-2-5.js`.  

In the [Lab Notebook](README.md):
1. Link to the program from 5.2.1.  
2. Link to a demo video showing the execution of the program from 5.2.1.  
3. Link to the program from 5.2.2.  
4. Link to a demo video showing the execution of the program from 5.2.2.  
5. Link to the program from 5.2.3.  
6. Link to a demo video showing the execution of the program from 5.2.3.  
7. Link to the program from 5.2.4.  
8. Link to a demo video showing the execution of the program from 5.2.4.  
9. Link to the program from 5.2.5.  
10. Link to a demo video showing the execution of the program from 5.2.5.  


### 6. Encapsulation    
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

##### Benefits of encapsulation  

_Encapsulation_, in computer programming, is the enclosing of computational artifacts (data and code) into _named_ containers (here meaning distinct program regions) for the purpose of avoiding code duplication, program structuring and organization, and abstraction and simplification of the top-level program loop. Encapsulation is a widely used engineering principle, allowing practitioners to implement and users to utilize technology without knowing all the details. It is the greatest way to decrease the _cognitive load_ of both engineering work and technology usage.

The main encapsulation features of computer programming languages, and also available in the single-file MakeCode programming environment for the micro:bit, are _functions_, _classes_, and _namespaces_. Other environments allow for multi-file programs, thus making files part of the encapsulation and abstraction hierarchy of functions, classes, and namespaces. Other languages additionally organize programs into _modules_, _packages_, and other top-level structural elements.

##### Functions

Functions encapsulate _code_. They are _declared_ as _named executable_ sub-programs. A function's name allows the function to execute when when it is _called_. A functions operation can be _parameterized_, that is, the data they operate on can be abstracted. When a parameterized function is called, the caller specifies _arguments_, that is, data for all function parameters. Functions can also return a single instance of any data type. This makes functions encapsulated sub-programs which have input and output. Functions are said to define an _input-output contract_. This contract is said to be a function's _invariant_. The first line of a function, the one that specifies its parameters and return type, is called a _signature_. In JavaScript, functions are _first-class citizens_, meaning they can be used everywhere variables are used.  

```javascript
// Example 6.1.1

function add(a : number, b : number) : number {     // <-- signature
    return a + b                                    // <-- body
}

function randint(min : number, max : number) : number {
    return min + Math.floor(Math.random() * (max + 1 - min))
}

function pause(ms : number) : void {               // <-- no return value
    fiber_sleep(ms)
}

function randomPrime() : number {                  // <-- no parameters
    return primes[randint(0, primes.length-1)]
}

basic.forever(function () {                        // <-- a function without parameters or return value passed as the argument to another function
                               led.plot(2, 2); pause(100); led.unplot(2, 2); pause(100); 
                          }
             )

basic.forever(() =>       {                        // <-- equivalent to previous 
                               led.plot(2, 2); pause(100); led.unplot(2, 2); pause(100); 
                          }
             )

// and, in typical JS shorthand:
basic.forever(() => { led.plot(2, 2); pause(100); led.unplot(2, 2); pause(100); })
```

##### Classes

Classes encapsulate code and data into _objects_ of programmer-defined _data types_. The term _class_ is synonymous with the term _type_, and the two terms are frequently used interchangeably. 

We know data have types. So, why do classes also encapsulate code along with the data? Because a type allows some operations and not others, thus making code a part of the definition of the type. For example, integers and strings allow completely different operations. Their operation sets are actually completely _disjoint_. The overloaded `+` operator does not change that, since it means _addition_ for integers and _concatenation_ for strings. We cannot meaningfully add strings the way we add integers, nor concatenate integers the way we concatenate strings. The _class methods_ comprise an exhaustive set of the operations that can be applied to objects of the class (aka type). In fact, the methods are a stronger determinant of the type than the data fields, as those can be changed without changing the input-output contract of the methods.

##### Namespaces

Namespaces encapsulate data, functions, and types (classes, `enum`, etc). Namespaces are just _named blocks_ (aka _named scopes_), and are declared as follows:
```javascript
// Example 6.1.2

namespace screensaver {
    // code and data, encapsulated in the namespace
    // some of it may be exported (see the next example)
}
```
Everything inside the curly braces `{}` is part of the namespace. A namespace is a _nested scope_. The `screensaver` namespace is nested in the top-level (aka _global_) scope.  

The "packages" of functions in the MakeCode environment (e.g. `basic`, `input`, `leds`, etc.) are all namespaces. If you are curious, you can explore the code of the [core MakeCode library](https://github.com/microsoft/pxt-microbit/tree/master/libs/core). The programming languages in which the files are written can most often be inferred from their _file extensions_:
1. `.ts` stands for TypeScript. _Remember that what we are programming in MakeCode is actually [TypeScript](https://makecode.com/language), despite calling it JavaScript._  
2. `.cpp` stands for C++.  
3. `.h` stands for header file (in C and C++).  
4. `.json` stands for JSON, a simple data format.  
5. `.jres` stands for a JSON file where project resources are stored.  
6. `.s` stands for _assembler_ (aka _assembly language_). This is the form of directly-executable code your programs are translated (the actual term is _compiled_) into. Both terms only make sense in their original historical setting, but have remained in usage ever since.    

Here is part of the `basic` namespace, contained in the [basic.ts](https://github.com/microsoft/pxt-microbit/blob/master/libs/core/basic.ts) file in the MakeCode codebase. The rest is in [basic.cpp](https://github.com/microsoft/pxt-microbit/blob/master/libs/core/basic.cpp), which is written in C++ and you don't have to read it.
```javascript
// Example 6.1.3

namespace basic {

    /**
     * Scroll a number on the screen. If the number fits on the screen (i.e. is a single digit), do not scroll.
     * @param interval speed of scroll; eg: 150, 100, 200, -100
     */
    //% help=basic/show-number
    //% weight=96
    //% blockId=device_show_number block="show|number %number" blockGap=8
    //% async
    //% parts="ledmatrix" interval.defl=150
    export function showNumber(value: number, interval?: number) {
        showString(Math.roundWithPrecision(value, 2).toString(), interval);
    }
}

/**
 * Pause for the specified time in milliseconds
 * @param ms how long to pause for, eg: 100, 200, 500, 1000, 2000
 */
function pause(ms: number): void {
    basic.pause(ms);
}

/**
 * Repeats the code forever in the background. On each iteration, allows other codes to run.
 * @param body code to execute
 */
function forever(a: () => void): void {
    basic.forever(a);
}
```
Notice the `export` keyword in front of the `showNumber`. This is what allows code outside the namespace to be called by prefixing the function name with the name of the namespace. You can see this in the declarations to `pause` and `forever`, which call `basic.pause` and `basic.forever`, respectively. Incidentally, this is why you can use `basic.forever` and `forever`, as well as `basic.pause` and `pause`, to get the same results.

#### 2. Apply
[[toc](#table-of-contents)]

1. Encapsulate your screensaver code in a namespace `screensaver` so that the only code that is outside is the main program loop, which calls functions exported by the namespace. In particular:
   1. The function `coding()` should be exported.  
   2. The function `rain()` should be exported.  
   3. The function `freqBars()` should be exported.  
   4. The function `bouncing_marbles()` should be exported.  
   5. Any global data necessary for the screensaver or working functions should be _encapsulated in the namespace_.  
   6. The class `Raindrop` should _not_ be exported.  
   7. The class `Marble` should _not_ be exported.  
   8. Any global data and code necessary for the main loop should remain outside of the namespace (e.g. the type `enum Mode`, the variables of type `Gesture` and `Gesture[]`, etc.).  
2. **[Optional challenge, max 10 extra step points]** Write a class to represent _unsigned_ binary integers as strings (e.g. `00011..` is 3<sub>10</sub>), called `UnsignedBinary`. Specifically:
   1. The strings contain two dots at the end as a subscript indicating the number is in binary.  
   2. The binary strings are at most 16 bits long (not counting the subscript).  
   3. The constructor takes a string `constructor(bin_str : string, carry : boolean)` and:  
      1. Rejects any characters that are not `0` or `1`. _Read the section on [exceptions](#exceptions)._  
      2. Calculates and stores the numerical value of the string. _Use **sum of powers**._ 
      3. Adds any leading zeros needed to complete the bit length to 16.  
      4. Stores the copy of the string with the suffix appended.  
      5. Stores the Boolean argument `carry`. (See the next points.)  
   4. The function `carry() : boolean` is implemented with the following specifications:
      1. It reports the value of an internal field which is `true` when the integer has overflowed and `false` otherwise. 
      2. An integer may overflow if it is a result of addition which has overflowed (e.g. `0001..` + `1111..` will overflow, so the result is `0000` and the carry is `true`; on the other hand, `0011..` + `0001` will not overflow so the result is `0111` and the carry is `false`).  
   5. The function `add(bi : BinaryInteger) : BinaryInteger` is implemented with the following specifications:
      1. It is called on a `BinaryInteger`, takes a second `BinaryInteger` as argument, and returns a `BinaryInteger`.  
      2. The returned object is a 16-bit result, with carry (if it overflows). 
      3. [Addition in binary](https://www.khanacademy.org/math/algebra-home/alg-intro-to-algebra/algebra-alternate-number-bases/v/binary-addition) works as follows:  
         1. 0<sub>2</sub> + 0<sub>2</sub> = 0<sub>2</sub>.   
         2. 0<sub>2</sub> + 1<sub>2</sub> = 1<sub>2</sub>.   
         3. 01<sub>2</sub> + 01<sub>2</sub> = 10<sub>2</sub>. _Note: Bit width grows by one._   
         4. 10<sub>2</sub> + 01<sub>2</sub> = 11<sub>2</sub>.   
         5. 011<sub>2</sub> + 001<sub>2</sub> = 100<sub>2</sub>. _Note: Bit width grows by one._   
   6. The function `show() : void` is implemented with the following specifications:
      1. It scrolls the binary string without the suffix.  
      2. Then, scrolls the suffix as two dots. Implement it with the animation feature of the micro:bit. Study the following example to find out how to do it:
         ```javascript
         // Example 6.1.4
         
         basic.showAnimation(
         `0 0 0 0 0 0 0 0 0 0 0 0 1 0 0 0 1 1 1 0 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 0 1 1 1 0 0 0 1 0 0 0 0 0
          0 0 0 0 0 0 0 1 0 0 0 1 1 1 0 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 0 1 1 1 0 0 0 1 0 0 0 0 0 0 0 0 0 0
          0 0 1 0 0 0 1 1 1 0 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 0 1 1 1 0 0 0 1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0
          0 0 0 0 0 0 0 1 0 0 0 1 1 1 0 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 0 1 1 1 0 0 0 1 0 0 0 0 0 0 0 0 0 0
          0 0 0 0 0 0 0 0 0 0 0 0 1 0 0 0 1 1 1 0 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 0 1 1 1 0 0 0 1 0 0 0 0 0`)
         ```
         _Hint: Blocks of 5x5._  

#### 3. Present
[[toc](#table-of-contents)]

In the [programs](programs) directory:
1. Add your program from 6.2.1 with filename `microbit-program-6-2-1.js`.  
2. Add your program from 6.2.2 with filename `microbit-program-6-2-2.js`.  

In the [Lab Notebook](README.md):
1. Link to the program from 6.2.1.  
2. Link to a demo video showing the execution of the program from 6.2.1.  
3. Link to the program from 6.2.2.  
4. Link to a demo video showing the execution of the program from 6.2.2.  


### 7. Functions revisited  
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

##### Input-output contract  
The input-output contract of a function consists of the particular transformation of the input data (that is, the arguments) into the output data (that is, the return value). Even functions which do not return anything have an input-output contract, as they may be modifying internal data structures (e.g. class methods). Functions which do not take any arguments are often called _routines_.

Formally, the input-output contract includes the number and types of function parameters as well as the type of the return value, if any. The shortest expression of the input-output contract is the function _signature_.

The input-output contract of a function is an _invariant_, meaning that it is strictly fixed, and _does not change_ even when the specific implementation of the function changes. A function is thus an _encapsulation of an input-output contract_.

Functions can also perform operations that are not strictly part of the input-output contract and are not otherwise explicitly stated. Such operations are therefore called _side effects_. Side effects relate to a very important feature of functional input-output contracts, namely that the latter guarantee that the program state is _consistent_ before and after the execution of a function (though it may briefly become inconsistent in the middle of its execution); side effects are potential holes in the input-output contract, and may introduce subtle inconsistencies that are hard to trace and fix.  

##### Pass by value vs pass by reference  

An important aspect of functions is how the arguments are passed to the function through the function call. There are two ways:
1. _Pass by value_ means that the value of the argument is a copy of the original variable (unless it is a _literal_ in which case it is not a copy of anything, for example the number `3`). In this case, the function can use the value but cannot modify the original variable. This method works for all _primitive_ data types.  
```javascript
// Example 7.1.1

let a : number = 2

function double(n : number) : void {
    n = 2*n
}

basic.showNumber(a)
double(a)
basic.showNumber(a)  // a retains its value

function double2(n : number) : number {
    return 2*n
}

a = double2(a)
basic.showNumber(a)  // only now does a change, because we assigned a new value to it
```  
<img src="images/pass-by-value.png" alt="Pass by value" width="600" />  

2. _Pass by reference_ means that the value of the argument is actually the _memory address_ (aka _pointer_, esp. in C/C++) of the data structure or object that is being passed. In this case, the function modifies the original variable. This method works for all arrays and class instances.  
```javascript
// Example 7.1.2

let arr : number[] = [1, 2, 3]

function double(a : number[]) : void {
    for (let i = 0; i < arr.length; i ++)
        a[i] *= 2
    }

double(arr)

arr.forEach(function (value: number, index: number) {
    basic.showNumber(value)                              // the elements of the array are now doubled!
})
   ```  
<img src="images/pass-by-reference.png" alt="Pass by reference" width="600" />  
   
##### Function naming

The argument over function naming has been long and intense, so we are only going to mention two very popular styles that we have already used:
1. _Camel case_ capitalizes every word in the function name except the first one (e.g. `frequencyBars` and `freqBars`).  
2. _Snake case_ is all lower-case and divides the words in the function name with underscores (e.g. `bouncing_marbles`).   

It doesn't matter that much which one you use, as long as you are consistent. This said, we have been inconsistent in naming our screensavers, but only so that we can explicitly talk about these two function naming conventions.  

##### Recursive functions  

Functions can call themselves. Since the signature of the function is already known by the time any call can be made from inside the function block, that call can be to the same function. This is called [_recursion_](https://en.wikipedia.org/wiki/Recursion_(computer_science)). Let's see an example:
```javascript
// Example 7.1.3

function factorial(a : number) : number {
    if (a == 1) {
        return 1
    } else {
        return a * factorial(a - 1)
    }
}

basic.showNumber(factorial(5))
```
Notice the following main points:
1. The recursive call is always with a "smaller" argument (e.g. a number minus one, or a subarray of the original array). The recursive call is solving a _smaller problem_.    
2. There is always a _termination condition_, in our case when a equals 1. This is the _smallest possible problem_ and it terminates the recursive call chain. Forgetting a termination condition will most often result in what is called an _infinite loop_.  

We need to note that recursive functions, while they look very elegant, are very wasteful of space (that is, memory), as they keep calling themselves until they reach the termination condition. All these copies of the function fill up the [_call stack_](https://medium.com/@ryanfarney/breaking-down-the-call-stack-e68b5633fbad), a special memory region that keeps function data for all outstanding function calls.    


#### 2. Apply
[[toc](#table-of-contents)]

1. Write a function `BubbleSort(arr : number[]) : void` to _sort_ _in place_ a numeric array, using the [Bubble Sort](https://en.wikipedia.org/wiki/Bubble_sort) algorithm. Requirements and notes:
   1. The function should take an array of numbers and sort it _in place_, without creating a new array.  
   2. The array should be sorted in _ascending_ order (e.g. `[1, 5, 17, 80, ...]`.  
   3. The function should not return anything.  
   4. There are two versions of Bubble Sort: [iterative and recursive](https://www.techiedelight.com/bubble-sort-iterative-recursive/). This function should implement an _iterative_ Bubble Sort. _Hint: The C syntax is closest to TypeScript, so you should read the C versions of the solutions in the referenced resource, for guidance._  
   5. An _algorithm_ is an exact series of precise (computational) steps that solves a certain problem or a class of problems. _Sorting_ is one of the most often performed computational activity in the modern world and there are many [sorting algorithms](https://en.wikipedia.org/wiki/Sorting_algorithm). Bubble Sort is not an efficient algorithm and is therefore not used in practice. However, it is great for developing intuition about the problem to be solved. For further intuition, watch this short [YouTube video](https://www.youtube.com/watch?v=kPRA0W1kECg&t=130s).
   6. Write a short program that uses your function. It should:
      1. Scroll "Input:" and then the input array. The input array should be `[14, 19, 3, 2, 0, 56, 12, 7, 90, 1, 11]`.     
      2. When done, it should scroll "Sorted:" and then the sorted array.  
2. **[Note: The solution to this problem will count for 2 extra step points]** Implement a _recursive_ `BubbleSort(arr : number[]) : void`. Run the same program you wrote to demo the iterative solution.  
3. **[Optional challenge, max 10 extra step points]** Design and implement the game [Tower of Hanoi](https://en.wikipedia.org/wiki/Tower_of_Hanoi) and a recursive solution. [Practice](https://www.mathsisfun.com/games/towerofhanoi.html) to get an intuition. Requirements and notes:
   1. Your program should be able to take a 3-peg game, with a tower of up to 7 stories at the leftmost peg, and solve it by moving the tower to the rightmost peg.  
   2. Your program should use **recursion** to solve the game.  
   3. Your program should have two display modes:  
      1. One mode will only scroll the start and end configurations (e.g. for a 3-story tower, `321|0|0` and `0|0|321`).  
      2. One that shows the start, all intermediate, and end configurations (e.g. for a 2-story tower, `21|0|0`, `2|1|0`, `0|1|2`,  and `0|0|21`).  
   4. Your implementation - classes, functions, etc. - is up to you. _Try to use what you have learned so far._  

#### 3. Present
[[toc](#table-of-contents)]
   
In the [programs](programs) directory:
1. Add your program from 7.2.1 with filename `microbit-program-7-2-1.js`.  
2. Add your program from 7.2.2 with filename `microbit-program-7-2-2.js`.  
3. Add your program from 7.2.3 with filename `microbit-program-7-2-3.js`.  

In the [Lab Notebook](README.md):
1. Link to the program from 7.2.1.  
2. Link to a demo video showing the execution of the program from 7.2.1.  
3. Link to the program from 7.2.2.  
4. Link to a demo video showing the execution of the program from 7.2.2.  
5. Link to the program from 7.2.3.  
6. Link to a demo video showing the execution of the program from 7.2.3.  
   
   
### 8. Classes revisited
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

##### Classes are type definitions

So, what are classes after all? We mentioned that they are _templates_ for _objects_, but that is too abstract and not well grounded. Most importantly, classes are _data type definitions_. A class defines a data type by defining its relationships with the rest of the data types in the computing environment (e.g. the `BrightPoint` class is essentially an array of three integers, `x`, `y`, and `b`) and constrains the operations that can be performed on objects of this type. Specifically, a class does that in the following ways:
1. Defines the **data** that an object of this type contains.  
2. Defines the **methods** that can be applied (that is, called on) objects of this type.   
3. If necessary, rejects **anomalous usage** (e.g. division by zero) with the help of an important language feature called [_exception handling_](https://basarat.gitbook.io/typescript/type-system/exceptions). 

##### Exceptions

_Exceptions_ are a mechanism for preventing disallowed usage of a data type and/or program because if such usage were to be allowed, the program state would become irrecoverably _inconsistent_. For example, knowing that division by zero is not mathematically defined, how can we rely on a program that has tried to divide by zero? Exceptions prevent this and similar anomalous behavior from ever happening and provide a recovery mechanism. Here is a canonical example **(note: does not work in makecode)**:
```javascript
// Example 8.1.1

class Fraction {
    num : number
    denom : number

    constructor(num : number, denom : number) {
        if (denom == 0) throw new Error("Denominator cannot be zero!")

        this.num = num
        this.denom = denom
    }

    show() {
        basic.showString(this.num.toString() + '/'+this.denom.toString())
    }
}

let f : Fraction = new Fraction(1, 2)
f.show()                                    // <-- this shows fine


try {
    let g : Fraction = new Fraction(5, 0)   // <-- this will "throw" the ValueError exception
    g.show()
} catch (e) {                               // <-- this is the exception handling machanism which can prevent the program being terminated
    basic.showString("Error: " + e.toString())
}
```
Notice the different parts:
1. The `throw` keyword is used to generate an exception, which is essentially a new `Error` object.  
2. The `try...catch` statement is used to enclose code that might thrown an exception, as the line trying to declare a `Fraction` object with a zero denominator.  
3. If the enclosed code does not throw an exception, the `g.show()` executes and the program continues after the `catch` block.  
4. If the enclosed code does throw an exception, it is "caught", processed (here, just printing its message), and then the program continues after the `catch` block.  

Unfortunately, the writers of MakeCode, though they [support exceptions](https://makecode.com/language), they have not exposed the `Error` class. And, despite the `try...catch` clause being accepted syntactically by the editor, it does not work as expected. However, the following code **does** work:
```javascript
// Example 8.1.2

class Fraction {
    num : number
    denom : number

    constructor(num : number, denom : number) {
        if (denom == 0) throw _py.VALUE_ERROR

        this.num = num
        this.denom = denom
    }

    show() {
        basic.showString(this.num.toString() + '/'+this.denom.toString())
    }
}

let f : Fraction = new Fraction(1, 2)
f.show()                                 // <-- this scrolls fine

let g : Fraction = new Fraction(5, 0)    // <-- the thrown exception terminates the program with a sad face 
g.show()                                 // <-- never reached
```
So, `throw` works to give you minimal functionality to reject unsupported input in the constructor. _(Incidentally, the debate over whether a constructor should throw exceptions is also a very heated one!)_


##### Objects are dictionaries

Another way to look at classes is to focus on the objects themselves and realize that they are _dictionaries_. Dictionaries in computing are data structures which match _keys_ with _values_. They are also called _maps_ or _hash tables_, but they are just collections of data pairs. The value can be anything, literally anything, including the same value throughout the dictionary. However, the keys have to be _unique_. There cannot be two different key-value pairs with the same key.

The keys of the objects are their field names (e.g. the `x`, `y`, and `b` of `BrightPoint` objects) and the values are their specific values, which are different for every object. This is the essence of objects - their independent _lifecycle_ - and correspondingly a very valid perspective on what classes are, as object templates. In fact, in JavaScript, this is the dominating perspective!

If you want to read the implementation details of the JavaScript-like language that we use in MakeCode, called Static TypeScript (STS), read their [paper](https://www.microsoft.com/en-us/research/publication/static-typescript/). It's a fascinating read, once you get used to the terminology, and provides an enticing peek into the software stack of the micro:bit.  


##### Getters and setters

In the line of the objects-as-dictionaries perspective on classes that we just discussed, we should mention a very common pattern for class methods, namely the so called [_getters and setters_](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance#Getters_and_Setters), (aka `get` and `set` accessors). These are methods with specific syntax that are just there to allow us to get and set the values in the "object dictionary". Here's an example:
```javascript
// Example 8.1.3

class Point {
    private _x : number
    private _y : number

    constructor(x : number, y : number) {
        this._x = x
        this._y = y
    }

    get x() {
        return this._x
    }

    set x(new_x : number) {
        this._x = new_x
    }

    get y() {
        return this._y
    }

    set y(new_y : number) {
        this._y = new_y
    }
}

let p0 : Point = new Point(1, 2)

basic.showNumber(p0.x)            // <-- call the getter of `_x`
basic.pause(100)
p0.x = 5                          // <-- call the setter of `_x`
basic.showNumber(p0.x)
```
Notice the following:
1. The `get` and `set` keywords.  
2. The underscore in `_x` and `_y` to avoid duplicate names with the getters and setters of `x` and `y`.
3. The `private` keyword in front of `_x` and `_y`, which disallows calls like `p0._x` (that is, direct access to the object fields). _Hiding_ the implementation of the functionality encapsulated in a class is the reason for the popularity of getters and setters in the first place. _The detailed considerations belong to the theory and history of object-oriented programming._      


#### 2. Apply
[[toc](#table-of-contents)]

1. In a namespece `Complex`:
   1. Write a class to represent [_complex numbers_](https://www.mathsisfun.com/numbers/complex-numbers.html), called `ComplexNumber`.  
   2. Implement the function `Complex.add(a : ComplexNumber, b : ComplexNumber) : ComplexNumber`.   
   3. Implement the function `Complex.conjugate(a : ComplexNumber) : ComplexNumber`.   
   4. Implement the function `Complex.multiply(a : ComplexNumber, b : ComplexNumber) : ComplexNumber`.   
   5. Implement the function `Complex.showComplex(c : ComplexNumber) : void` to scroll a complex number as a string (e.g. `"-14-i31"`, `i`, `-i6`, `4+i7`, etc.).  
2. Using the `ComplexNumber` and the `Complex` methods, define the numbers `6+i7` and `-8-i5`, and:
   1. Add them. The program should scroll the first number, then show `+` for 1500 ms, then scroll the second number, then show `=` for 1500 ms, and finally scroll the result. _Note that you cannot use `showString` for the plus. You will have to define your own icon `Plus`._  
   2. Find their conjugates. For each number, the program should scroll the number, then show `C` for 1500 ms, and finally scroll the result. _See the previous note._   
   3. Multiply them. The program should scroll the first number, then show a custom icon `Mult` (a X centered at (2, 2) and spanning the 3x3 square with origin at (1, 1)) for 1500 ms, then scroll the second number, then show `=` for 1500 ms, and finally scroll the result.  
3. **[Optional challenge, max 10 extra step points]** In the namespace `Complex`:
   1. Write a class to represent _fractions_, called `Fraction`. Fractions should show in their _reduced form_. If a `Fraction` object is defined in _irreduced form_, it should be reduced internally in the constructor. 
   2. Implement the function `Complex.showFraction(f : ComplexNumber) : void` to scroll a reduced fraction as a string (e.g. `"15/16"`, `7`, `13/14`, `9/5`, etc.).  
   3. Modify your `ComplexNumber` class to work with fractions instead of [_continuous real and imaginary coefficients_](https://proofwiki.org/wiki/Real_and_Imaginary_Part_Projections_are_Continuous). If the _real_ or _imaginary_ part of the a complex is an irreducible fraction, show the number with fractional (not continous real) _coefficients_.  
   4. Modify your `showComplex` function to show complex numbers with integers or fractional coefficients (e.g. `12/13+i4/7`, `-14-i31`, `9/5-i7`, etc.).  
   5. Divide `6+i7` by `-8-i5`. The program should scroll the first number, then show a custom icon `Div` (a / centered at (2, 2) and spanning the 3x3 square with origin at (1, 1)) for 500 ms, then scroll the second number, then show `=` for 500 ms, and finally scroll the result. _Note the result has to be in the canonical form A + iB, where A and B are either integers or fractions._    

#### 3. Present
[[toc](#table-of-contents)]
   
In the [programs](programs) directory:
1. Add your program from 8.2.2 with filename `microbit-program-8-2-2.js`.  
2. Add your program from 8.2.3 with filename `microbit-program-8-2-3.js`.  

In the [Lab Notebook](README.md):
1. Link to the program from 8.2.2.  
2. Link to a demo video showing the execution of the program from 8.2.2.  
3. Link to the program from 8.2.3.  
4. Link to a demo video showing the execution of the program from 8.2.3.  

### 9. Code reading
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

##### game.ts

Being able to read programming code written by others is almost as important a skill as being able to write it yourself. This skill is called upon much more frequently than a novice programmer might expect. Large programming projects are highly collaborative undertakings and reading each other's code is one of the main activities of the project members.

Having the micro:bit as our model computer and MakeCode as our programming environment and editor, we will take [`game.ts`](https://github.com/microsoft/pxt-microbit/blob/master/libs/core/game.ts), one of the _library_ files of the Microsoft PXT project, the foundation for MakeCode's support for the micro:bit, as our object of exercise in code reading. This library defines the `game` namespace, which we have used when we used the `game.LedSprite` class in some programming tasks.

A library is a self-contained collection of programming artifacts, in particular _type definitions_, _functions_, and _classes_, generally of a common theme. A library has no _main program_, but instead is used as an already prepared resource in writing a main program. A libary exports (some of) its programming artifacts to be used in writing other libraries or standalone programs.

The way MakeCode exposes libraries like [`game.ts`](https://github.com/microsoft/pxt-microbit/blob/master/libs/core/game.ts) is by compiling all of them together in the TypeScript _runtime_. The TS runtime is a top layer of the micro:bit _software stack_. (If we instead wrote our programs in MicroPython, its runtime would be the top layer of the stack.) A runtime is a set of programs which translates human-readable programs in a particular programming language into one lower layer of the software stack, the code in which is usually much similar to the physical operation of the physical device that will run the programs. For example, in the case of the micro:bit, the layer below the TS runtime is the [micro:bit runtime](https://tech.microbit.org/software/runtime-mbed/), which abstracts the low-level functionality of the physical device into generic-device programming artifacts. For this reason, it is also called a _device abstraction layer_ (DAL). See the diagram showing the software stack of the micro:bit when we use TS to program it: 

<img src="images/microbit-software-stack-01.png" alt="micro:bit software stack sketch" width="600" />

The TS runtime is used in the in-browser MakeCode editor and simulator, but is also inserted as part of the generated HEX file that is written to the micro:bit device. You may notice that the comments above the programming artifacts included in the [`game.ts`](https://github.com/microsoft/pxt-microbit/blob/master/libs/core/game.ts) library are highly structured and look like code themselves. These are called _annotations_ and are used for various purposes, including presentation, linking in a programming environment, documentation generation, etc. The MakeCode editor, which presents artifacts in both Blocks and TS, these annotations are an inseparable part of creating such a straightforward programming environment. 

When we said that the [`game.ts`](https://github.com/microsoft/pxt-microbit/blob/master/libs/core/game.ts) library is self-contained, this was meant to indicate that it defines the game package in its entirety. That is, there aren't two different libraries that have to be used in tandem to create a game for the micro:bit. This said, the library itself depends on artifacts defined in other libraries.

##### enum types

The [`game.ts`](https://github.com/microsoft/pxt-microbit/blob/master/libs/core/game.ts) library defines two enumerated (that is, `enum`) types:
1. `Direction` is used to simplify the manipulation of the `LedSprite` motion.    
2. `LedSpriteProperty` exposes 5 different "properties" of the `LedSprite`, creating a common mechanism for their retrieval and manipulation (aka getting and setting), as shown in the next example:
```javascript
// Example 9.1.1

let sprite : game.LedSprite = game.createSprite(4, 0)

let b : number = sprite.get(LedSpriteProperty.Brightness)  

sprite.set(LedSpriteProperty.Brightness, b/2)
```

An enumerated type is a programming artifact which has attributes of arrays and classes at the same time, though it is neither. It is multi-valued like an array, and it defines a type like a class. It is an ordered collection of names, which in themselves correspond to integers. All names can have their numeric value assigned explicitly, or they take the incremented value of the previous name in the collection:
```javascript
// Example 9.1.2

enum CommodityValue { Iron = 100, Silver = 250, Gold = 350 }
enum Bird { Sparrow = 0, Hawk, Eagle, Finch, Osprey, Canary }  // e.g. Bird.Finch equals 3
```

Notice that the two enumerated types are defined _outside_ the namespace `game`. Thus, they can be used freely for purposes other than the ones which define a game environment. It is conventional to put types in the top-level scope of a program (or, in this case, library).

##### Namespace `game`

A namespace is a named scope (aka block):
```javascript
// Example 9.1.3

namespace screensaver { }
```
It is just a way to enclose a set of tightly related programming artifacts together. Those of the artifacts that are expected to be called from outside the scope are _exported_ via the keyword `export` put in front of the artifact signature. The `game` namespace exports game-related functions (e.g. `createSprite`) and the class `LedSprite`. As we have seen, this means we have to use the namespace name as a _prefix_ to the function and class names:
```javascript
// Example 9.1.4

let s : game.LedSprite = game.createSprite(2, 1)
```

The scope that a namespace provides is ideal for defining namespace-global variables for the specific purpose of the namespace (in our case, a micro:bit game) without contaminating the top-level program scope with them. The following example lists all the variables used in a game, which are nonetheless not directly visible to the programmer using the `game` package in MakeCode:
```javascript
// Example 9.1.4

namespace game {
    let _score: number = 0;
    let _life: number = 3;
    let _startTime: number = 0;
    let _endTime: number = 0;
    let _isGameOver: boolean = false;
    let _countdownPause: number = 0;
    let _level: number = 1;
    let _gameId: number = 0;
    let _img: Image;
    let _sprites: LedSprite[];
    let _paused: boolean = false;
    let _backgroundAnimation = false; // indicates if an auxiliary animation (and fiber) is already running
    
    // rest of the namespace
}
```
Reading through the namespace code, we see that these are the variables used internally by the functions in the namespace. Notice that the names all start with an _underscore_ (e.g. `_score`, _gameId_, etc.). This is a convention in programming for _internal_ variables that are not exposed and/or exported.

##### Exported functions

The functions declared in the `game` have to do with game-related functionality (e.g. `addScore`, `startCountdown`, `gameOver`, etc.). Most of them are exported and are meant to be used together. Most of the function names are self-explanatory, but, if in doubt, read the [reference](https://makecode.microbit.org/reference/game) for `game`.

Not all of the artifacts declared in the namespace need be exported. For example, the functions `checkStart`, `unplugEvents`, `init`, and `plot` are not exported, but are only used internally by exported functions.

##### Class `LedSprite`

We have already used the class `game.LedSprite`, for example, in `HaloSprite` where we _extended_ the base `game.LedSprite` class to add a halo around a bouncing sprite. One implementation of the `Raindrop` class can also use `game.LedSprite` as a _base class_. One obstacle for using it for all the screensavers is that every `game.LedSprite` is managed by the machinery of the `game` namespace, which has its own constraints and proper intended uses. For example, to remove a `game.Sprite` completely, one needs to explicitly call `delete()` on a sprite. Also, `game.LedSprite` objects do not accept out-of-bound coordinate values.

`game.LedSprite` is built on top of the much simpler functionality of turning LEDs on and off, and varying their brightness. For some of our screensavers, using `game.LedSprite` may make the implementation unnecessarily burdensome, because, like every data type defined by a class, there is a specific intended manner of manipulating objects of the type. For example, creating a new class `Raindrop` without extending `game.LedSprite` results in a much cleaner and shorter implementation.


#### 2. Apply
[[toc](#table-of-contents)]

1. Organize your `screensaver` namespace like the [`game.ts` library](https://github.com/microsoft/pxt-microbit/blob/master/libs/core/game.ts). Write the _main program_ at the very bottom, using the exported functions. _Do you have types outside the namespace? Do you need to export any classes?_   
2. For each global variable, function, and class method in the namespace `screensaver`, write a descriptive comment, on the side of the variables and on top for the functions/methods. Remember the _last repository commit_ that you made completing these tasks.    

#### 3. Present
[[toc](#table-of-contents)]

In the [programs](programs) directory:
1. Add your program from 9.2.1 with filename `microbit-program-9-2-1.js`.  
2. Add your program from 9.2.2 with filename `microbit-program-9-2-2.js`.  

In the [Lab Notebook](README.md):
1. Answer the questions in 9.2.1.  
2. Link to the program from 9.2.1.  
3. Link to a demo video showing the execution of the program from 9.2.1. This is needed as a verification that you haven't broken your code.  
4. Link to the program from 9.2.2.  
5. Link to a demo video showing the execution of the program from 9.2.2. This is needed as a verification that you haven't broken your code.  

   
### 10. Iterative development with Github  
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

##### Git command line

Github is built around the _version-control system_ [Git](https://git-scm.com/) (aka _source-control management_ system). The term "source" is used for the raw human-readable form of a program, to be contrasted against the machine-executable form of the program. Nowadays, no programming or engineering project is undertaken without keeping a dynamic record of all the changes made. As a large project does not happen overnight, this record is indispensable. It is the central component of modern engineering workflows, supporting a large range of team organizations, company policies, development use cases, and release schedules.  

One of the first large _open-source_ projects, and still one of the most popular, is the [Linux kernel](https://en.wikipedia.org/wiki/Linux_kernel), which is the basis for all Linux-based _operating systems_. Git was [developed](https://git-scm.com/book/en/v2/Getting-Started-A-Short-History-of-Git) to coordinate its highly-distributed multi-person development. Just take a look at the number of commits to Linus Torvalds' [Linux kernel repository on Github](https://github.com/torvalds/linux) to get an idea of the scope of the project and the complexity of its maintenance.

We are already working with Git. You are reading a Markdown file in a _private_ Github repostory which is owned by the course staff and was created specifically for you. You have been added as an _outside collaborator_ and given full member access to the repository. You and the course staff can create files, modify files, and make comments.

##### Git remote and local

Working directly with the Github website, we are using Git only _indirectly_, because all Git operations are handled for us by Github. To learn Git, we need to take our code out of Github and look at the underlying Git operations performed on it in a _local_ _clone_ of the repository.

This step asks you to install the _command-line_ [Git client](https://git-scm.com/), a program which can work with _remote_ servers where Git repositories are maintained. Github is the largest such server. 

Git was meant to be a distributed source control system so it was designed with the notion of _remote_ and _local_ repositories. In our case, the remote repositories are on Github, and the local are copies of the remote ones on our own computers. There are three scenarios of remote-local work we will cover:
1. **Scenario 1: Github only**. It is explained and shown in this [demo video](https://msudenver.yuja.com/V/Video?v=1991009&node=7634464&a=961358564&autoplay=1).   
2. **Scenario 2: Github and local**. It is explained and shown in this [demo video](https://msudenver.yuja.com/V/Video?v=1991697&node=7636328&a=1013082438&autoplay=1).    

<img src="images/git-add-commit-push-pull-checkout.jpeg" alt="Git basic commands" width="600" />  

[[Image credit](https://dev.to/mollynem/git-github--workflow-fundamentals-5496)]

3. **Scenario 3: Local to Github**. It is explained and shown in this [demo video](https://msudenver.yuja.com/V/Video?v=1992746&node=7638785&a=1457131414&autoplay=1).   

##### Git commands

Follow a quick review of the most fundamental Git commands, with links to the documentation:
1. [`git init`](https://git-scm.com/docs/git-init): Creates an empty local Git repsitory. Usually the first command when starting from local.    
2. [`git clone`](https://git-scm.com/docs/git-clone): Clones a repository into a new directory. This is what we use to make a local copy of a repository already existing on Github.     
3. [`git remote`](https://git-scm.com/docs/git-remote): Manage a set of tracked repositories. In particular, can point a local repository to its remote counterpart. It has many options.    
4. [`git status`](https://git-scm.com/docs/git-status): Reports the status of the working tree. In particular, reports modifications of tracked files and newly created untracked files.  
5. [`git add`](https://git-scm.com/docs/git-add): Add file(s) to tracking _index_. In other words, this includes a file(s) to version control.     
6. [`git commit`](https://git-scm.com/docs/git-commit): Record changes to a repository. It requires a commit message (with option `-m`), which should be a short informative summary of what changed since last commit.     
7. [`git pull`](https://git-scm.com/docs/git-pull): Fetch and sync with another repository, usually a remote. Used to sync a local repository with its Github remote if the latter changed.    
8. [`git push`](https://git-scm.com/docs/git-push): Update remote repository. Local commits need to be pushed to be refleced in the remote repository (e.g. on Github).    
9. [`git mv`](https://git-scm.com/docs/git-mv): Move or rename a file/directory. Updates the index!  
10. [`git rm`](https://git-scm.com/docs/git-mv): Remove a file/directory. Updates the index!  

##### Git branch and merge

In the image in [Git remote and local](#git-remote-and-local) section image, we saw the command `checkout` but we didn't explain it. One of the most important features of Git is that it allows a team to isolate the development of new features from the main project until they are sufficiently mature. This is achieved by _branching_ off the main project (aka master), which can be thought as the _trunk_. Branching (aka **Fork** in Github), is essentially a copy of the repository under a new name, which however is still tracked in parallel with the trunk. At some point in the future, the branch developers may request that their code is _merged_ into the trunk. Merge is done when the branch code is sufficiently mature and may require several iterations to be brought into consistence with the trunk, which may also have changed and/or been merged with other branches. This is illustrated in the following simple diagram:

<img src="images/git-branch-merge.png" alt="Simple branch and merge diagram" width="600" />

[[Image credit](https://www.nobledesktop.com/learn/git/git-branches)]

The most relevant Git commands which support branching and merging are:
1. [`git branch`](https://git-scm.com/docs/git-branch): Manipulate branches.    
2. [`git checkout`](https://git-scm.com/docs/git-checkout): Switch branches. Updates the working tree.    
3. [`git switch`](https://git-scm.com/docs/git-switch): Switch branches.    
4. [`git merge`](https://git-scm.com/docs/git-merge): Join two or more development histories together.    
5. [`git tag`](https://git-scm.com/docs/git-tag): Manipulate tags. Tags are names for particular points in the development history of a project branch. They are used to indicate that a major feature is completed, a significant rework has been completed, an early release is ready for testing, etc. See an example of a [Git tag](https://github.com/ivogeorg/ce-learning-progression-002-bouncing-sprites/releases/tag/v1.0) on a Github repository. Github creates code packages and some additional features around tags and calls this extended feature _Releases_. This is a common term in software development, and you have experienced it at least once when, for example, your computer or phone operating system updated to a new version.    
6. [`git log`](https://git-scm.com/docs/git-log): Shows commit logs. On Github, this is done by clicking on **Commits**.    

<img src="images/git-tag.png" alt="Master marked with version tags" width="600" />

[[Image credit](https://leanpub.com/git-flow/read)]

##### Github workflow

Github follows the main contours of the Git workflow, but adds various features on top, among them:
1. Defines organizations, teams, and projects, with all the necessary management and logistics around them.  
2. It adds various collaboration tools and workflow details that don't exist in raw Git.  
3. It adds _pull requests_, which is a feature related to team organization, in which only some team members (called _committers_) are allowed to commit to the trunk, while others can only request that their changes are pulled in by the committers.  
   - [Github Classroom](https://classroom.github.com/classrooms) currently piggy-backs on top of pull requests for the **Feedback** feature.  
4. It adds comments at many places in the workflow.  
5. It maintains the `README.md` convention.  
6. Defines releases.  

##### Incremental development

_Incremental development_ means a sequence of programming iterations which:
1. Make a small but sufficient (that is, incremental) addition to the current program, be it a new feature, a modification of its functionality or user interface, a bug fix, etc.  
2. Runs, tests, and _debugs_ the additions, until no more bugs can be identified. This should include testing older code, to ensure that the new additions have not introduced bugs into the old code. This is called _regression testing_.      
3. Commits the changes. If a significant new functionality has been accumulated, all the outstanding local commits are pushed to the remote repository.    

Watch the following recordings of two live coding sessions where incremental development was shown in the context of creating two new classes in JavaScript:
1. `class Complex` [video](https://msudenver.yuja.com/V/Video?v=1978529&node=7604592&a=1823805177&autoplay=1) and [source code](https://gist.github.com/ivogeorg/842c36004e50143b43c6affd0dfa7984).    
2. `class UnsignedBinary` [video](https://msudenver.yuja.com/V/Video?v=1978655&node=7604844&a=1873218802&autoplay=1) and [source code](https://gist.github.com/ivogeorg/ef5f46b8ca67cfa5cdf9c8cbd217c9ef).   

#### 2. Apply
[[toc](#table-of-contents)]

1. Clone your remote assignment repository to your local environment. In the local directory, create an initally empty documentation directory called `docs`, commit, and push to remote.  
2. Start a new local repository. Create a `.txt` and `.js` file in it. Add and commit. On github create a new empty repository called `remote-home-for-local`. Link the local with the remote and push the contents.    
3. Tag the last commit from 9.3.1 as `v0.8`. _Note: It should include your latest commits of the Lab Notebook._   
4. Tag the last commit from 9.3.1 as `v0.9`. _Note: It should include your latest commits of the Lab Notebook._   
5. Create a file `screensavers.js` from the `v0.9` program. Tag as `v1.0`.  

#### 3. Present
[[toc](#table-of-contents)]
   
In the [programs](programs) directory:
1. Add your program from 10.2.5 with filename `screensavers.js`.  

In the [Lab Notebook](README.md):
1. Link to the `docs` directory created in 10.2.1.  
2. Link to the repository created in 10.2.2.  
3. Link to the `v0.8` tag.  
4. Link to the `v0.9` tag.  
5. Link to the `v1.0` tag.  


### 11. Reactive system  
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

##### Software stack

As we have mentioned already, the software that runs (on) the micro:bit is not _monolithic_, but layered, with the layers forming a _stack_, which we call _software stack_. A stack is such a structure, data or physical, in which every element (layer) isolates completely the elements above and below it. In software engineering, that is, writing large system programs, such an organization follows the important designs principle of _uncoupling_ (keeping apart components which should be separate) and _abstraction_ (performing increasingly integrated operations at each higher layer).

The software stack of the micro:bit consists of 3 main layers (see the [diagram](#gamets) in an earlier step):
1. TypeScript [runtime](https://en.wikipedia.org/wiki/Runtime_system). This is the highest-abstraction layer and is responsible for translating the TS program into computational artifacts that can be handled by the micro:bit device, among those:    
   - arrays  
   - classes & objects, including:  
     - _virtual tables_ for _polymorphic methods_  
     - memory management  
   - functions  
   You can read about these and more in the [Static TypeScript paper](https://www.microsoft.com/en-us/research/uploads/prod/2019/09/static-typescript-draft2.pdf) which describes the implementation of the [subset of TypeScript implemented for the MakeCode environment](https://makecode.com/language) in detail.      
2. [micro:bit runtime](https://lancaster-university.github.io/microbit-docs/). This is the middle layer and is responsible for exposing various computational capabilities of the micro:bit to a programming language runtime for TypeScript, [MakeCode Python](https://support.microbit.org/support/solutions/articles/19000111744-makecode-python-and-micropython), or [MicroPython](https://microbit-micropython.readthedocs.io/en/v1.0.1/). Among the exposed capabilities are: 
   - scheduling  
   - device _drivers_ (small programs specifically focused on running a sensor, an actuator, or other device)      
   - the 5x5 LED matrix  
3. [Mbed](https://os.mbed.com/) _operating system_. This is the lowest level and is responsible for overall management of the computational resources of the micro:bit device, including:  
   - security foundations  
   - cloud management services  
   - drivers for sensors, I/O devices, and networking    
   - hardware abstraction layer (HAL) (the HAL is an instance of _uncoupling_ and _abstraction_, allowing the same general functionality to run on millions of different devices)  
   An important portion of the Mbed layer is the [Nordic Semiconductor Software Development Kit](https://www.nordicsemi.com/Software-and-tools/Software/nRF5-SDK), which is a collection of programs and development tools for the most important hardware component of the micro:bit, the _application processor_. More on the [hardware stack](https://tech.microbit.org/hardware/) of the micro:bit in a later learning progression.  

The [software](https://tech.microbit.org/software/) section of the [technical documentation](https://tech.microbit.org) of the micro:bit is a good source of detail on these stack components. A full study of the software stack is beyond the scope of this learning progression, but you can read a more in-depth description in this [blog post](https://mattwarren.org/2017/11/28/Exploring-the-BBC-microbit-Software-Stack/).

##### Fiber scheduling 

One of the most important functions of a runtime or an operating-system layer of the software stack is _scheduling_, the process of arranging various program components to execute in some order. Schedulable program components are called _threads_. While several threads can be part of the same program, they can be executed independently of each other. Look at the following screenshot of a macOS Activity Monitor window:

<img src="images/activity-monitor.png" alt="Programs, processes, and threads" width="800" />

Notice the following:
1. The first column is called **Processes** rather than programs. _Processes_ are activated executable programs. In contrast, unactivated _programs_ are just unopened files.  
2. The column **Threads** shows the number of threads being executed for each of the processes. There is no process that has only one thread!  

Threads are the units of scheduling. They have a lifecycle of several states, as shown in the following image (notice that _scheduling_ is an operation that changes the state of the thread):

<img src="images/thread-states.png" alt="Thread states" width="600" />

[[Image credit](https://medium.com/@dreamume/kernel-thread-states-9a8c877b3fc2)]

The micro:bit reference has a page that explains [how scheduling is performed for the micro:bit](https://makecode.microbit.org/device/reactive), along with examples of handling events. _It is the most important part of reading in this learning progression as it is the first one in which we treat the micro:bit as a computer rather than an entertaining toy._

The scheduling is done in the TS runtime layer, based on a computational capability provided by the micro:bit runtime (DAL) layer. The unit of scheduling provided by the dal is called a `Fiber`, as it is a _lightweight_ (meaning providing more limited functionality) thread. The TS runtime uses in its code computational artifacts provided in the DAL. The following links give a glimpse into the code of the two layers, invloved in fiber scheduling:
1. micro:bit runtime (DAL):
   1. [`MicroBitFiber.h`](https://github.com/lancaster-university/microbit-dal/blob/master/inc/core/MicroBitFiber.h) declares the scheduling machinery that is to be exposed.  
   2. [`MicroBitFiber.cpp`](https://github.com/lancaster-university/microbit-dal/blob/master/source/core/MicroBitFiber.cpp) is the source code of the implementation.  
2. TypeScript runtime:
   1. Fiber calls in the [pxt-common-packages](https://github.com/microsoft/pxt-common-packages/search?q=fiber+in%3Atext) libraries.  
   2. Fiber calls in the [pxt-microbit](https://github.com/microsoft/pxt-microbit/search?q=fiber+in%3Atext) libraries.      

All the issues of programming with multiple threads (aka _multithreading_) are beyond the scope of this learning progression, but it is important to know that they are the main units of scheduling and execution, and thus have to do with, among others:
1. Issues of program speed.
2. Issues of memory utilization.
3. Issues of thread safety. (Usually due to _non-deterministic_ splitting & rearrangement of code portions.)  

##### Events revisited 

The [Reactive system](https://makecode.microbit.org/device/reactive) reference page gave an example of how a button press is handled. The whole process involves not only the full software stack, but the _full stack_ of the micro:bit, which includes the hardware on top of which the software stack lays. (See the diagram in the [micro:bit software-stack blog post]((https://mattwarren.org/2017/11/28/Exploring-the-BBC-microbit-Software-Stack/)). The full account of the traversal of the full stack of the reaction to an external event (e.g. button pressed, a gesture made, a signal receieved over radio or a GPIO pin), from the detection of the signal which generates a processor interrupt to the way your program is informed of the event and reacts to it, is also beyond the scope of this learning progression. We will only revisit the top layer, namely the _registrant functions_.

Examples of registrant functions are `input.onButtonPressed()`, `input.onGuesture()`, and `pins.onPulsed()`, among others. These functions register _event handlers_ by providing functions to be executed for specific events. They take as arguments the event-handler functions that we write, as in:
```javascript
// Example 11.1.1

let turn : Direction = Direction.Right

input.onButtonPressed(  Button.A,   () => { turn = Direction.Left; }  )
```
Notice the following:
1. The registrant function is `input.onButtonPressed` and is registering an event-handler for the event of button A having been pressed (note, and _released_).  
2. The two arguments of the registrant function are the name of the button from the `enum` type `Button`, and the event-handler code wrapped in an anonymous function. _Note that `() => { }` is just a lazy shortcut for `function () { }` and widely used in JavaScript._  
3. The registrant function is _in the global scope_ (meaning the top level of the program), and not enclosed in a `forever`, a function, or a class. If you have read the [Reactive system](https://makecode.microbit.org/device/reactive), you will know that **you should never have event handling in a `forever` loop** or other nested scope. First, it doesn't make sense, because the event handling mechanism has an execution protocol which is _defined sufficiently_ by a free-standing registrant function, and over which you have _no further control_. Second, it makes your program extremely hard to read. Lastly, it creates false impressions in you that you have extra control over event handling.
4. The event handling code is _minimal_. The [Reactive system](https://makecode.microbit.org/device/reactive) reference page also shows that the even handler _preempts_ (meaning it inserts inself in front of) the current fiber which is running, making its execution timing unpredictable and possibly making the display dynamics less smooth.

##### `forever` vs `while`

The `basic.forever()` function is under special management of the TypeScript runtime, but the `while () {}` loop is just a basic language component and is handled without any translation through the TR and micro:bit layers of the software stack. This results in some notable differences in the program execution behavior of the same code, passed as an anonymous function argument to a `forever` function, on one hand, and wrapped in a simple `while` loop, on the other. The following table summarizes the differences:

feature | `forever` | `while`
-- | -- | --
condition | no | yes
`break` | no | yes
scheduling | yes | no
simulator fidelity | yes | no

This is one simple example of why knowledge of the layers of a software stack are important to a computer engineer. The practice tasks below are supposed to provide some direct experience with the particular handling of `forever` loops by the TS runtime.


#### 2. Apply
[[toc](#table-of-contents)]

1. Create 6 separate `forever` loops, each one containing `showNumber()` with a different one of the numbers n = 1, 3, 5, 7, 9, 11, 13. Describe the behavior. Can you see all the numbers clearly?  
2. Modify the previous program to show the either n or n + 1 toggled by pressing button A. Describe the behavior. How soon do the numbers switch after you press the button?  
3. Modify the previous program, adding a random `pause()` between 300 and 1200 ms after `showNumber()`. Describe the behavior. Can you see the numbers out of order?   

#### 3. Present
[[toc](#table-of-contents)]
   
In the [programs](programs) directory:
1. Add your program from 11.2.1 with filename `microbit-program-11-2-1.js`.  
2. Add your program from 11.2.2 with filename `microbit-program-11-2-2.js`.  
3. Add your program from 11.2.3 with filename `microbit-program-11-2-3.js`.  

In the [Lab Notebook](README.md):
1. Link to the program from 11.2.1 and describe its behavior.  
2. Link to a demo video showing the execution of the program from 11.2.1.  
3. Link to the program from 11.2.2 and describe its behavior.  
4. Link to a demo video showing the execution of the program from 11.2.2.  
5. Link to the program from 11.2.3 and describe its behavior.  
6. Link to a demo video showing the execution of the program from 11.2.3.  


### 12. Matrix dynamics  
[[toc](#table-of-contents)]

#### 1. Study
[[toc](#table-of-contents)]

##### Out-of-bound coordinates

The screensavers program is largely meant as a culminating programming experience, but a close second reason for it is to expose the programmer to some of the manifestations of the functioning of the software stack. The most readily observable telltales are in the LED matrix dynamics of complex randomized behavior demanded by the various screensavers.

One of the easiest discernable difference between two seemingly equivalent programming expressions is that the functions `led.plot()` and `led.unplot()` accept out-of-bound coordinates, while the constructor and other methods of the `game.LedSprite` class do not. The former are _low-level functionality_, directly connected to the physical turning on and off of the LEDs, while the latter is part of the `game` namespace, itself part of the pxt platform underlying the MakeCode environment and the TS runtime, which imposes extra constraints in order to focus on the _high-level functionality_ of a micro:bit game. Here, for example, are the lines of the `game.LedSprite` constructor, which enforces one of these constraints:
```javascript
// Example 12.1.1

namespace game {

    // namespace data and functions
    
    export class LedSprite {
        private _x: number;
        private _y: number;
        private _dir: number;
        private _brightness: number;
        private _blink: number;
        private _enabled: boolean;

        constructor(x: number, y: number) {
            this._x = Math.clamp(0, 4, x);             // <-- clamp to range [0, 4]
            this._y = Math.clamp(0, 4, y);             // <-- clamp to range [0, 4]
            this._dir = 90;
            this._brightness = 255;
            this._enabled = true;
            init();
            _sprites.push(this);
            plot();
        }
    }
}
```

##### Smooth graphics

The screensaver sub-programs look the best when the graphics are smooth. One of the ways to achieve that is to refrain from using the methods in the `basic` namespace, in particular the `show...()` and `plot...()` methods as well as the `pause()`, the former because they are slow, and the latter because it adds the uncertainty about when the fiber that was put to sleep will run again. The only guarantee that `pause()` gives is that the fiber will not restart _earlier_ than the time argument in ms. So, for smooth graphics, one should try to handle most of the lighting and timing of the screensaver, even if that means letting go of the comfort and ease of the functions exported by the `basic` namespace.

One `basic` function which is relatively safe to use is `basic.clearScreen()`, because it is fast and as basic as `led.plot()` and `led.unplot()`. In fact, it is much faster than a loop to `led.unplot()` all lit-up LEDs.

##### Speed and scheduling

Using `basic.clearScreen()` may result in behavior that is both unexpected and hard to debug at first. Look at the following example:
```javascript
// Example 12.1.2

while (true) {
    if (isHeart) {                                             
        basic.showIcon(IconNames.Heart)
    } else {
        basic.showIcon(IconNames.Butterfly)
    }
    basic.pause(100)
    basic.clearScreen()
    basic.pause(100)                             // THIS IS REQUIRED TO SEE THE ICON BLINK
}
```
Because `showIcon()` is slow but `clearScreen()` is fast, the will be no detectable interval between the call to `basic.clearScreen()` and the subsequent call to `basic.showIcon()` in the loop, requiring an extra `basic.pause()` to be inserted. This may or may not affect the smoothness of a screensaver, so it pays to be aware of it.

##### Mod-based timing

One method to smooth out graphics, especially when there are multiple independent objects moving in randomized trajectories to create the visual effect of the screensaver, is _mod-base timing_. This is a way to avoid using `pause()` but still be able to have minute control over the relative timing of the behavior of different objects. It most often applies to the `move()` method of a screensaver object class (e.g. `Raindrop`, `BouncingMarble`, etc.), though it may be applied also in other methods, as well as the main loop. The basic premise is to control the _responsiveness_ of the `move()` method, as shown in the following example:
```javascript
// Example 12.1.3

class Raindrop {
    x : number
    y : number
    z : number             // virtual 3rd dimension (aka depth, distance)
    counter : number       // helper variable to implement relative timing

    // constructor and methods
    
    move() : void {
        if (this.counter % this.z == 0) {
            
            // perform "motion"
            
            this.counter = 0        // <-- restart counter
        }
        this.counter ++             // <-- increment counter
    }
}

const NUM_RAINDROPS : number = 10
let rain : Raindrop[] = []
for (let i=0; i<NUM_RAINDROPS; i++) rain.push(new Raindrop(...))

forever(() => {
    for (let i=0; i<rain.length; i++) rain.move()      // <-- call move on all Raindrop objects
})
```
Notice that `move()`, while called on each object every time through the `forever` loop, will actually perform the motion **only periodically** with a period equal to the value of the 3rd dimension `z`.

The only drawback of using this timimg method for smoothness is that it might potentially:
1. Invlove a lot of manual tuning (e.g. the `BouncingMarble` trajectory), which is never good in programming and engineering in general.  
2. Exacerbate the timing mismatch between the MakeCode simulator and the actual micro:bit device.

##### Frame-based display

Very smooth graphics can be achieved with a complex screensaver by using _frame-based display_. Frames are the still images that compose a video. We usually don't see separate frames because they change at a [_frame rate_](https://www.techsmith.com/blog/frame-rate-beginners-guide/) sufficient to create the visual perception of uninterrupted motion.

The key to the implementation of a frame-based screensaver is that each position in the image (25 in all for the micro:bit) has to be modified, if necessary, _between_ the frames which are shown (e.g. `basic.plotLeds()` or a nested `for` loop of `led.plot()`). The following is a forward-looking example of one possible approach to the implementation of a frame-based implementation of the `slytherin` screensaver, which is the object of the practice tasks below:
```javascript
// Example 12.1.4

class Snake {
    private _body : number[][]       // [x, y] positions, _body[0] is head
    private startLen : number        // _body.length
    private _color : number          // brightness
    private alive : boolean          // not killed yet
    private step : number            // for turnDelay
    private dir : Heading            // current direction of motion
    private nest : Nest              // nest controls the snakes
    
    // constructor and methods
    
    slither() {
    
        // implementation of snake-like motion
        
    }
}

class Nest {
    occupancy : Snake[][][]
    snakes : Snake[]

    constructor() {
        this.occupancy = [
            [[], [], [], [], []],
            [[], [], [], [], []],
            [[], [], [], [], []],
            [[], [], [], [], []],
            [[], [], [], [], []],
        ]
        this.snakes = []
    }

    // other methods
    
    show_snakes() {
        for (let x=0; x<5; x++) {
            for (let y=0; y<5; y++) {
                led.unplot(x, y)
                let l : number = this.occupancy[x][y].length
                if (l > 0) {
                    // show heads at max brightness
                    let s : Snake = this.occupancy[x][y][l-1]
                    led.plotBrightness(x, y, s.is_head(x, y) ? s.color + 50 : s.color)
                }
            }
        }
    }
}
```
The 3-dimensional `occupancy` array holds arrays of `Snake` objects for each (x, y) position. One snake occupies more than one position, so belongs to more than one position array:
```
// Example 12.1.5

      0      1      2      3      4
  ------------------------------------
0 |      |   1  |      |      |      | 
  ------------------------------------
1 |      |   1  |  1   |      |      | 
  ------------------------------------
2 |      |   2  |  1,2 |      |      | 
  ------------------------------------
3 |      |   2  |      |      |      | 
  ------------------------------------
4 |      |   2  |   2  |      |      | 
  ------------------------------------
```
In this sketch of an occupancy array, there are 2 snakes, #1 and #1. Snake #1 occupies 4 positions and its body is `[[1, 0], [1, 1], [2, 1], [2, 2]]`, while snake #2 occupies 5 positions and its body is `[[2, 2], [1, 2], [1, 3], [1, 4], [2, 4]]`. The snakes move between calls to `show_snakes()` just like the `Raindrop.move` method was `this.hide(); this.y++; this.show()`, but this time all the snake motions that we want perform at the same time have to happen between the `frames`, represented by `show_snakes`. 

Note that this implementation is quite complex and is not necessary for getting the 1 point for this step.
 
##### Simulator fidelity revisited

The one-to-one correspondence between what we see for the same program in the MakeCode simulator and the micro:bit device, may depend on several factors:
1. Level of implementation of the particular behavior programmed in the simulator. (For example, last year there was limited simulation of the functions in the `pins` namespace, but the capabilities have increased markedly since. More on `pins` in a later progression.)  
2. The complexity of your code and the difference between the _execution path_ lengths for different branches and/or cases of the program. (For example, depending on the details of your implementation of the `bouncing_sprites` screensaver, the rate of motion along the trajectory of the marbles might depend on how many marbles are being released at the same time.)  
3. The _level_ of code that you use, namely TS-runtime supported or not (remember `forever` vs `while).
4. The efficiency of your code. As we have seen, there are often multiple ways to implement the same behavior, but some implementations can _scale_ with the size of the problem, while others cannot.   

These are all considerations that a programmer grows to consistently make from one project to another, and this learning progression was meant to give you a glimpse into them in preparation for your professional career as a computer engineer.

#### 2. Apply
[[toc](#table-of-contents)]

1. Implement the Slytherin screensaver into a function called `slytherin`. There are three tiers of implementation, where the **first tier is sufficient for full credit for this step**, and the others are **optional challenges**:
   1. **Tier 1** A single snake moves randomly around the screen (in all 8 directions, 4 straight and 4 diagonal), without stepping off the screen, without wrapping around at edges, and without stepping on itself. The head of the snake should be brighter than its body. The snake's starting length (including head) should be random in the range [3, 6]. If the snake gets stuck in a corner (meaning there is no position for it to go next by the above rules), it dies and is removed. ([Demo video](https://msudenver.yuja.com/Dashboard/Permalink?authCode=296215767&b=1908509&linkType=video).)    
   2. **Tier 2** [max 5 extra step points] Multiple snakes, with different colors and random overlap.  ([Demo video with 2 snakes](https://msudenver.yuja.com/Dashboard/Permalink?authCode=1371836612&b=1908523&linkType=video). [Demo video with 5 snakes](https://msudenver.yuja.com/Dashboard/Permalink?authCode=489117902&b=1908533&linkType=video).)  
   3. **Tier 3** [max 10 extra step points] Add the functionality of a _biter snake_, which bites and kills other snakes on contact (meaning its head is in a position where there are other snakes). There should be a 15% chance for a snake to be a biter. Upon being bitten, a snake disappears. A biter does not bite itself. For each snake bitten, the biter grows its tail by 1. The snakes are randomly repopulated so that a biter does not remain by itself.
2. Integrate into `screensavers.js` with a gesture of your own choosing, and tag with `v1.2`.  

#### 3. Present
[[toc](#table-of-contents)]
   
In the [programs](programs) directory:
1. Add your program from 12.2.1 with filename `microbit-program-12-2-1.js`.  
2. Add your program from 12.2.2 with filename `microbit-program-12-2-2.js`.  

In the [Lab Notebook](README.md):
1. Link to the program from 12.2.1.  
2. Link to a demo video showing the execution of the program from 12.2.1.  
3. Link to the program from 12.2.2.  
4. Link to a demo video showing the execution of the program from 12.2.2.  

## Resources
[[toc](#table-of-contents)]

1. [Github with MakeCode](https://makecode.microbit.org/github).  
2. [MakeCode language support](https://makecode.com/language).  
