# 3D tower of Hanoi drawn by WebGL

## Introduction
The Tower of Hanoi is a mathematical game or puzzle. It consists of three rods and a number of disks of different sizes,
 which can slide onto any rod. The puzzle starts with the disks in a neat stack in ascending order of size on one rod, 
 the smallest at the top, thus making a conical shape.

The objective of the game is to move the entire stack to another rod, obeying the following simple rules:
1. Only one disk can be moved at a time.
2. Each move consists of taking the upper disk from one of the stacks and placing it on top of another stack.
3. No disk may be placed on top of a smaller disk.

## Ways to run the program
1. Here is the GitHub Pages link for the game: // TODO
2. Download all files and run index.html in your native browser
3. Modify paths of JavaScript files in index.html and use your own server

## Ways of control
1. You could drag the screen by mouse to adjust the view
2. You could click buttons on the web page to move discs
3. You could also press keys denoted in texts of buttons to move discs instead of clicking buttons. Here is the list of 
hot keys:

    | key | motion                                      |
    | --- | ------------------------------------------- |
    | Q   | move a disc from the 1st rod to the 2nd rod |
    | A   | move a disc from the 1st rod to the 3rd rod |
    | W   | move a disc from the 2nd rod to the 1st rod |
    | S   | move a disc from the 2nd rod to the 3rd rod |
    | E   | move a disc from the 3rd rod to the 1st rod |
    | D   | move a disc from the 3rd rod to the 2nd rod |
4. You could click the button 'solve it' to watch the solving animation

## Miscellaneous
1. It is best for computers, not mobile phones.
2. I meant to let users use mouse to drag and drop any discs, but the implementation will be too complicated without a 
physics engine because I have to implement collusion detection and mouse selection detection by myself. It is unwise 
to reinvent the wheel and WebGL is a little low-level for games so I suggest you choosing any game engine such as 
three.js to realize the feature. 

