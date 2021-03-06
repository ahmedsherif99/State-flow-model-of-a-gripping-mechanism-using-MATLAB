# State-flow-model-of-a-gripping-mechanism-using-MATLAB
A gripper actuated using four-bar mechanism. It has four states depending on the power and pushbuttons. The states are:
  • Stop.
  • Start.
  • Forward Motion.
  • Backward Motion.
  • Gripping.
  
   Forward Motion, Backward Motion, and Gripping states are indicated by three LEDs. Each motion is actuated using its pushbuttons or by command from the mobile application. The mobile application is communicating with the Arduino using Bluetooth module. Potentiometer is used to select slow or rapid motion of the four-bar mechanism (Stepper motor). The State is displayed live on the LCD display.

   The first step of the project is to receive all inputs from Arduino pins and preprocess any noise. Then these inputs enter the state flow. The stop state is the default system state with power switch not off. The system is idle and waiting for the switch to be on and for the communication between the mobile app and the Arduino to establish. This idle state has the highest priority from all other state and is only when power is off at any time. When the system enters the start states it is waiting for one of the pushbuttons to be pressed or waiting for a command to be sent from the mobile application. After the blue button is pushed, the FW state starts and the four-bar mechanism moves forward and a blue LED indicates the states is turned on, the system runs this state until it reaches the limit switch, or the button is released. Then it returns to the start state. If the green button is pushed, the BW state starts and the four-bar mechanism moves backward, until it reaches the limit switch. Then it returns to the start state again. The final state is the gripping state, it uses a PID controller to control a servo motor based on the pressure required to hold the object.


Drive Video Link for Project Demonstration: https://drive.google.com/folderview?id=1L0iJrhx-nc_TFKU6miRPu-MTuPNgy04D

![image](https://user-images.githubusercontent.com/68401714/150700741-c2b326bc-269d-4acd-a545-b1f942787dc3.png)
![image](https://user-images.githubusercontent.com/68401714/150700902-23552ce6-351c-453f-8448-0c957d1fb28d.png)

