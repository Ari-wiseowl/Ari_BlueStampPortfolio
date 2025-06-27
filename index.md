# Three Joint Robotic Arm
//KSIIBIIDI

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Ari S | The Harker School | Computer Science | Incoming Eighth Grader

# Main Project Picture:
![Headstone Image](mainProjectPictures(1).png)

# Final Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

## Description
To make sure that the joystick accually controls the robot arm, I had to make code. I coded my code per joystick. I coded the left joystick first, which controls motor of the base and the second joint. I coded it so that if I turn the joystick left and right it twists the base left and right, and if I turn the joystick up and down, the second joint bends down and up. Then I coded the right joystick which controls thrid joint and the claw. The left and right movements control the claw and the up and down movements control the third joint. First I had problems connecting my computer to my arduino nano board, so I had to replace the USB-A TO USB-C adapter becuase it was not working.

## Challenges
I had trouble connecting my arduino nano to my computer becuase my computer kept on disconnecting from the port. First I changed out my wire connecting my arduino and my computer, but that did not change anything. Then, I changed out the adapter, and it suddently started connecting. Therefore, I was able to implement my code to the arduino so that I could control the robotic arm using the joystick.

After I completed my first revision of my code, the robot could not move left or down if the clamp has already been closed. To fix that I had to switch up the direction of the clamp so that instead of the right movement closing the clamp, the left movement closes it. After that revision was implemented, the robot could move seamlessly without any problems.

## Next Steps
**Modifications**
- Make the Robot Dance with the Joystick button
- I also want to control it with my computer (if I type "Dance" on the terminal, the robot starts dancing)
- Add googly eyes on the claw so that it the eyes get wider apart when the claw opens.

# Second Milestone: Building the Robotic Arm

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/uqtCaf1NxMw?si=jvoUUuXZFAiw9Wqr" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Description
To complete my second milestone, finishing building the robotic arm, I started assemhling the body of the robotic arm. I assembled the base of the arm which includes the battery and the nano shield. I switched out the Lithium Ion batteries to AA batteries. Therefore, I had to tape it on to the base since there was no dedicated spot.

I had to write all of the servos to 90° so that all of the servos would turn to the correct direction when I implemented the main code for the entire robot arm. I had to set all of them to 90° so the servos turn to the correct direction when I move the joystick. At first, I did not know how to calibrate all my servos to 90°, but then I found code from the portfolio of Cokoino, the maker of the Three-Joint Robotic Arm kit. Since I forgot to set my base servo to 90° before I implemented it in my robot arm, so I had to take many parts off to fix the issue.

While I was assembling the second joint of the robotic arm, two pieces broke off while I assembling them because I screwed on the servo screws too tightly. First, we tried to dimension the broken pieces so that we could 3D print a new piece. Luckily, we were able to find replacement parts and I could complete assembling the rest of the arm.

### Writing to 90° Code:
```
#include<Servo.h>
Servo myservo1;  // Create a servo class
Servo myservo2;  // Create a servo class
Servo myservo3;  // Create a servo class
Servo myservo4;  // Create a servo class

void setup() {  
myservo1.attach(4);  //Set the servo control pin as D4
myservo2.attach(5);  //Set the servo control pin as D5
myservo3.attach(6);  //Set the servo control pin as D6
myservo4.attach(7);  //Set the servo control pin as D7
delay(100);          //delay 100ms 
}

void loop() {
 myservo1.write(90);  //The servo is 90 degrees
 myservo2.write(90);  //The servo is 90 degrees
 myservo3.write(90);  //The servo is 90 degrees
 myservo4.write(90);  //The servo is 90 degrees
 delay(1000);
 }
```

## Challenges
While I was implementing the second joint of my robotic arm, two pieces that hold the entirety of the arm broke while I was attaching a servo on. Initially, I tried to fix it by superglueing it on, but the superglue did not dry as fast as I wanted it to and left bumpy white streaks all over the plastic pieces. Then, I realized that I would have to print the parts in order for me to finsh my project. I tried to look for online measurements so I could 3D print the part, but there seemed to not be any detailed measurements. So, I decided to measure them myself. I could not find an electrical caliber, so I tried to use a manual caliber to get measurements so I could 3D print a piece using Autodesk Fusion 360. Fortunately, I was able to find replacement parts from another kit and I could complete assembling the rest of the arm.

## New Steps
For my next milestone, I will have to code the robotic arm so that the joystick can control the arm's movements.


# First Milestone: Testing the Servos

<iframe width="560" height="315" src="https://www.youtube.com/embed/4fMHdtYCE2Y?si=LOW1Mc4TG0xlK4kw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Description
For my main project at Bluestamp, I chose to do the Three-Joint Robotic Arm. I chose it because it seemed an interesting way to show what I will learn here at Bluestamp. To test the servos, I needed to download this code called "Sweep," which makes the servo's arm move left and right in a sweeping motion, just as the name suggests. To download it on my computer, I went to File, then clicked on the Servo code to get code that makes the servo arm sweep. Proper assembly at this stage is essential for the robot arm to follow controller commands accurately. 

The next step was to test the joystick by using the Cokoino joystick test code. The code reads what the joystick outputs (x, y and z values). For my left joystick, GND, 5V were connected to A0. The VRx pin was connected to the signal pin A0. The VRy pin was connected to the signal pin A1. The variable orientations of the joystick correspond to different voltages that get sent to the ADC pins on the NANO and get converted to digital values that I can see. If the values for x and y changes when someone moves the joystick, that means that the joystick is working properly. 

### Sweep Code:
```
#include <Servo.h>

Servo myservo;  // create Servo object to control a servo
// twelve Servo objects can be created on most boards

int pos = 0;    // variable to store the servo position

void setup() {
  myservo.attach(10);  // attaches the servo on pin 9 to the Servo object
}

void loop() {
  for (pos = 0; pos <= 180; pos += 1) { // goes from 0 degrees to 180 degrees
    // in steps of 1 degree
    myservo.write(pos);              // tell servo to go to position in variable 'pos'
    delay(15);                       // waits 15 ms for the servo to reach the position
  }
  for (pos = 180; pos >= 0; pos -= 1) { // goes from 180 degrees to 0 degrees
    myservo.write(pos);              // tell servo to go to position in variable 'pos'
    delay(15);                       // waits 15 ms for the servo to reach the position
  }
}
```

## Challenges
Because my code could not find the right port for the Arduino app to connect to, I had to restart my computer. Then, my computer could find the non-Bluetooth port that I can successfully use.

## New Steps
For my next milestone, I will finish building my 3-joint robotic arm. To complete my entire project, I will also have to make code for the arm to actually move.

# Starter Project Picture:
![Headstone Image](starter_project_ari.png)
  
# Starter Project Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/1MOVeSZ_zO0?si=YhtbP7l8hZccBY3d" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Description
For my starter project at Bluestamp, I chose the RGB color sliders. Before my experience at Bluestamp, I had never worked with circuits, so I chose the RGB color sliders to learn about circuits and soldering irons. I thought it would be a good idea to familiarize myself with circuits and Arduinos because my final project uses them as well. For my RGB color sliders, I soldered the pieces on using a soldering iron. The way it works is that if you push one of the red, green, and blue sliders, it sends a signal to the LED, resulting in the color of the light changing. Each of the sliders has a small resistor near it to prevent the circuit from short-circuiting.

## Challenges
When I finished soldering everything on my circuit, it was time to start testing my project. Unfortunately, none of the sliders worked, and the LED did not light up. Eventually, I did a multimeter connectivity test to see if all my soldering was perfect. When all of the connections made a buzz, it was then evident that I did not position the LED in the correct orientation. Then, I tried to desolder the joints, but without any luck. I had to redo the entire project, but, fortunately, the second time I made the RGB color sliders, they were fully functional.

## Next Steps
Now that this project is completed, I have a better understanding of circuits, soldering, and LEDs.

# Schematics 
## Testing Servos Schematics:
![Headstone Image](circuit_image.svg)
## Robotic Arm Schematics:
![Headstone Image](RobticArmSchematics.png)
  

# Code

```
#include <Servo.h>

int basecurpos = 90;
int joint2curpos = 90;
int joint3curpos = 90;
int clawcurpos = 90;
Servo baseservo4;
Servo joint25;
Servo joint36;
Servo claw7;
//int curpos; I don't think this does anything but just to make sure im commenting it out
int countl = 0;

void setup() { 
  baseservo4.attach(4);
  joint25.attach(5); 
  joint36.attach(6);
  claw7.attach(7);
} 

void dance() {
  baseservo4.write(90); //set all the motors to the origional position so it is easier to move the robotic arm
  joint25.write(90); //this is not affected if the button is pressed to make it stop or not
  joint36.write(90);
  claw7.write(90)
  
  if (countl % 2 == 1) {
    for (int i = 90) {
      //ddd
    }
    baseservo4.write(90);
    countl++;
  }
}

void loop(){
  baseservo4.write(basecurpos);
  joint25.write(joint2curpos);
  joint36.write(joint3curpos);
  claw7.write(clawcurpos);

  //left joystick
    int xlvalue = 0; 
    int ylvalue = 0;
    xlvalue = analogRead(A0);  
    Serial.println(xlvalue);
    ylvalue = analogRead(A1);
    Serial.println(ylvalue);
    pushlvalue = analogRead(11)
    //base 
    if (ylvalue == 0) {
      baseservo4.write(basecurpos - 5);
      basecurpos -= 5;
    } 
    if (ylvalue == 1023) {
      baseservo4.write(basecurpos + 5);
      basecurpos += 5;
    }

    //joint 2
    if (xlvalue == 0) {
      joint25.write(joint2curpos - 5);
      joint2curpos -= 5;
    } 
    if (xlvalue == 1023) {
      joint25.write(joint2curpos + 5);
      joint2curpos += 5;
    }

  //right joystick
    int xrvalue = 0; 
    int yrvalue = 0;
    xrvalue = analogRead(A2);  
    yrvalue = analogRead(A3);
    pushrvalue = analogRead(10)
    //base 
    if (yrvalue == 0) {
      claw7.write(clawcurpos + 5);
      clawcurpos += 5;
    } 
    if (yrvalue == 1023) {
      claw7.write(clawcurpos - 5);
      clawcurpos -= 5;
    }

    //joint 2
    if (xrvalue == 0) {
      joint36.write(joint3curpos + 5);
      joint3curpos += 5;
    } 
    if (xrvalue == 1023) {
      joint36.write(joint3curpos - 5);
      joint3curpos -= 5;
    }
  
  delay(15); 
}

```

# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |

# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.
