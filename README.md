# Dobot Hand Tracking
Custom made Hand Tracking software for the Dobot Magician. 


This is software that I have coded to show off the Dobot Magician and its capabilities.


## Modes

### Hand tracking: 
when your hand is in the red box the arm will follow your movements, pinching your thumb and pointer finger together will close the claw, opening your fingers again would then open the claw. 


### Rock Paper Scissors: 
Camera checks which fingers are extended and guesses whether you are throwing rock, paper or scissors. The robot will then throw the counter to that move, rock (vertical, claws closed), paper (horizontal, claws open), scissors (vertical, claws open).


### Idle: 
Robot just moves between coordinates and rotates the claw.



## Main script Features

### Mode Lock: 
press 1,2,3,4 to select and lock modes (1 - hand tracking, 2 - rock paper scissors, 3 - idle, 4 - complete stop).


### Quit program: 
Q, just closes the program safely.


### Custom made functions: 
move_to_immediate(), gripper.open/close_immediate, suction_cup.suck/idle_immediate. This is because when the code runs at 30fps, it is sending the move to command 30 times per second, this would backlog the arm with a bunch of coordinates to move to which wouldn't follow your hand well. The new function stops the arm from receiving inputs until it has moved to the proper position. This is the same for gripper.open/close_immediate and suction_cup.suck/idle_immediate.


### Automatic hand scaling: 
will change the pinch distance based on how close or far your hand is


### Information labels: 
Tells you a lot of information about the bot - selected mode, coordinates of the bot, if you are pinching, which fingers are extended


## Test scripts

### FPS test: 
tests the FPS of the camera, Used because some webcams would run at extremely low FPS on my laptop while others would work fine. 


### Hand tracking: 
My Default file that I would go back to if something broke in the hand tracking, this was the first script I had made for the hand tracking and was used to show off how it worked with less clutter from other modes. 


### Port Finder: 
Finds which COM ports are being used and what they're being used for. (to find which COM port the arm was using) 


### Rotation calculation: 
When testing, the claws would rotate while moving, but i needed them to stay in the same rotation. My test script r_calibration gets and plots the current R value on a graph, using this i found the calculation to keep R straight when moving.


### Dobot API test: 
Connects to the Dobot arm, moves it to the set "Home" position, then opens and closes the claw 3 times. Used to check whether the connection was good. 

### Webcam Finder: 
Finds the webcams that are attached (used because we used a separate webcam to the default laptop one, as well as testing some other webcams)

