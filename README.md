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
1. Here is the GitHub Pages link for the game: https://shxuy.github.io/TowerOfHanoi_3D/index.html
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

## Code modification suggestions
1. If you want to adjust the position of camera in world coordinate, the angele of field of view or the position of 
light in world coordinate, please change numbers in function draw in main.js
2. If you want to adjust the position or the size of rods and discs, or the flying altitude of the moving disc, please
modify numbers in function Game in gameLogic.js
3. If you want to speed up the moving disc, please modify variable movingSpeed defined in 
Game.prototype.updateDiscPosition in gameLogic.js
4. I use some parallel lights, but you can swift to a dot light with a lot of work. I give out a brief instruction in
main.js
5. If you want to save power when running the game, please use a smaller number for framebuffer.resolution defined in 
allObjects.js at the expense of aliasing of the shadow.

## Known bug
1. If you use Safari, open the GitHub Pages link in new tab but do not swift to the web page immediately, the speed of 
the moving disc will be abnormally fast. The reason why the issue exists is that I use the first 10 frames to compute 
frame per second(FPS) and the speed of the moving disc depends on it. If the web page does not have focus, animation 
will be stopped by browser automatically to save energy so that the interval between the start time and the end time of 
my timer will be quite long and I cannot get the correct FPS. However, Chrome does not have the problem.

## Miscellaneous
1. It is best for computers or iPads, not mobile phones.
2. I meant to let users use mouse to drag and drop any discs, but the implementation will be too complicated without a 
physics engine because I have to implement collusion detection and mouse selection detection by myself. It is unwise 
to reinvent the wheel and WebGL is a little low-level for games so I suggest you choosing any game engine such as 
three.js to realize the feature. 

## Update: Procedural Wood & AI-Assisted Modernization

This project recently received a major visual and technical overhaul. The most significant change is that the wood texture is no longer an image file. It is now a 100% procedural texture generated in real-time by the GPU. By using fragment shaders and noise functions (mapped in polar coordinates for the rods' side and top faces), the wood grain, rings, and colors are calculated mathematically at 60fps.

**Other upgrades in this refactored version:**
*   **WebGL 2.0**: Upgraded from WebGL 1.0, utilizing native `DEPTH_COMPONENT24` for much cleaner and more accurate shadow mapping.
*   **Zero External Dependencies**: Removed reliance on `twgl-full.js`, jQuery, and `woodTexture.js`. The entire game is now contained in a single, modern, vanilla JavaScript file.
*   **Improved Lighting**: Added PCF (Percentage-Closer Filtering) for soft shadows and a Hemisphere lighting model for more natural ambient light. The ground and discs are now rendered with clean solid colors, while only the rods feature the procedural wood effect.

**A Developer's Reflection in 2026**
 
Looking back at 2018, writing the original WebGL 1 shadow mapping and debugging the `alert()` frame-rate bug took me an entire weekend of pure grinding. My original handwritten game logic and state machine were rock solid. 
 
Fast forward to today, I asked an AI to rewrite the rendering pipeline and implement a highly realistic 3D procedural wood shader which I originally thought was too complex to do without external textures. The visual upgrade was done in just a few minutes — a pace that is truly mind-blowing.
