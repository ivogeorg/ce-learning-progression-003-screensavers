# CPE 1040 - Fall 2020

## Learning Progression 003: Screensavers

### Topics

_Note: Composition and target-program learning curve in [progression notes](progression-notes.md)._

1. Arrays revisited  
    - array methods  
    - Multidimensional arrays   
    - Matching gestures with screensavers ([gist](https://gist.github.com/ivogeorg/efa6747383323654b3556e3c3470efa6))   
2. Screensavers ([gists](https://gist.github.com/ivogeorg)):   
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
      - [software stack revisited](https://mattwarren.org/2017/11/28/Exploring-the-BBC-microbit-Software-Stack/)  
      - threads, fibers, and the [fiber scheduler](https://lancaster-university.github.io/microbit-docs/advanced/)  
      - (Brendan) Does a time slice have to end for event handling to proceed?  
    - `forever` function vs `while (true)` loop  
      feature | `forever` | `while`
      -- | -- | --
      condition | no | yes
      `break` | no | yes
      scheduling | yes | no
    - Why you shouldn't have event handling in a `forever` loop  
    - How is `pause` executed and what is affected (e.g. other repeated behavior, event handling, etc.)  
      - `pause()` should be avoided, especially with multiple `forever()` loops  
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
