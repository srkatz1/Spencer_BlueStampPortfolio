# Mini Tank Robot
Replace this text with a brief description (2-3 sentences) of your project. This description should draw the reader in and make them interested in what you've built. You can include what the biggest challenges, takeaways, and triumphs from completing the project were. As you complete your portfolio, remember your audience is less familiar than you are with all that your project entails!

You should comment out all portions of your portfolio that you have not completed yet, as well as any instructions:
```HTML 
<!--- This is an HTML comment in Markdown -->
<!--- Anything between these symbols will not render on the published site -->
```

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Spencer K | Fayetteville High School | Aerospace Engineering | Incoming Senior

**Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**

![Headstone Image](logo.svg)
  
# Final Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE
After completing my final milestone at Blue Stamp Engineering, I took some time to reflect on my experience and what I have accomplished here. Starting with the positives, the robot is fully operational that way that I imagined it three weeks ago. The robot can move forward, backward, left, and right using a remote. Additionally, I added three ultrasonic sensors to the robot: one at the nose of the robot and two on each side of the robot (mounted on Lego wings). Using sound waves, each sensor detects the same data, the distance from the robot to an object ahead of it. However, when an individual sensor detects an object, it causes the robot to react in different ways. If the sensor on the nose of the robot detects something, the robot will stop and go backward for a half of a second. If the sensor on the left wing detects an object, the robot will stop, move backward for a fourth of a second, turn right, and move forward to avoid the object. If the sensor on the right wing detects an object, it will operate the same as the latter, but the robot will turn left instead of right. I was ecstatic when I finally figured out how to program the robot, but it was not always easy. Lining up the tire treads was the most difficult process during these three weeks. Some of the wiring was difficult because of the mass amount of wires -- it got confusing after a little bit. With all of these challenges came great lessons. I discovered how mechanical and electrical engineering mesh together to create an amazing product a


# Second Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/R3Zbe-6IdEo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

The second milestone was getting the motors to be fully operational using the IR remote control. Using trial and error, I discovered that many of the functions in C++ are similar to Python functions, which helped me achieve milestone two in only two days—for example, using "if statements" allow me to control the direction of the robot when a specific button is pressed. To complete my project, I must program the ultrasonic sensor to help the robot avoid objects. I will use three separate sensors, which will all operate similarly and simultaneously.

# First Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/qWKYwoYF6oM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
 
The first milestone was completing the structural build of my robot and testing the motors. Using a series of "motherboards" and wires, the robot can process information and move left, right, forward, and backward. Following instructions are simple; however, some parts, such as the tire treads, were difficult to attach. Aligning them was difficult because the load-bearing wheel would sometimes stick out too much or be misaligned with the tank driver's rotation. In my next milestone, I plan to have the robot fully functional (ultrasonic sensors operating and the robot being remote-controlled) so I can integrate modifications easier before demonstration night.

# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 

# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

```c++
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  Serial.println("Hello World!");
}

void loop() {
  // put your main code here, to run repeatedly:

}
```

# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Keyestudio DIY Mini Tank V2.0 Smart Robot car kit for Arduino STEM | What the item is used for | $78.90 | <a href="https://www.keyestudio.com/products/new-keyestudio-diy-mini-tank-v20-smart-robot-car-kit-for-arduino-robot-stem-mixly-blocks-coding-support-ios-ampampandroid-app-1"> Mini Tank Robot V2 </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |

# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Arduino Reference](https://www.arduino.cc/reference/en/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)
