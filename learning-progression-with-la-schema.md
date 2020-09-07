# CPE 1040 - Fall 2020

## Learning Progression 003: Screensavers

### Topics

1. Random(ized) behavior  
2. Program structure   
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
4. `forever` function vs `while (true)` loop  
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
  - [reactive system](https://makecode.microbit.org/device/reactive)  
  - [software stack revisited](https://mattwarren.org/2017/11/28/Exploring-the-BBC-microbit-Software-Stack/)  
  - threads, fibers, and the [fiber scheduler](https://lancaster-university.github.io/microbit-docs/advanced/)  
  - (Brendan) Does a time slice have to end for event handling to proceed?  
  - How is `pause` executed and what is affected (e.g. other repeated behavior, event handling, etc.)
5. Divide & conquer: program decomposition:  
   - 2 "modes": working and asleep  
   - code writing in working mode  
   - 5 gestures for five screensavers in asleep mode  
6. Why you shouldn't have event handling in a `forever` loop  
7. Incremental development + a closer look at Github  
8. Encapsulation revisited  
  - functions vs classes   
  - in JS, classes are functions under the hood  
  - [Static TS](https://www.microsoft.com/en-us/research/publication/static-typescript/)   
  - JS vs TS  
9. more on classes:  
  - object properties  
  - object literals: objects as dictionaries  
10. Arrays revisited  
    - Multidimensional arrays   
    - Matching gestures with screensavers ([gist](https://gist.github.com/ivogeorg/efa6747383323654b3556e3c3470efa6))   
11. Target ([gists](https://gist.github.com/ivogeorg)):   
  - "rain" (Ivo)  
    - challenge: rain at 45°
  - [fireworks](https://github.com/Introduction-to-Computer-Engineering/screensavers-for-the-micro-bit-AKA-turtle/blob/master/screensaver.js) (Dwight)  
    - need to add the pre-explosion arc  
  - bouncy ball (Dwight)  
    - challenge: change the "bouncing" coefficient of the ball  
  - [snake](https://github.com/iconoptic/snake-microbit/blob/master/snake.js) (Brendan)  
  - frequency bar (Ivo)  
  - pond ripples  
    - reflection and fading at the walls  
12. Namespaces (`basic`, `input`, etc.)  
    
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
