# CPE 1040 - Fall 2020

## Learning Progression 003: Screensavers

Topics:
- random behavior  
- `forever` function vs `while (true)` loop
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
- divide & conquer: program "modes"  
- why you shouldn't have event handling in a `forever` loop  
- incremental development + a closer look at Github  
- encapsulation redus: functions vs classes   
- classes redux: [interfaces](https://makecode.microbit.org/javascript/interfaces)?  
- multidimensional arrays  
- JS vs TS  
- target: 
  - "rain" at 45°  
  - fireworks (Dwight)  
  - snake (Brendan)
  - selection from the best ones from last semesters  
- namespaces (`basic`, `input`, etc.)

### Step 1: 

#### 1. Study
#### 2. Apply
#### 3. Present
