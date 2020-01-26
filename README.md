# CPE 1040 - Introduction to Computer Engeneering

## Assignment: Exploring JavaScript by Designing a Microbit "Screensaver"

### 1. Summary

This assignment asks you to design a program and implement it in micro:bit JavaScript (that is, TypeScript) from scratch. **No Blocks!** This assignment is submitted through Github.

### 2. Requirements

#### 2.1 "Screensavers"

1. Design 5 abstract, randomized, moving patterns for the 5x5 LED array. Some ideas:
   1. Rotating "lines" like | / - \ | / -, that are centered at different spots.
   2. Dots that appear gradually and disappear gradually (use LED intensity), at random positions.
   3. Gradient waves, vertical, horizontal, or diagonal, where the parallel rows, columns, or diagonal lines change their intentsity in a wave-like manner.
   4. Concentric version of the gradient waves.
   5. **BONUS:** For the most original and unexpected "screensaver" pattern.
   
2. Make sure you can control which one is displayed. It's a good idea to wrap them in functions.

3. **BONUS:** Write a Screensaver class for the micro:bit.

4. The "screensaver" should time out and the "screen" should go blank.

#### 2.2 Controls

1. Use the A button to "put the screen to sleep" (that is, activate the "screensaver").

2. Use the B button to "wake the screen up". When the micro:bit is awake, the 5x5 LED matrix should just scroll some sentence of your choosing.

3. **BONUS:** Require that the A button is _held down_ for 2 seconds to activate the "screensaver".

#### 2.3 Gestures

1. Pick 5 gestures to correspond to your 5 "screensavers". When the micro:bit detects a gesture, it should switch to the corresponding "screensaver".

2. The gestures should work _only_ when the "screensaver" is on.

#### 2.4 Github commits

1. Feel free to work in MakeCode, as long as you only write JavaScript. 

2. Copy your program file from Makecode to the open JS file in your remote repository on Github. The first time around, it will be a new file. Subsequently, overwrite the contents with the updated program. Github will be able to show you the differences between commits, because it does it on the fly and based on textual comparison.

3. Commit often, and include informative messages.

#### 2.5 README

1. Each time you design a new "screensaver", describe it in the [screensavers](#screensavers) section of the README.

#### 2.6 Demo video

1. Record a short video with your phone of your "screensavers" changing from gesture to gesture.

2. Upload it to [Imgur](https://help.imgur.com/hc/en-us/articles/115000083326-What-files-can-I-upload-What-is-the-size-limit-).

3. Include the URL in the [demo URL](#demo-url) section of the README.

## Resources

### micro:bit 

1. [micro:bit lessons](https://makecode.microbit.org/lessons).

2. [micro:bit ideas](https://microbit.org/ideas/).

3. A list of some more [advanced projects](https://www.itpro.co.uk/desktop-hardware/26289/13-top-bbc-micro-bit-projects).

4. The [projects](https://www.itpro.co.uk/desktop-hardware/26289/13-top-bbc-micro-bit-projects) at the [awesome micro:bit list](https://github.com/carlosperate/awesome-microbit).

### Github

1. Github Tutorial for Beginners ([webpage](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners)).

2. Github Basics for Mac and Windows ([video](https://www.youtube.com/watch?v=0fKg7e37bQE)).

3. git & Github Crash Course for Beginners ([video](https://www.youtube.com/watch?v=SWYqp7iY_Tc)).

4. Introduction to Github for Beginners ([video](https://www.youtube.com/watch?v=fQLK8Ib_SKk)).

5. About `git` ([webpage](https://git-scm.com/about)).

6. `git` [documentation](https://git-scm.com/doc) (webpage, book, videos, reference manual).

7. [Github markdown cheat sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

### JavaScript

1. Technically, the language which is used side-by-side with Blocks in the Makecode environment is a subset of [TypeScript](https://makecode.com/language), which itself is a superset of JavaScript (technically, [ECMAScript](https://www.ecma-international.org/ecma-262/10.0/index.html#Title)), with some JS features not implemented in Makecode.

2. The limited [JavaScript mini-tutorial](https://makecode.microbit.org/javascript) in Makecode. Make sure you read it but that can't be your only reference.

3. Official [TypeScript documentation]():
   1. TypeScript in 5 min [tutorial](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html). _**Highly recommended!** You will need to [download](https://www.typescriptlang.org/index.html#download-links) and install an integrated development envinronment (IDE). The two that I recommend are Visual Studio Code from Microsoft and WebStorm from JetBrains._
   2. The full documentation and reference is under _Handbook_. Bear in mind that you are drinking from the hose. Don't be surprised if not everything is presented in a strictly incremental manner.
   
4. In-browser TypeScript [playground](https://www.typescriptlang.org/play/index.html). Note that micro:bit specific code will not run, but you can still play. _Start making the distinction between a generic multi-purpose programming language (TypeScript) and functionality (packages, libraries, objects, etc.) that is specific to a particular device (micro:bit), though written in the same programming language._

5. A pretty good and very palatable JS tutorial with in-browser coding, by [Codecademy](https://www.codecademy.com/learn/introduction-to-javascript).

6. Extensive and detailed [JS tutorial](https://javascript.info/), with some advanced material thrown in. _**I like this one!**

7. The most authoritative JS resource on the Web, including tutorials and reference, by [Mozilla](https://developer.mozilla.org/en-US/docs/Web/JavaScript).

---

## Screensavers

### SS 1

_[Your description of screensaver 1]_

### SS 2 

_[And so on]_

## Demo URL

