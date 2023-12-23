<h1 align="center" style="font-size:20">
Endless Runner
</h1>

<p align="center">
A simple game that can be played on a 8x8 LED matrix.
</p>


#### Components Used

<img src="https://github.com/Pepi100/Endless-Runner/blob/master/Birdseye.png" align="right"
     alt="Diagram" width="700">


* 1x 8x8 LED Martrix
* 1x MAX7219 Driver
* 1x 16x2 LCD Display
* 1x Active Buzzer
* 1x Joystick
* 1x Potentiometer
* 1x Arduino Uno
* 1x Half breadboard
* 1x Mini breadboard
* 1x 10uf Electrolytic Capacitor
* 1x 104 pF Ceramic Capacitor
* 1x 100K&#8486; rezistor
* 1x 10K&#8486; rezistor
* 1x 100&#8486; rezistor
* many colorful wires

[Demo](https://www.youtube.com/watch?v=fO3gBPfXR-w)

#### Technical Task
>The task involves developing a complete game on the 8x8 LED Matrix.

### The game:
     
"Endless Runner" is a fast-paced endless game designed to run on an Arduino. The goal is simple: survive for as long as possible by skillfully jumping over and crouching under obstacles. The game progressively intensifies as the obstacles aproach at a higher and higher speed as the player travels more.



<summary> How it works:</summary>

  #### Main Loop
  

  The main loop constantly reads input from the joystick and passes it to specific functions, accorting to the current "state" variable value.

| Value | Meaning |
| :---:   | :---: |
| 0 | Initial screen  |
| 1 | Main menu  |
| 2 | In game state, including game start and end screen  |
| 3 | Settings  |
| 4 | About  |
| 5 | How to play  |
| 6 | Leaderboard  |
| 7 | Difficulty  |

Each of these states is split into 2 main parts, display and logic, reprezented in code by two functions. 

Display functions take care of the information that should appear on the LCD during a specific state. Display functions are only called when update tag has been set because we only want the display to update when new information needs to be displayed.

Logic Functions take care of processing the user's input and overall logic of that state. These functions set the update tag.
