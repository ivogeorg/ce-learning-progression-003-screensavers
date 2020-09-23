# CPE 1040 - Fall 2020

This is learning progression 003 for the Fall 2020 installment of the course CPE 1040: Introduction to Computer Engineering at MSU Denver.

## Learning Progression 003: Screensavers

This progression is the culmination of the first part of the course, in which we program the bear-bones micro:bit without any extenral circuitry attached and without communication features. We pull together all the programming language features and best practices that we introduced in the previous two learning progressions, to write a significantly larger target program over 12 steps. This will present the opportunity to learn about some of the design considerations a programmer makes when approaching a larger project. The progression is also going to dig a bit deeper into the _softare stack_ of the micro:bit, and uncover the ways it affects these considerations.

### 1. Arrays revisited  

#### 1. Study  

`[<lernact-rd>]` We have already seen how versatile and powerful arrays can be in a program, allowing us to achieve complex program behavior far more easily than if arrays weren't available to the programming language. Let's quickly review what arrays are. An `[<cept>]`_array_ is an _ordered sequence_ of elements _of the same type_. Because it holds more than one piece of data, it is also called a `[<cept>]`[_data structure_](https://en.wikipedia.org/wiki/Data_structure). Like any other variable and function, an array has a _name_. This name can be used to refer not only to the whole array, but to individual elements of the array. Because they are ordered, they can be referenced by `[<cept>]`_index_, that is, by their place in the order, using the `[<cept>]`_selection operator_ `[]` (opening and closing square bracket). Let's take a look:
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

The usefulness of the arrays doesn't stop with the ability to keep a collection of data together. Arrays come with many useful `[<cept>]`_methods_ and `[<cept>]`_properties_ for manipulating the elements of the collection or the whole collection itself. In Example 1.1.1, we already encountered the `length` property. The best way to explore methods in MakeCode is to declare an array variable, invoke the dropdown by using the `.` selection operator to pick a method or property, 

<img src="images/method-dropdown.png" alt="MakeCode editor method dropdown" width="400"/>  

and then hover over the name to invoke the documentation popup.

<img src="images/doc-popup.png" alt="MakeCode editor method dropdown" width="400"/>  

Let's take a look at some of the methods:
```javascript
// Example 1.1.2


```
methods are called as functions...
properties are called as fields...

    - array methods  
    - Multidimensional arrays   
    - Matching gestures with functions   
    
#### 2. Apply  

#### 3. Present  

### 2. Screensavers   
   - code writing simulation in work mode  
     - challenge: scroll up the already written text, adding one line at a time, except the first 4  
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
   - pond ripples  
     - TODO:
       - fading away from drop splash point  
       - interference patterns with brightness  
     - challenge: reflection and further fading at the walls  
3. Program structure  
   - global vars  
   - function and class declarations  
   - event handlers  
   - forever loops  
4. Divide & conquer: program decomposition:  
   - high-level program structure:  
     - 2 "modes": working and asleep  
     - code writing in working mode  
     - 5 gestures for five screensavers in asleep mode  
   - analysis and decomposition of target programs   
5. Encapsulation    
   - the benefits of encapsulation  
   - functions
   - classes   
   - namespaces (`basic`, `input`, `game`, etc.)    
6. Functions revisited  
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
7. Classes revisited    
   - object properties  
   - object literals: objects as dictionaries  
   - in JS, [classes are functions under the hood](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)  
   - TODO  
     - [Static TS](https://www.microsoft.com/en-us/research/publication/static-typescript/) implementation  
     - prototypes (too much)  
     - JS vs TS  
8. Code reading: https://github.com/microsoft/pxt-microbit/blob/master/libs/core/game.ts  
   - export  
   - functions (`createSprite`)  
   - classes (`LedSprite`)  
   - namespaces (`game`)  
   - use of variables  
   - TODO:
     - micro:bit [tech docs](https://makecode.com/docs)  
     - TS [namespaces](https://www.typescriptlang.org/docs/handbook/namespaces.html)  
9. Iterative development with Github  
   - status, add, commit, pull, push  
   - remote & local (git SCM)  
   - Github workflow (pull requests, Github Classroom **Feedback**)  
   - informative commit messages  
   - releases & tags  
   - incremental development example
10. Reactive sysem  
    - [reactive system](https://makecode.microbit.org/device/reactive)  
    - `forever` function vs `while` loop  
      feature | `forever` | `while`
      -- | -- | --
      condition | no | yes
      `break` | no | yes
      scheduling | yes | no
    - Why you shouldn't have event handling in a `forever` loop  
    - How is `pause` executed and what is affected (e.g. other repeated behavior, event handling, etc.)  
      - `pause()` should be avoided, especially with multiple `forever()` loops  
    - Advanced material: [software stack](https://mattwarren.org/2017/11/28/Exploring-the-BBC-microbit-Software-Stack/)  
      - threads, fibers, and the [fiber scheduler](https://lancaster-university.github.io/microbit-docs/advanced/)  
      - issues of speed, memory, etc.  
      - (Brendan) Does a time slice have to end for event handling to proceed?  
11. Matrix dynamics  
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
12. Randomized behavior  
    - dimensions of randomization  
    - the family of random functions  (`random`, `randint`, `randomBoolean()`, etc.)   
    - write your own custom randomization routines  


### For later LP
1. Stack frames: here or further along the curriculum (if so, where?)   
2. [interfaces](https://makecode.microbit.org/javascript/interfaces)?  
3. Memory layout.  
4. Data structures, abstract data types, and algorithms:  
   - [data structures vs ADTs](https://www.google.com/search?q=data+structure+vs+abstract+data+type&oq=data+structure+vs+&aqs=chrome.0.0l2j69i57j0l5.4669j0j7&sourceid=chrome&ie=UTF-8)  
   - array, linked-list, map (dictionary, hash table), tree   
   - stack, queue  
   - sorting  
   
   

### Step 1: 

#### 1. Study
#### 2. Apply
#### 3. Present
