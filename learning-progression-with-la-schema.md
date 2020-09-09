# CPE 1040 - Fall 2020

## Learning Progression 003: Screensavers

### Topics

1. Encapsulation revisited  
   - the benefits of encapsulation  
   - functions vs classes   
   - in JS, [classes are functions under the hood](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)    
   - [Static TS](https://www.microsoft.com/en-us/research/publication/static-typescript/)   
   - JS vs TS  
2. more on classes:  
   - object properties  
   - object literals: objects as dictionaries  
3. Pass by value, pass by reference  
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
4. Arrays revisited  
    - array methods  
    - Multidimensional arrays   
    - Matching gestures with screensavers ([gist](https://gist.github.com/ivogeorg/efa6747383323654b3556e3c3470efa6))   
5. Namespaces (`basic`, `input`, etc.)  
   - Code reading: https://github.com/microsoft/pxt-microbit/blob/master/libs/core/game.ts  
     - export  
     - functions (`createSprite`)  
     - classes (`LedSprite`)  
     - namespaces (`game`)  
     - use of variables  
   - micro:bit [tech docs](https://makecode.com/docs)  
   - TS [namespaces](https://www.typescriptlang.org/docs/handbook/namespaces.html)  
6. Reactive sysem  
   - [reactive system](https://makecode.microbit.org/device/reactive)  
   - [software stack revisited](https://mattwarren.org/2017/11/28/Exploring-the-BBC-microbit-Software-Stack/)  
   - threads, fibers, and the [fiber scheduler](https://lancaster-university.github.io/microbit-docs/advanced/)  
   - (Brendan) Does a time slice have to end for event handling to proceed?  
   - How is `pause` executed and what is affected (e.g. other repeated behavior, event handling, etc.)
7. Why you shouldn't have event handling in a `forever` loop  
8. `forever` function vs `while (true)` loop  
   - this code requires a `pause` after `clearScreen`:
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
9. Program structure  
   - global vars  
   - function and class declarations  
   - event handlers  
   - forever loops  
10. Divide & conquer: program decomposition:  
    - high-level program structure:  
      - 2 "modes": working and asleep  
      - code writing in working mode  
      - 5 gestures for five screensavers in asleep mode  
    - analysis and decomposition of target programs   
11. Incremental development + a closer look at Github  
    - status, add, commit, pull, push  
    - remote & local (git SCM)  
    - Github workflow (pull requests, Github Classroom **Feedback**)  
    - informative commit messages  
    - releases & tags  
    - incremental development example
12. Random(ized) behavior  
13. Target ([gists](https://gist.github.com/ivogeorg)):   
    - "rain" (Ivo)  
      - challenge: rain at 45°
    - [fireworks](https://github.com/Introduction-to-Computer-Engineering/screensavers-for-the-micro-bit-AKA-turtle/blob/master/screensaver.js) (Dwight)  
      - challenge: pre-explosion arc  
    - bouncy ball (Dwight)  
      - should add horizontal motion? => too short a path, unless we bounce off the walls  
      - challenge: change the "bouncing" coefficient of the ball  
    - [snake](https://github.com/iconoptic/snake-microbit/blob/master/snake.js) (Brendan)  
    - frequency bar (Ivo)
      - challenge: 
    - pond ripples  
      - challenge: reflection and fading at the walls  
    

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
