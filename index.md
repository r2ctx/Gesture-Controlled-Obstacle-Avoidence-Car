# Gesture Controlled Robot

<!--- You should comment out all portions of your portfolio that you have not completed yet, as well as any instructions: --> 
<!--- This is an HTML comment in Markdown -->
<!--- Anything between these symbols will not render on the published site -->






| **Engineer** | **School** | **Field of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Ryan Chakravarthy | Amador Valley High School | Cybersecurity | Rising Junior |

<p align="center">
<img src="Untitled design.png" alt="Profile Pic" height="500">
</p>

# Modification 

<iframe width="560" height="315" src="https://www.youtube.com/embed/9k2UJPtmCCA?si=DuoJOoHEpr13QJqq" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

In the video, I worked on getting the base of the car 


# Third Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/7sxZPStkVJo?si=WXr-_IeogFqZ7ExR" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

 *(- created move methods for all directions
 - mapped move methods to Bluetooth Logic
 - UltraSonic Sensors.)
   
 

# Second Milestone


<iframe width="560" height="315" src="https://www.youtube.com/embed/PngfwoImU6A?si=Sr4rgwN2wUguZjp-" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

I built the controller for the car using a half-size soughterless breadboard, with an HC-05 Bluetooth Module, and MPU6050 Axis Accelerametor, and an Arduino Nano. I then wired the GND and 3.3V on the HC-05, as well as the RXD and TXD pins for trasmitting and reciving data to the Arduino Nano. Next, I wired the MPU6050 with 5V and GND on the Arduino Nano, along with the SCL and SDA pins for sycronizing I2C communication with and transferring data between the MPU6050 and the Arduino Nano. Then on the car I wired up the HC-05 much the same, with the RXD and TXD pins plugged into the Arduino Uno. With both Bluetooth Module's correctly wired up, I bonded them using AT Commands setting the controler as the 'master', and the car as the 'slave'. Firstly, I used the 

*(AT Binding with Bluetooth HC-05/ Bluetooth Methods/Serial Monitor) --> Envoke car move method.

<!---
After finding the slave's ip address using 'AT+ADDR=?', I binded 
-->

# First Milestone 

<iframe width="560" height="315" src="https://www.youtube.com/embed/uGJLj3cOeik?si=okMysitVvUACM0zb" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

In building the Gesture Controlled Robot, my first milestone encompassed building the car's base, and wiring up all necessary electrical components (boards) to ensure the car was physically functional. I first began by wiring the IN ports on the H-Bridge controller to digital ports on the Arduino Uno. Next, I connected the motors to the terminals on the H-Bridge Controller (OUT1, OUT2, OUT3, OUT4) in a criss-cross orientation. I then connected 4 AA Batteries to the 12V+ and GND terminals on the H-Bridge, which I also wired up to the VIN and GND ports on the Arduino Uno, thus powering the entire car. Furthermore, I connected the Arduino Uno to my laptop via USB type B and uploaded a C++ program using Arduino IDE. In setup(), I defined the numbered ports on the Arduino UNO by the inputs they were connected to on the H-Bridge (ex. IN1) and defined each port's pintype as an output or input using pinMode(). Then in loop(), I sent a digital signal using digitalWrite() and set the IN ports on the H-Brige controller to a HIGH or LOW signal, correctly distributing voltage between motors enabling them to all turn forward.



# Starter Project

<iframe width="560" height="315" src="https://www.youtube.com/embed/lBnLvlJ5_s4?si=6Fjxz9oYdJ5fjPSC" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

*Today I constructed a calculator through soldering buttons, an MPU (STC Chip), and a CR2032 battery to a motherboard. Originally, when soldering the MPU, I failed to realize that one of its pins did not make it through to the other side of the motherboard, causing the calculator to malfunction when outputting to its display. Fixing the issue was painfully done by re-soldering, and changing the chip's orientation. This was especially confusing as the instructions were unclear on the intended position of the MPU, so I had to troubleshoot by soldering it in multiple orientations until I found one that worked. After fully soldering all the components in the correct orientation, I assembled the motherboard inside its casing using small screws and nuts.



<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My GitHub Pages Site</title>
    <style>
        .code-block {
            overflow-x: auto;
            white-space: pre;
            width: 750px;
            height: 475px;
            max-height: 475px;
            background-color: #1E1E1E; /* Optional: Set background color */
            padding: 5px;
            border: 2px solid #CCCCCC; 
            border-radius: 10px; /* Optional: Rounded corners */
            font-family: Consolas, Monaco, 'Andale Mono', monospace; /* Example font */
            font-size: 14px; /* Example font size */
        }
    </style>
</head>
<body>
    <h1>Code</h1>
    <div class="code-block">
        <pre>
<span style="color:#FFFFFF;"><b>Arduino Uno & H-Bridge (car)</b></span>
            <code> 
<span style="color:#FFFFFF;">
#include &lt;SoftwareSerial.h&gt;
#define TXD 11
#define RXD 10

//defining HC-05 Inputs & Outputs
SoftwareSerial BT_Serial(TXD, RXD);
                
// mapping H-Bridge outputs to ports on Arduino Uno
int ena = 10;
int IN1 = 9;
int IN2 = 8;
int IN3 = 7;
int IN4 = 6;
char z;
                
void setup() {
            
   // Configures bluetooth and serial monitor
   Serial.begin(9600);
   BT_Serial.begin(9600);
                
   // Sets H-Bridge ports as outputs
   pinMode(ena, OUTPUT);
   pinMode(IN1, OUTPUT);
   pinMode(IN2, OUTPUT);
   pinMode(IN3, OUTPUT);
   pinMode(IN4, OUTPUT);
                
}
                
void moveForward() {
    digitalWrite(IN1, HIGH);
    digitalWrite(IN2, LOW);
    digitalWrite(IN3, HIGH);
    digitalWrite(IN4, LOW);
}
                
void moveBackward() {
    digitalWrite(IN1, LOW);
    digitalWrite(IN2, HIGH);
    digitalWrite(IN3, LOW);
    digitalWrite(IN4, HIGH);
}
                
void turnLeft() {          
   digitalWrite(IN1, LOW);
   digitalWrite(IN2, HIGH);
   digitalWrite(IN3, HIGH);
   digitalWrite(IN4, LOW);          
}
                
void turnRight() {
    digitalWrite(IN1, HIGH);
    digitalWrite(IN2, LOW);
    digitalWrite(IN3, LOW);
    digitalWrite(IN4, HIGH);
}
                
void coast() {            
    digitalWrite(IN1, HIGH);
    digitalWrite(IN2, HIGH);
    digitalWrite(IN3, HIGH);
    digitalWrite(IN4, HIGH);      
}
                
void stop() {      
    digitalWrite(IN1, LOW);
    digitalWrite(IN2, LOW);
    digitalWrite(IN3, LOW);
    digitalWrite(IN4, LOW);
}
                
                
void loop() {
    
    // Prints direction from Arduino Nano
    if (BT_Serial.available() > 0) {   
        z = BT_Serial.read();
        Serial.println(z);         
    }
                
    // Correlates input letter to correct move method
    switch(z) {                                         // 'else if' equivalent
        case '^':                                       // 'if' equivalent
            moveForward();
            break;
        case 'v':
            moveBackward();
            break;
        case '<':
            turnLeft();
            break;
        case '>':
            turnRight();
            break;
         case '.':
            stop();
            break;
     }
}
</span>
            </code>
        </pre>
    </div>
</body>
</html>




<!---
 # Final Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

/* For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE */



# Second Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/y3VAmNlER5Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your second milestone, explain what you've worked on since your previous milestone. You can highlight:
- Technical details of what you've accomplished and how they contribute to the final goal
- What has been surprising about the project so far
- Previous challenges you faced that you overcame
- What needs to be completed before your final milestone 

# First Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/CaCazFBhYKs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your first milestone, describe what your project is and how you plan to build it. You can include:
- An explanation about the different components of your project and how they will all integrate together
- Technical progress you've made so far
- Challenges you're facing and solving in your future milestones
- What your plan is to complete your project

# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 

# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

-->

&nbsp;

# Components
<!---
| **Component** | **Price** | **Usecase** |
|:--:|:--:|:--:|
-->

| [Arduino Uno](https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/ref=sr_1_1_sspa?crid=1V4XJ1JOA8UQQ&dib=eyJ2IjoiMSJ9.MazmhFfn-DF8W5oyX_S-tH7qkt_WuogERq_8M3-FTf6ou9kOBA5zItAmHHSDNak0z60nUJ-2lw_MGDugGZSVnD2v64TGllCLNOhouT8ifL9mqHfaVwIJIJDDQRs9U9Q6GI0IKsWWvjHtrn6FGgfvF9HdxFHV5n3_NF-uCB2HVDhXEWZqayzOWTsLbOGt6RRNKYHL0p2PgFGimKSbp3PUgKIHsKG_3F9sPSdbEpm_Qt0.sGetorRX1BiMIfXBXxhwWw8uqP5AKgpqNDL0tv2u7MA&dib_tag=se&keywords=Arduino%2BUno&qid=1718558645&sprefix=arduino%2Buno%2Caps%2C134&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1) | $29.00 | controls H-Bride, motors, and HC-05 bluetooth module|
| [Arduino Nano](https://www.amazon.com/Arduino-A000005-ARDUINO-Nano/dp/B0097AU5OU/ref=sr_1_3?crid=3BTE9ZUKPU3KP&dib=eyJ2IjoiMSJ9.DuUAPNKOZx3V-ph33HzyN07Qbfpikx59bB5Qb_BiE51Vy1oguSeb8nkrcN01TQfzpxFOYkQ0osRbYSjo9mQNZ7d5f0y7HI4UOISCA6T17bofs3LnIUpj9F7gDS46r_NB804pwBNPk6KRC_QzGR63NP7N5Mv90TpOVGxTGC0CiX3HHv0L7tZndIwZ-NfyOc_kh3hcxJrGc3GcJt9puPfsJJWWbQb8dPX10zdkVEqAGgc.M1h1yLu1Q_7DRs-q3gXAiHxcTtquvqS-AqZYDMUNnVU&dib_tag=se&keywords=Arduino+Nano+R3&qid=1718558821&sprefix=%2Caps%2C162&sr=8-3) | $25.10 | controls IMU and HC-05 Bluetooth Module |
| [MPU6050 Axis Accelerometer](https://www.amazon.com/HiLetgo-MPU-6050-Accelerometer-Gyroscope-Converter/dp/B01DK83ZYQ?th=1) | $6.49 | detects orientation on hand |
| [H-Bridge Motor Driver](https://www.amazon.com/Qunqi-Controller-Module-Stepper-Arduino/dp/B014KMHSW6/ref=sr_1_11?crid=2I0MTAM87KGBX&dib=eyJ2IjoiMSJ9.Uhkp4V4YuMhSQCL0zp7DOagThE52qqHMItNDAg9kPKfS4JZ9iDUMvFsuc8egCwssjf00Nmxfxyw1COwlCLaQO840s3u0MaRBK3dW2mzeK09EtH_Y6zQjFbiVMiOR6CHMCZjxxXZ93QCSlXUL73DVt-llACkd2PQLRex8Ilpvbo-uW9XVpxyUhoUjUku5xPG6l9lMxXcA6tiq8r88g1YatfNdJhbmEijZns6wV6XbD0s.rbLGWtWTbYHXjq5M3tghJa95-S8XEcPOLrrsclhVZAs&dib_tag=se&keywords=SparkFun+Dual+H-Bridge+motor+drivers+L298&qid=1718559198&sprefix=sparkfun+dual+h-bridge+motor+drivers+l298%2Caps%2C149&sr=8-11) | $6.99 | direct module for motors
| [HC-05 Bluetooth Module (2x)](https://www.amazon.com/DSD-TECH-HC-05-Pass-through-Communication/dp/B01G9KSAF6/ref=sr_1_1_sspa?crid=1Y1E63CI5V330&dib=eyJ2IjoiMSJ9.GVe7xTdQBd8ycP5WU8ZbiWWV7BFUDNGSUph0cXQjue5IrNCfv4w86s2ZhriTU5-OJz9Pb0U9ADpSaqeNpsiD3YWnwTvHbZ-nmvkVzV1bVFyk64Dg5oueYfxrOWrP8zL237YIXI3A_vZyDl57bAsJcmuQWrwh402QjpOFOgKKGrcnMTSl7FMdpn_hK2quExKVMAe-UtAj7AdCZZqAxmq9-Gn34ulNeCWXSaLgzC3rhIU.OQX71neyKQAbgDKW9kMG-jZL3uzOYHLkpEbLZs_Mp40&dib_tag=se&keywords=HC-05+Bluetooth+Module&qid=1718559342&sprefix=%2Caps%2C196&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1) | $9.99 | signals between Arduino Uno and Nano |
| [Joyick for Arduino](https://www.amazon.com/Teyleten-Robot-Dual-axis-Controller-Raspberry/dp/B0CPFDKWZF/ref=sr_1_1?crid=2721KLBYAXK0G&dib=eyJ2IjoiMSJ9.6zfYPy2SA893_1p8cYE-sIZkQ1viGapkKtMLPZjCAjQ8vES9HHRSoqsmhSHrlRjIxPp7B0cXty-XvziLGNDGuTC0Fn9cXxn1q0tp-5Mhxln_x6R4on7tz44M6RAKrVhjH985Q1YehejohUhNxtX_z8ILEXmCS-10-0kHjKWuVoic1SF2XzAJmXbP13rGMxsrEV-ak1WZ-TB6jeQibC_BwLMPHEcjLvbfsJ5RxVeYBkk.eTPb36RxXUA1hGNGLGKPh-fwYLmvGOpG0BYJ02620KM&dib_tag=se&keywords=joystick+arduino&qid=1720730419&sprefix=joystick+arduion%2Caps%2C181&sr=8-1) |
$9.88 | joystick control of car |
| [Solderless Breadboard - Half Size](https://www.amazon.com/Qunqi-point-Experiment-Breadboard-5-5%C3%978-2%C3%970-85cm/dp/B0135IQ0ZC/ref=sr_1_10?crid=2IFADSYVTFSVX&dib=eyJ2IjoiMSJ9.6TgbxdjPWRSoIqeLPap38EFx3ylBBBq0oRRvqZun2nf8c3J3kqDvsLTAJg4mQJN2DQZnEKh5siy8fssIDqPXNdpG5iO8d05mNWQUdDEZAx3ArbHIhLAPaw2x8QE9h1pI50A1gx2gl3B3qYnDo4T9pv_8-ZnEGkM-87OYIH27RYRtQogcM-AC6zdLS8mSiSHexrUziQCayzAuFUR-TuQUXJZjBxgEqYIeZrcKNhsib9d6g9KG4Ge5IyX9gM-qL-Ub9000ifuf9cln8U8036s9hp9aW8xkCtbaPQP1Vu48NDU.ezzkxHOsO-XwLrOKP1Ni3N_tf2aG_6UTv4p0BnSGIP0&dib_tag=se&keywords=half-size+bread+board&qid=1720893952&sprefix=half-size+bread+boar%2Caps%2C149&sr=8-10) | $5.98 | base for glove components |
| [Motors + Wheels + Base](https://www.amazon.com/MakerFocus-Chassis-MEGA2560-MEGA1280-Microcontroller/dp/B01LYZDP9U) | $19.99 | motors, wheels, and car base|
| [Set of Male/Female Wires](https://www.amazon.com/ZYAMY-120PCS-Connector-Multicolor-Breadboard/dp/B0742RS6YL/ref=sr_1_1?crid=21S67LIQJEWBY&dib=eyJ2IjoiMSJ9.6XXe8GsCSvJz4ezKFLOnW-HQzxR-V2K194UJ-mxTqdj2IQK47UrDg8c5hx-iURTM9tfb-yR55yjIX6FyOV6Saz018AALKek67BQYE3IK9KJ8q6-NQwRGilZG4sddccCYQFdpqwOt-IVS3K3dydlE9S00nuo_koy2p2SQl26k3I7IbRyj0UWL_oZYWHrktBL8LTzAOfq3pEvmB2pp1X7IsfGmUFvCkkZKpyMc0ZsverIYJtFwqGgb4am0GYW-JimuUnvqxIHt9IXO1QVmJVCmcYnpT7G5EiDEoOSseFkmRis.Q-IH9PSHqskX_Ygs1CwrJdzY-PRUXOPF3_y1eRq3ppw&dib_tag=se&keywords=set+of+male-male%2C+male-female%2C+and+female-female+wires+short&qid=1719345645&s=industrial&sprefix=set+of+male-male%2C+male-female%2C+and+female-female+wires+sho%2Cindustrial%2C125&sr=1-1) | $7.39 | for wiring all components |
| [Ultrasonic Sensor(s)](https://www.amazon.com/WWZMDiB-HC-SR04-Ultrasonic-Distance-Measuring/dp/B0B1MJJLJP/ref=sr_1_5?crid=9ZJP8VRZSJFF&dib=eyJ2IjoiMSJ9.hxKSGnm38uFYPbLd-yrIsGKtiigcjiHBIR4HeBGiJvRLTXVkrQVm2-2X9h0DX4IGZYcDIy5GlwZ6-_r_mPVsFAWYOWj4DIl5qoKw5z9-69Yu_s0Iod1JUacucsC7zRfGCgBi6MWbRNOOrfNnCJls21sZ5X92RuBO0Mdgc9F1zcVC3jLL--a2XxVReiEoJ0M9A2H0lylYhk3uxuJ2ve1swutQGgGFlIVTbD0YsDVd3Ro.uaMr3MvshBPzwS6EHg3CTlKfFCI2Ru2EEpGKw5yudtA&dib_tag=se&keywords=ultrasonic%2Bsensors&qid=1720730628&sprefix=ultrasonic%2Bsensor%2Caps%2C135&sr=8-5&th=1) | $6.99 | object detection |
| [Set of 9V Batteries](https://www.amazon.com/AmazonBasics-Volt-Everyday-Alkaline-Battery/dp/B081FGCRQQ/ref=sr_1_15?dib=eyJ2IjoiMSJ9.LzVLI_Okv1aX44UDnl3M2wmckTFUx_wn4DFEVq1jt6YlixM49-Dq2GivmKD_qLibdVrEYkwQ74PpweLVb6f2Xr2GWLnFspellT-4_hm4FkLx56zpk7QSCtV-Fr9e6D7FQ1n4j4gJPO-Fb0reQDnu-6ViykwxP4FhbfvKNscLOV2GoBnbhaMoWehGGJuywcp-b2co2zi7lsxd24VsHs2gbmAGbIlv0pBE8vsc2MBGj9y8HKhzkRJVl5Et1Gx-9WtfvBQjazPVUK1ZE6DdXSfam88xlshMOfFU5XPv0IBAxgI.RZD4uSFrxVaVkImhVBpiNDLvRXCt1TmHMf5dHMxwNgU&dib_tag=se&keywords=Set+of+9V+Batteries&qid=1719345894&sr=8-15) | $10.99 | power delivery  via H-Bride 12V+ and GND |
| [*On/Off Rocker Switch](https://www.amazon.com/5Pcs-Rocker-Switch-Position-QTEATAK/dp/B07Y1GDRQG/ref=sr_1_6?crid=784YWU3U28U4&dib=eyJ2IjoiMSJ9.1fYIrtWoaUU8xQPki0E5sT2OfE4-ax56S4xw1AsDXmeTIsVCMEIi4_g188cCbXwpZoBib8H8wszaEjj17ScudtUZdYqCpNk57H1LPajCaJCa0VQgT_CPHr7vVDKtWzkFx90KD6wtyA94BXBbokSvMTEIW616yi-ls65Pw6coKq940gHlF_bdeBDCaR_V5AvTcALSpXFEbAp_O5yF4f1PHU2-FqlqAa7s_RYU7YUI2tQ.lFgIkO4RTLgCELY6sZbl7zhuJ79C9JduWUhVAvC2cCA&dib_tag=se&keywords=rocker+switch&qid=1718562620&sprefix=rcoker+switch+%2Caps%2C145&sr=8-6) | $6.99 | *optional* power button |
| [Micro USB Cable](https://www.amazon.com/Braided-Charging-Compatible-Controller-Microphone/dp/B0B3J6RD34/ref=sr_1_14?crid=2YQBYUGH259IQ&dib=eyJ2IjoiMSJ9.f9NYn_Pp6FspnGAravIPXUZauuNB4JTty_d5vJncfcvd069SnYXXAY9fL_mMSZUusQlly-ID6lafuF6Af--hmTLMYbS6LYDkMA_x8tbuLNVaMDUeBErzQbQdoWhPhzcxzbS4Rjq_4iOm_sUzyH3jA6c9UpHFhOmW6G1y2Mv_CqtiUCPSnqirp0HtTDsSnuRYsnJZuLx8SWnyKQW2JzLgk7tVjBaSbxEmX7-zZ9BjH2Y.-UC7-3So9eFHBK-wXy_0XJyRGeaCNyfe-O9aQIq--yY&dib_tag=se&keywords=USB+B+to+A+and+mini+USB+to+A+bundle&qid=1720893654&sprefix=usb+b+to+a+and+mini+usb+to+a+bundle%2Caps%2C143&sr=8-14) | $4.99 | connect Arduino Nano to Computer |
| [USB Type B](https://www.amazon.com/Monoprice-6-Feet-24AWG-Plated-105438/dp/B003BXPQF2/ref=sr_1_8?crid=2YUWBTC59H9Z5&dib=eyJ2IjoiMSJ9.hCC1scuHFhmHD3CfyTe_zLUECEvKqGhh9tXOxP0XsrFyfKOw1Si4xoF5FdOEEPZ6shBCewBfdqtfkicwyangDoHa5-4548AduMsw-Xw_HXdEIWvDT2g9hjc9c0YUgWiaK5U6KzcYuH3RmdEaNSPn675SPUd1iLlwqx1cFVEjJE-QVs-nvN70x6TElmgkWdIO48kJjATvYM4tpQHLl_rpiE05o_BRIm2O4w_OMngOP78.gz8eJIIGjAvfE2MfE0SQf4vDTUvhvhvLxsJtBHzGmqY&dib_tag=se&keywords=USB+B+to+A&qid=1720893787&sprefix=usb+b+to+a+and+mini+usb+to+a+bundle%2Caps%2C167&sr=8-8) | $3.89 | connect Arduino Uno to computer |




<!---
# Referenced Resources
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.
-->

