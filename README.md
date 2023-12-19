<h1 align="center" style="font-size:20">
Endless Runner
</h1>

<p align="center">
A simple game that can be played on a 8x8 LED matrix.
</p>



<img src="https://github.com/Pepi100/IntroductionToRobotics/blob/master/%236%20-%20Environment%20Monitor%20and%20Logger/Diagram.png" align="right"
     alt="Diagram" width="500">

#### Components Used

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


#### Technical Task
>The task involves developing a complete game on the 8x8 LED Matrix.



  <summary> How it works:</summary>

  #### Main Loop
  <img src="https://github.com/Pepi100/IntroductionToRobotics/blob/master/%236%20-%20Environment%20Monitor%20and%20Logger/Loop.png" align="right"
     alt="Diagram" width="500">
  
  The main loop constantly reads data form the sensors and triggers the alert if necessary. It is also responsible for reading input from [serial](https://www.arduino.cc/reference/en/language/functions/communication/serial/), which it than passes to:

  ```cpp
    void advanceMenu(int option);
  ```
  This function takes over the main functionality of the program. It takes the input from the user and uses it to perform the required action, according to the number of the current menu. This function implements a giant switch.



  ```cpp
    void printMenu();
  ```
  Works identical to advanceMenu(), but is only responsible for printing the options available in the current menu.



  ```cpp
  short movementMatrix[MENUS][MAX_MENU_OPTIONS]={
    {-1,1,2,3,4},
    {-1,11,12,13,0},
    {-1,21,22,23,0},
    {-1,31,32,33,0},
    {-1,41,42,0,-1},
  };
  ```
  In order to traverse faster between menus, I've implemented this movement matrix that keeps track of what menu (or submenu) the program should switch to next.



