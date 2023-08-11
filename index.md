
# Mini Object Avoiding Robot
This obstacle-avoiding robot displays the solution to ground-level accidents in the aviation industry. Placing ultrasonic sensors, which measure the distance from the sensor to another object, on the nose gear and the two wingtips will detect and prevent the aircraft from striking an object. Using Arduino and various hardware sources, I have created a prototype to save the aviation industry thousands of dollars.

You should comment out all portions of your portfolio that you have not completed yet, as well as any instructions:
```HTML 
<!--- This is an HTML comment in Markdown -->
<!--- Anything between these symbols will not render on the published site -->
```

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Spencer K | Fayetteville High School | Aerospace Engineering | Incoming Senior

![Spencer BSE Project](https://github.com/srkatz1/Spencer_BlueStampPortfolio/assets/140825566/bda99387-5944-41ec-ba70-f679716ee6af)


  
# Final Milestone


<iframe width="560" height="315" src="https://www.youtube.com/embed/pRUXsx4GDG8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


After completing my final milestone at Blue Stamp Engineering, I reflected on my experience and accomplishments here. Starting with the positives, the robot is fully operational the way I imagined it three weeks ago. The robot can move forward, backward, left, and right using a remote. Additionally, I added three ultrasonic sensors to the robot: one at the nose of the robot and two on each side of the robot (mounted on Lego wings). Using sound waves, each sensor detects the same data, the distance from the robot to an object ahead of it. However, when an individual sensor detects an object, it causes the robot to react differently. If the sensor on the nose of the robot detects something, the robot will stop and go backward for half a second. If the sensor on the left wing detects something, the robot will stop, move back for a fourth of a second, turn right, and move forward to avoid the object. If the sensor on the right wing detects an object, it will operate the same as the latter, but the robot will turn left instead of right. I was ecstatic when I finally figured out how to program the robot, but it was not always easy. Lining up the tire treads was the most challenging process during these three weeks. Some of the wiring was difficult because of the mass amount of wires -- it got confusing after a little bit. With all of these challenges came great lessons. I discovered how mechanical and electrical engineering mesh together to create a fantastic product, and I got exposed to C++ syntax for the first time. In the future, I plan to build on the foundation I have made at Blue Stamp and develop more advanced projects to impact the world significantly.


# Second Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/R3Zbe-6IdEo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Achieving my goal of a remote-controlled robot was a massive leap in completing my project. I programmed the IR remote to move the robot forward and backward, turn left and right, and stop. By default, the remote uses hexadecimal numbers to determine which button is clicked, which can confuse a new programmer. I translated the hexadecimal numbers to simple words such as up, down, left, right, and stop to simplify my program. Currently, the robot moves in all directions when the user clicks the corresponding button. Because of my previous experience with Python (a computer programming language), I was surprised to discover how similar C++ syntax was to Python. This similarity made software development much easier than I thought. To complete my project, I will program three ultrasonic sensors to detect objects in front of the robot and avoid them. 

# First Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/qWKYwoYF6oM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
 
My first milestone was to complete the hardware of the base project. An abundance of nuts and bolts keep the robot sturdy to handle various types of surfaces and help the robot to operate flawlessly. The motors will be able to move using electrical connections based on commands given through the Arduino once the software is downloaded. Overall, building the robot was not difficult; however, lining up the tire treads was the most challenging part. Holding the bolts and lining up two wheels simultaneously was difficult, and it took me a couple of hours to complete. With the main hardware complete, my next goal is to program the robot to move in various directions using a remote control.

# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 

# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

~~~c++
#include <IRremoteTank.h>
  int RECV_PIN = A0;//define the pin of IR receiver as A0
  int trigPinFront = 5;    // Trigger for Nose Sensor
  int echoPinFront = 4;    // Echo for Nose Sensor
  int trigPinLeft = 10;    // Trigger for Left Wing Sensor
  int echoPinLeft = 9;    // Echo for Left Wing Sensor
  int trigPinRight = 7;    // Trigger for Right Wing Sensor
  int echoPinRight = 8;    // Echo for Right Wing Sensor
  long durationfront, durationLeft, durationRight, cmfront, cmLeft, cmRight;
  int ML_Ctrl=13; //define the direction control pin of right motor
  int ML_PWM=11;  //define the PWM control pin of right motor
  int MR_Ctrl=12;  //define direction control pin of left motor
  int MR_PWM=3 ;  // define the PWM control pin of left motor
  long up = 0xFF629D;
  long left = 0xFF22DD;
  long right = 0xFFC23D;
  long down = 0xFFA857;
  long stop = 0xFF02FD;

  IRrecv irrecv(RECV_PIN);
  decode_results results;

  void setup() {
    //Serial Port begin
    Serial.begin (9600);
    //Define inputs and outputs
    irrecv.enableIRIn(); // Initialize the IR receiver 
    pinMode(ML_Ctrl, OUTPUT);//define direction control pin of left motor as output
    pinMode(ML_PWM, OUTPUT);//define PWM control pin of left motor as output
    pinMode(MR_Ctrl, OUTPUT);//define direction control pin of right motor as output.
    pinMode(MR_PWM, OUTPUT);//define the PWM control pin of right motor as output
    pinMode(trigPinFront, OUTPUT);
    pinMode(echoPinFront, INPUT);
    pinMode(trigPinLeft, OUTPUT);
    pinMode(echoPinLeft, INPUT);
    pinMode(trigPinRight, OUTPUT);
    pinMode(echoPinRight, INPUT);
  
}
  void forward(){
    Serial.println("forward");
    digitalWrite(ML_Ctrl,LOW);//set the direction control pin of left motor to LOW
    analogWrite(ML_PWM,200);//set the PWM control speed of left motor to 200
    digitalWrite(MR_Ctrl,LOW);//set the direction control pin of right motor to LOW
    analogWrite(MR_PWM,200);//set the PWM control speed of right motor to 200
  }
  void backward(){
    Serial.println("backward");
    digitalWrite(ML_Ctrl,HIGH);//set the direction control pin of left motor to LOW
    analogWrite(ML_PWM,200);//set the PWM control speed of left motor to 200
    digitalWrite(MR_Ctrl,HIGH);//set the direction control pin of right motor to LOW
    analogWrite(MR_PWM,200);//set the PWM control speed of right motor to 200
  }
  void left_sensor(){
    Serial.println("left");
    digitalWrite(ML_Ctrl,HIGH);//set the direction control pin of left motor to LOW
    analogWrite(ML_PWM,200);//set the PWM control speed of left motor to 200
    digitalWrite(MR_Ctrl,LOW);//set the direction control pin of right motor to LOW
    analogWrite(MR_PWM,200);//set the PWM control speed of right motor to 200
  }
  void right_sensor(){
    Serial.println("right");
    digitalWrite(ML_Ctrl,LOW);//set the direction control pin of left motor to LOW
    analogWrite(ML_PWM,200);//set the PWM control speed of left motor to 200
    digitalWrite(MR_Ctrl,HIGH);//set the direction control pin of right motor to LOW
    analogWrite(MR_PWM,200);//set the PWM control speed of right motor to 200
  }
  void stop_sensor(){
    Serial.println("stop");
    digitalWrite(ML_Ctrl,LOW);//set the direction control pin of left motor to LOW
    analogWrite(ML_PWM,0);//set the PWM control speed of left motor to 200
    digitalWrite(MR_Ctrl,LOW);//set the direction control pin of right motor to LOW
    analogWrite(MR_PWM,0);//set the PWM control speed of right motor to 200
  }
  void loop() {

    // Remote Motor Controls
       if (irrecv.decode(&results)) {
     if (results.value== up) 
{
      Serial.println("forward");
      digitalWrite(ML_Ctrl,LOW);//set the direction control pin of left motor to LOW
      analogWrite(ML_PWM,200);//set the PWM control speed of left motor to 200
      digitalWrite(MR_Ctrl,LOW);//set the direction control pin of right motor to LOW
      analogWrite(MR_PWM,200);//set the PWM control speed of right motor to 200
} 
    if (results.value== down) 
{
    Serial.println("backward");
    digitalWrite(ML_Ctrl,HIGH);//set the direction control pin of left motor to LOW
    analogWrite(ML_PWM,200);//set the PWM control speed of left motor to 200
    digitalWrite(MR_Ctrl,HIGH);//set the direction control pin of right motor to LOW
    analogWrite(MR_PWM,200);//set the PWM control speed of right motor to 200
    
} 
    if (results.value== left) 
{
      Serial.println("left");
      digitalWrite(ML_Ctrl,HIGH);//set the direction control pin of left motor to LOW
      analogWrite(ML_PWM,200);//set the PWM control speed of left motor to 200
      digitalWrite(MR_Ctrl,LOW);//set the direction control pin of right motor to LOW
      analogWrite(MR_PWM,200);//set the PWM control speed of right motor to 200
    
} 
    if (results.value== right) 
{
      Serial.println("right");
      digitalWrite(ML_Ctrl,LOW);//set the direction control pin of left motor to LOW
      analogWrite(ML_PWM,200);//set the PWM control speed of left motor to 200
      digitalWrite(MR_Ctrl,HIGH);//set the direction control pin of right motor to LOW
      analogWrite(MR_PWM,200);//set the PWM control speed of right motor to 200
    
} 
    if (results.value== stop)
{
      Serial.println("stop");
      digitalWrite(ML_Ctrl,LOW);//set the direction control pin of left motor to LOW
      analogWrite(ML_PWM,0);//set the PWM control speed of left motor to 200
      digitalWrite(MR_Ctrl,LOW);//set the direction control pin of right motor to LOW
      analogWrite(MR_PWM,0);//set the PWM control speed of right motor to 200
}

    irrecv.resume();

}

    // Sensor Controls
      digitalWrite(trigPinFront, LOW);
      delayMicroseconds(2);
      digitalWrite(trigPinFront, HIGH);
      delayMicroseconds(10);
      digitalWrite(trigPinFront, LOW);
      durationfront = pulseIn(echoPinFront, HIGH);
      digitalWrite(trigPinLeft, LOW);
      delayMicroseconds(2);
      digitalWrite(trigPinLeft, HIGH);
      delayMicroseconds(10);
      digitalWrite(trigPinLeft, LOW);
      durationLeft = pulseIn(echoPinLeft, HIGH);
      digitalWrite(trigPinRight, LOW);
      delayMicroseconds(2);
      digitalWrite(trigPinRight, HIGH);
      delayMicroseconds(10);
      digitalWrite(trigPinRight, LOW);
      durationRight = pulseIn(echoPinRight, HIGH);
     // Read the signal from the sensor: a HIGH pulse whose
    // duration is the time (in microseconds) from the sending
    // of the ping to the reception of its echo off of an object.
     // Convert the time into a distance
      cmfront = (durationfront/2) / 29.1;     
      Serial.print(cmfront);
      Serial.print("cm");
      Serial.println();
      cmLeft = (durationLeft/2) / 29.1;     
      Serial.print(cmLeft);
      Serial.print("cm");
      Serial.println();
      cmRight = (durationRight/2) / 29.1;     
      Serial.print(cmRight);
      Serial.print("cm");
      Serial.println();

    if (cmfront < 15){
      results.value== 0;
      Serial.println("FrontSensor: Stop due to object avoidance");
      stop_sensor();
      delay(500);
      backward();
      delay(500);
      stop_sensor();
      if (results.value== stop){
        stop_sensor();
    }
  }
    if (cmLeft < 10){
      results.value== 0;
      Serial.println("Left Sensor: Stop due to object avoidance");
      stop_sensor();
      delay(200);
      backward();
      delay(1000);
      right_sensor();
      delay(400);
      forward();
      delay(1000);
      stop_sensor();
      if (results.value== stop){
        stop_sensor();
    }
  }
    if (cmRight < 10){
      results.value== 0;
      Serial.println("Right Sensor: Stop due to object avoidance");
      stop_sensor();
      delay(1000);
      backward();
      delay(1000);
      left_sensor();
      delay(400);
      forward();
      delay(1000);
      stop_sensor();
      if (results.value== stop){
        stop_sensor();
    }
  }
}
//****************************************************************
~~~

# Bill of Materials
| Keyestudio DIY Mini Tank V2.0 Smart Robot car kit for Arduino STEM | Foundation of the Project | $78.90 | <a href="https://www.keyestudio.com/products/new-keyestudio-diy-mini-tank-v20-smart-robot-car-kit-for-arduino-robot-stem-mixly-blocks-coding-support-ios-ampampandroid-app-1"> Mini Tank Robot V2 </a> |
| WWZMDiB Ultrasonic Sensor Module | Additional Sensors for Modification | $7.99 | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6"> 3 Extra Sensors </a> |

# Other Resources/Examples
- [Arduino Reference](https://www.arduino.cc/reference/en/)
- [Mini Tank Robot V2 Wiki](https://wiki.keyestudio.com/Ks0428_keyestudio_Mini_Tank_Robot_V2)
