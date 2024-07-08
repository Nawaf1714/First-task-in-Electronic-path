First-task-in-Electronic-path
write an algorithm for operating servo motors to shape the robot's walking movement

The robot moves in repeated steps in which the feet alternate. We make one foot move before the other.

There are 6 servo motors, 3 for each foot. The right foot has a motor in the upper joint, knee joint, and foot joint.

Connecting electronic parts

First : we connect the power and ground port from the Arduino to the board.

Secondly : we connect each servo to the signal port on the Arduino.

Third : we connect all the power and ground ports from the servo motors to the board.

Fourth : Writing the code. After downloading the Arduino, we call the servo library and then we know the motors and where we connected them. We write functions that continuously repeat the movement of the feet.

code

#include <Servo.h>

Servo sr13,sr11,sr9,sl7,sl5,sl3;
int pos = 0;

void setup() {

sr13.attach(13);

sr11.attach(11);

sr9.attach(9);

sl7.attach(7);

sl5.attach(5);

sl3.attach(3);

}

void loop() {

for (pos = 0; pos <= 180; pos += 1) {

   sr13.write(pos);
   sr11.write(pos);
   sr9.write(pos);
delay(6);
}

for (pos = 180; pos >= 0; pos -= 1) {

   sr13.write(pos);
   sr11.write(pos);
   sr9.write(pos);
delay(10);
}

for (pos = 0; pos <= 180; pos += 1) {

   sl7.write(pos);
   sl5.write(pos);
   sl3.write(pos);
delay(10);
}

for (pos = 180; pos >= 0; pos -= 1) {

   sl7.write(pos);
   sl5.write(pos);
   sl3.write(pos);
delay(6);
}

}

<img width="892" alt="ardouinu" src="https://github.com/Nawaf1714/First-task-in-Electronic-path/assets/173706458/4b9dc61f-da87-40eb-8aec-43591c525067">
