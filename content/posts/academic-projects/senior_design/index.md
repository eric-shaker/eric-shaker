---
title: "Bioengineering Senior Design: Developing A Feedback-Oriented Trainer for Reducing Shoulder Subluxations "
date: 2022--4-28T08:06:25+06:00
description: A culminatory bioengineering senior design project. 
menu:
  sidebar:
    name: Bioengineering Senior Design
    identifier: Senior Design
    parent: academic-projects
    weight: 2
hero: gif_senior_design.gif
tags: ["Markdown","Content Organization","Multi-lingual"]
categories: ["Basic"]
---
As part of the University of Pittsburgh's Bioengineering Department, I partook in a culminatory senior design project that was aimed at conducting as many parts of the medical design process as possible. Below will be an outline of primarily my personal contributions, but also the position of the work in the grander scheme surrounding the issue we tackled. The sidebar on the right can be used to navigate across the sections.

This portfolio page has been divided into three sections depending on the interests of the reader. Project related background and ideation efforts will be grouped first, project engineering will be a second category, and the last will be regulatory considerations, risk and hazard analysis, and other insights from the rest of the medical design process.

I would like to thank Dr.Mark Gartner for instructing the class and providing grounded guidance. I also would like to thank Dr.Iovine, Dr.Potts, and Dr.Richard Debski for considerable contribution to our project in the form of mentorship. Lastly, this project could not be done without my six other groupmates. Young Kim, Jeremy Remeinschneider, Karthik Iyer, Yu-Hsuan Chao, Natalie Danielsen and Molly Bevenour and I have spent an ungodly amount of time together from this project, and my respect has only grown. 

## Project Choice, Background and Ethnography 
#### Ethnography
Before delving into a project, my team and I identified areas of unmet clinical need. 

We then broke apart those large areas in ethnographic plans. Ethnography is based on cultural anthropology and entails understanding a group through various means. I conducted ethnography on the issues pertaining to emergency medical service providers, issues with pervasive eye strain, and measuring metrics prognostic of longevity. Ethnography is composed of ethnographic plans that will be carried out and essentially specify who you will talk to, when you will talk to them, what questions will you ask and lays down a protocol for how to go about gathering real-world information. This is complemented by other forms of ethnography that include immersing yourself in the environment, observing a population in a certain environment, or conducting a certain task yourself.  

The FDA cites ethnography, and research related to what a user needs as the first step in the medical design process.

Due to my background in EMS, I spoke to ~30 people over the phone from my old squad, gathering information about common issues. I spoke to local heads of EMS crews from contacts in Pittsburgh. I consulted with my PI and others in my lab about the sources of pervasive eye strain and mitigation strategies, and underwent plans to speak to geriatricians, endocrinologists and another physician who was specialized in longevity medicine. Below is an image of section of our ethnography plan including a protocol.

{{< img src="/posts/academic-projects/senior_design/ethno.png" align="center" title="EMS Based Ethnography Plan">}}

After amalgamating all the data gathered, my team and I decided that we would focus only on solutions issues afflicting patients with Ehler's Danlos syndrome. 

#### Background

Ehler's Danlos Syndrome is a collagen deficiency disorder that exists in a variety of forms. One of the most prevalent is hypermobile Ehler's Danlos syndrome. Patients with this condition have a propensity to dislocate joints from lack of collagen, a vital component in the ligaments that bind muscle to bone. As such, they undergo frequent struggles in everyday life, dislocating hips while walking, shoulders while carrying their child, wrists when doing basic movements that many would take for granted. 

Physical therapy is the main form of remediation for this condition. However, EDS is a rare disease disorder, affecting <200,000 people nationally. As such, physical therapists are often unfamiliar with the proper ways to treat these patients and often end up performing inadequate interventions, or harming the patients themselves. The lack of education is so prevalent that most patients we've spoken to report having to educate their own physical therapists on their condition and its implications. 

The shoulder subluxation presents a particular challenge as it is a point of frequent dislocation that often is treated by a physical therapist. It impedes normal shoulder function, and, alongside the hip, is a pervasive issue in hEDS patients. 

#### Project Ideation

Two avenues were narrowed down to be pursued for a project area: one which improved medical education and awareness around EDS, and another which would directly reduce (relocate) the subluxation. 

Although we conducted an analysis  (reproduced below) in which we decided that developing a reduction device was a more preferable image, due to the scope of the classs and liability incurred with doing human-subjects based testing on a medical device, we chose to develop a shoulder trainer. 

{{< img src="/posts/academic-projects/senior_design/project_analysis.png" align="center" title="Project Area Analysis">}}


## Project Engineering

#### Iteration 1 
The first iteration was simply a proof of concept that could be engineered quickly, and get as much essential functionality working as possible with limited effort. It is for feedback purposes, and prototpying quickly like this can make obvious several issues that are difficult to conceptualize without a physical model. I personally contributed to the design of the product, and made the ball and socket joint out of a golf ball and a cut up tennis ball respectively. Final assembly was largely done by my peers. 

{{< img src="/posts/academic-projects/senior_design/IMG_9334.jpg" align="center" title="First Iteration Prototype">}}

#### Iteration 2
I fully conceptualized and developed iteration 2. A mannequin was purchased for the base. A labrum (the socket joint) was made through cutting into the mannequin, hollowing out a section equivalent to the labrum dimensions and filling that in with sanded down tennis ball (to reduction friction). 
###### Muscle Fibers 
Afterwards, a 3D printed humerus was attached with pliable fishing line to mimic musclular connections. I studied the muscle insertions for a couple hours before attachment to ensure that the lines of action of the muscle fibers would be physiologically similar. The four rotator cuff muscles, namely the subscapularis, the supraspinatus, the infraspinatus and the teres minor were the significant muscle groups identified. The differing sizes of the muscles neccesitated that I used different amounts of fishing line depending on the muscle I was mimicking. Therefore, I fanned out 5 lines for the subscapularis, 3 lines for the supraspinatus, 7 lines for the infraspinatus and 2 lines for the teres minor. These choices were made off of educated guesswork, and many insertion schematics (pictured below). Once glued down with epoxy resin, I fanned out the action of each of these muscle fibers in shapes that best mimicked the physiology to my capabilities. One the other end, these fibers, representing 4 muscle groups, were threaded into a guitar tuner. The guitar tuner was capable of adjusting the tension of each muscle (and thereby each ligament) in order to mimic real-world conditions. The tuners were mounted on a wood piece.


{{< img src="/posts/academic-projects/senior_design/Drilling.jpg" align="center" title="Drilling Mounts for Prototype 2 Guitar Tuners">}}


{{< youtube ZmV1ec9U3ZA >}}

{{< vs >}}

#### Third Iteration 
The feature set for iteration 3 was greatly expanded. It can be broken down into a subset of component:

* Component that can sense whether the center of the humerus is touching the labrum. If so, an LED and an auditory signal will be produced
* Component that can sense the orientation of the humerus in space. This would be later accompanied by a statistical test that can measure whether the movements produced by a user are statistically similar to the ones performed by a trained physical therapist 
* Component that can alter the elasticity of the ligaments controlling the four major muscle groups of the rotator cuff. This component will be how the differences between the EDS and the non-EDS patient state will be produced. This component will also be responsible for producing a subluxation that is to be fixed by the user
* Emotional component that plays a prompt and brief instructions prior to user usage of the device. Future direction mainly
* Physical compartment that houses the electronics, and mimics the physiological, shape, structure, size, and weight of a typical EDS patient

I personally developed the servo component that allows for the variable ligament/muscle fiber tension, and which produces a subluxation. I also contributed to the production of the physical housing through helping design the humerus itself. Lastly, I also personally wrote code to revamp our electrical sensing system. 

###### Servo Motor
I pushed for, designed, and developed the circuit below such that we would be able to induce a subluxed state, as well as modelling different patient archetypes within one device. Stepper motors were chosen over servo due to their excellent holding torque (through testing, I determined that we wanted at least a holding torque of 30N such that the model would withstand significant forces applied to the humerus). The TMC2208 driver from Trinamaric was chosen, and has been represented by a 16 input IC below.

{{< img src="/posts/academic-projects/senior_design/circuit1.png" align="center" title="Stepper Circuit Diagram">}}

Once wired upon, the above system was done 4 times, so each muscle group had a different stepper motor that could be actuated to elicit different tensions. 

After confirmation that the system worked, I implemented an ON-OFF switch for easy transition of states.


{{< youtube _V3LPuNmDWw >}}

{{< vs >}}

From there, the motors had to be all programmed to do different actions. The code is below 



```

#define STEP_PIN_1 2
#define DIR_PIN_1 3 //direction
#define STEP_PIN_2 4
#define DIR_PIN_2 5
#define STEP_PIN_3 6
#define DIR_PIN_3 7
#define STEP_PIN_4 8
#define DIR_PIN_4 9
#define MS1_PIN 11
#define MS2_PIN 12
#define EN_PIN 13 //enable (CFG6)
#define MOVE_LEFT_1 'w'
#define MOVE_RIGHT_1 'e'
#define MOVE_LEFT_2 'r'
#define MOVE_RIGHT_2 't'
#define MOVE_LEFT_3 'y'
#define MOVE_RIGHT_3 'u'
#define MOVE_LEFT_4 'i'
#define MOVE_RIGHT_4 'o'


void setup()
{
  //set pin modes
  Serial.begin(9600);
  pinMode(EN_PIN, OUTPUT);
  digitalWrite(EN_PIN, HIGH); //deactivate driver (LOW active)
  
  pinMode(DIR_PIN_1, OUTPUT);   pinMode(DIR_PIN_2, OUTPUT);  pinMode(DIR_PIN_3, OUTPUT);  pinMode(DIR_PIN_4, OUTPUT);

  //digitalWrite(DIR_PIN_1, LOW); //LOW to CCW
  digitalWrite(DIR_PIN_1, HIGH); digitalWrite(DIR_PIN_2, HIGH); digitalWrite(DIR_PIN_4, HIGH); digitalWrite(DIR_PIN_4, HIGH); 
  //HIGH to CW
  
  pinMode(STEP_PIN_1, OUTPUT);  pinMode(STEP_PIN_2, OUTPUT);  pinMode(STEP_PIN_3, OUTPUT);  pinMode(STEP_PIN_4, OUTPUT);

  digitalWrite(STEP_PIN_1, LOW);  digitalWrite(STEP_PIN_2, LOW);  digitalWrite(STEP_PIN_3, LOW);  digitalWrite(STEP_PIN_4, LOW);

  pinMode(MS1_PIN, OUTPUT);
  pinMode(MS2_PIN, OUTPUT);

  digitalWrite(MS1_PIN, HIGH); digitalWrite(MS2_PIN, LOW);
  digitalWrite(EN_PIN, LOW); //activate driver
  Serial.println(EN_PIN);

}

void loop()
{
  char byte = 0; 
  Serial.readBytes(&byte, 1); 
  switch(byte){
  case MOVE_LEFT_1:
  for(int i = 0; i < 100; i ++){
    digitalWrite(DIR_PIN_1, HIGH); digitalWrite(STEP_PIN_1, HIGH); delay(1); digitalWrite(STEP_PIN_1, LOW); delay(1); Serial.println("SUBSCAPULARIS COUNTERCLOCKWISE TIGHTENING");
  }
  break;
  case MOVE_RIGHT_1:
  for(int i = 0; i < 100; i ++){
    digitalWrite(DIR_PIN_1, LOW); digitalWrite(STEP_PIN_1, HIGH); delay(1); digitalWrite(STEP_PIN_1, LOW); delay(1); Serial.println("SUBSCAPULARIS CLOCKWISE LOOSENING");
  }
  break;
  case MOVE_LEFT_2:
  for(int i = 0; i < 100; i ++){
    digitalWrite(DIR_PIN_2, HIGH); digitalWrite(STEP_PIN_2, HIGH); delay(1); digitalWrite(STEP_PIN_2, LOW); delay(1); Serial.println("INFRASPINATUS COUNTERCLOKWISE TIGHTENING");
  }
  break;
  case MOVE_RIGHT_2:
  for(int i = 0; i < 100; i ++){
    digitalWrite(DIR_PIN_2, LOW); digitalWrite(STEP_PIN_2, HIGH); delay(1); digitalWrite(STEP_PIN_2, LOW); delay(1); Serial.println("INFRASPINATUS CLOCKWISE LOOSENING");
  }
  break;
  case MOVE_LEFT_3:
  for(int i = 0; i < 100; i ++){
    digitalWrite(DIR_PIN_3, HIGH); digitalWrite(STEP_PIN_3, HIGH); delay(1); digitalWrite(STEP_PIN_3, LOW); delay(1);  Serial.println("TERES MINOR COUTNERCLOCKWISE TIGHTENING");
  }
  break;
  case MOVE_RIGHT_3:
  for(int i = 0; i < 100; i ++){
    digitalWrite(DIR_PIN_3, LOW); digitalWrite(STEP_PIN_3, HIGH); delay(1); digitalWrite(STEP_PIN_3, LOW); delay(1);  Serial.println("TERES MINOR CLOCKWISE LOOSENING");
  }
  break;
  case MOVE_LEFT_4:
  for(int i = 0; i < 100; i ++){
    digitalWrite(DIR_PIN_4, HIGH); digitalWrite(STEP_PIN_4, HIGH); delay(1); digitalWrite(STEP_PIN_4, LOW); delay(1); Serial.println("PECTORALIS MAJOR COUNTERCLOCKWISE LOOSENING");
  }
  break;
  case MOVE_RIGHT_4:
  for(int i = 0; i < 100; i ++){
    digitalWrite(DIR_PIN_4, LOW); digitalWrite(STEP_PIN_4, HIGH); delay(1); digitalWrite(STEP_PIN_4, LOW); delay(1); Serial.println("PECTORALIS MAJOR CLOCKWISE TIGHTENING");
  }
  break;
  default:
  break;
  }
  Serial.println("working");
  //digitalWrite(EN_PIN,HIGH);
 
}
```
###### Muscle Fiber Material
An important consideration in the development of our device was the material choice for the mimicking of of the muscle/ligaments of the rotator cuff. Ideally, these muscles would have a tension profile that resmebles a shifted sigmoid. Speaking to Dr.Debski gave us a rough idea for what we were looking. Each line represents the angle of the humerus with respect to the scapula. X and Y represent force applied, and resulting translational shift. Essentially, how hard you have to push to move the joint in the socket. We reasoned that to extrapolate to EDS patients would involve making the curve more steep - less force would produce more translation because of the hypermobility.

{{< img src="/posts/academic-projects/senior_design/debski_meeting.png" align="center" title="Meeting with Dr.Debski">}}


From here, we kept on testing different elastics by manually stretching them out, and noticing if we felt the force exhibited mirrored what we desired. 

{{< youtube 8fGkPXKcj7I >}}
{{< vs >}}

###### Electrical Sensing Component
I wrote code to transition our initial circuit design to a little more refined model. The previous version simply had an LED and buzzer in series, with either connected to ground and a 5V power respectively. There are obvious issues and risks with this design. I wrote code to use the Arduino Uno's innate INPUT_PULLUP resistor that is built into the microcontroller to detect differences in the circuits connectivity. Thereby we could track when users failed, and use that data to improve. Furthermore, we could fix some of the practicalities that came with the original design (i.e. the buzzer just kept going off for all moments that the labrum was in contact with the humerus - this proved to be frustrating)

###### Housing and Final Assembly
I contributed to designing the humerus by deciding where the insertions sites for the muscle fibers would attach to. As stated before, to mimic physiology the four rotator cuff muscles were chosen. Below is an image of one of the reference images I used as well as the final STL 3D printer project file. 

{{< img src="/posts/academic-projects/senior_design/insertions.png" align="center" title="Muscle Insertions">}}




For final assembly, I connected all 3D parts with an epoxy resin plastic binder and clamping until the epoxy had set. Afterward, I installed the stepper motors into stepper motor brackets and fastened the brackets to the base of the housing. After which, I, along with two of my groupmmates, designed a method to fasten the muscle fibers to the stepper motor (using flexible couplings) and implemented this system. From there, we threaded the muscle fibers through the holes made in the 3D printed mold and calibrated the stepper motors to the tightness requisite to mimic normal shoulder functioning. 

Furthermore, in the early months of the projects I made the decision to order clay, which could be enveloped by memory foam (suggested by another teammate) and a final layer of synthetic scar tissue I found to mimic the feeling of soft tissue. A model of that has also been shown

{{< img src="/posts/academic-projects/senior_design/final_assembly_collage.png" align="center" title="Final Assembly">}}

## Fourth and Final Iteration 
The fourth iteration was the final one that would be made in the scope of the class. Although functional, iteration 3 failed in some capacities - including visually, functionally (regarding the consistency of the electrical conductance system) and interactively as it needed to be set up with a laptop that would be running the Arduino program in which commands would be directly inputted into. This obivously poses a huge problem. 

These were the principal areas in which the device was improved in the final iteration: 

#### Additional stepper motors 
After discussion with my design team about the current functionality of the motors, we decided to add two more stepper motors, allowing for independent internal and external rotation. Iteration 4 had issues with excessive internal rotation occurring with the tightening of the subscapularis analogue (the front-facing fiber), an independent external rotator was added to the model to ensure that the humerus can be displaced translationally without excessive rotation. This will allow the model to be a better mimic of the physiological issue. I rewired all the stepper motors and reprogrammed the arduino to take into account these additional forces myself. Furthermore, myself and Jeremy installed these in our new 3D printed housing in orientations that wouldn't impede the line of pull of the stepper motors.
{{< img src="/posts/academic-projects/senior_design/gluing_motors.JPEG" align="center" title="Motor Integration">}}

#### Interactive touchscreen

The primary addition for this iteration was the successful development of an interactive touchscreen that allows the user to specify which condition (hypermobile EDS or non-hEDS) they would like to perform treatment on. Furthermore, the interactive screen contains buttons that allow the user to select whether they would like the trainer to produce a subluxed state, or reduce a previously subluxed state on its own. Lastly, a certified trainer can access the “Manual” mode which allows for the precise specifications of the fibers in each individual stepper motor - allowing for high fidelity in mimicking a shoulder joint. Another external screen controlled by a Raspberry Pi microcontroller has been implemented to allow the continuous display of the gyroscopic simulation to the user. An external housing that contains all the electrical and visual components has been developed and implemented to this end.

I came up with the idea for the integration of both screens and an external housing unit that a team-mate made. It took alot of effort, but without it our use case did not make any sense. A practicing PT or phyiscal therapist student would have to have knowledge of Arduino, have the Arduino program loaded onto their laptop and inputs commmands directly into the command line if they wanted to use the device previously. This was incongruent with the use case and needed to be remediated. I had to restructure the Arduino pins, install, and code for the screen myself. 

{{< img src="/posts/academic-projects/senior_design/screen_wiring.JPEG" align="center" title="Screen Wiring">}}

The interface was tweaked several times to be easy enough to read but robust enough to use. The "Manual" mode allowed a technician or experienced user to alter the degree of tension or looseness in any one of the 6 different stepper motors. 

{{< img src="/posts/academic-projects/senior_design/screen.JPEG" align="center" title="Screen Display">}}


#### Power Supply

Lastly, the final alteration was changing the device power supply. Iteration 4 derived motor power from a wall outlet, and logical power (for the arduino and stepper drivers) from a USB cable connected to a laptop. The previous iteration was thereby limited in who could use the device, and where. A user would have to input commands by altering the command line of the Arduino software, and be continually within close range of an outlet. This did not satisfy the design inputs, and limited the educational applicability of the devie. By making every system powered by portable batteries encased in an external electrical housing, the device is now enabled to be used anywhere for extended periods of time, and by someone with no software background.I rewired everything to be powered by battery packs on my own. This includes the stepper battery, the batteries to compute logical commands, and the wall outlet neccessary to power the screen. 

{{< img src="/posts/academic-projects/senior_design/rewiring_battery.JPEG" align="center" title="Rewiring Battery">}}

#### Electrical Conductance System
The previous electrical conductancec system was inconsistent and was based on a principal that was bound to fail. Essentially if the circuit was completed (via interaction between the humeral head and the labral peak), current would run through the speaker. This has implicit disadvantages, includy janky connections, high resistivity leading to low current flow and subsequently low volume, and inherent safety risks. I remade the electrical conductance system on Arduino myself and integrated it with the existing code. This way, we could also record mistakes and excessive labral contact that could be used to tell the user how to improve in the future. The code block containing the screen, stepper control, and feedback system has been displayed below: 

```


#include <Elegoo_GFX.h>     // Core graphics library
#include <Elegoo_TFTLCD.h>  // Hardware-specific library
#include <TouchScreen.h>

// The control pins for the LCD can be assigned to any digital or
// analog pins...but we'll use the analog pins as this allows us to
// double up the pins with the touch screen (see the TFT paint example).
#define LCD_CS A3  // Chip Select goes to Analog 3
#define LCD_CD A2  // Command/Data goes to Analog 2
#define LCD_WR A1  // LCD Write goes to Analog 1
#define LCD_RD A0  // LCD Read goes to Analog 0

#define LCD_RESET A4  // Can alternately just connect to Arduino's reset pin

#define BLACK 0x0000
#define BLUE 0x001F
#define RED 0xF800
#define GREEN 0x07E0
#define CYAN 0x07FF
#define MAGENTA 0xF81F
#define YELLOW 0xFFE0
#define WHITE 0xFFFF

// Color definitions
#define ILI9341_BLACK 0x0000       /*   0,   0,   0 */
#define ILI9341_NAVY 0x000F        /*   0,   0, 128 */
#define ILI9341_DARKGREEN 0x03E0   /*   0, 128,   0 */
#define ILI9341_DARKCYAN 0x03EF    /*   0, 128, 128 */
#define ILI9341_MAROON 0x7800      /* 128,   0,   0 */
#define ILI9341_PURPLE 0x780F      /* 128,   0, 128 */
#define ILI9341_OLIVE 0x7BE0       /* 128, 128,   0 */
#define ILI9341_LIGHTGREY 0xC618   /* 192, 192, 192 */
#define ILI9341_DARKGREY 0x7BEF    /* 128, 128, 128 */
#define ILI9341_BLUE 0x001F        /*   0,   0, 255 */
#define ILI9341_GREEN 0x07E0       /*   0, 255,   0 */
#define ILI9341_CYAN 0x07FF        /*   0, 255, 255 */
#define ILI9341_RED 0xF800         /* 255,   0,   0 */
#define ILI9341_MAGENTA 0xF81F     /* 255,   0, 255 */
#define ILI9341_YELLOW 0xFFE0      /* 255, 255,   0 */
#define ILI9341_WHITE 0xFFFF       /* 255, 255, 255 */
#define ILI9341_ORANGE 0xFD20      /* 255, 165,   0 */
#define ILI9341_GREENYELLOW 0xAFE5 /* 173, 255,  47 */
#define ILI9341_PINK 0xF81F

#define TEXT_X 5
#define TEXT_Y 40
#define TEXT_W 230
#define TEXT_H 40
#define TEXT_TSIZE 2
#define TEXT_TCOLOR ILI9341_BLACK
char textfield[26] = "                          ";
int manualState = 0;
int lastManualState = 1;
int EDS = 2;
int subluxed = 0; 

char buttonlabels1[14][26] = { "Trainer", "Manual", "ER Tighten", "ER Loosen", "IR Tighten", "IR Loosen", "SSp Tighten", "SSp Loosen", "IS Tighten", "IS Loosen", "SSc Tighten", "SSc Loosen", "TM Tighten", "TM Loosen" };
char buttonlabels0[14][26] = { "Trainer", "Manual", "EDS", "Non-EDS", "Sublux", "Reduce", "Supraspinatus Tighten", "Infraspinatus Tighten", "Supraspinatus Loosen", "Infraspinatus Loosen", "Subscapularis Tighten", "Teres Minor Tighten", "Subscapularis Loosen", "Teres Minor Loosen" };
int BUTTON_X1 = 58; int BUTTON_Y1 = 60; int BUTTON_W1 =  116; int BUTTON_H1 = 35; int BUTTON_SPACING_X1 = 8; int BUTTON_SPACING_Y1 = 4; int BUTTON_TEXTSIZE1 =1; 
int BUTTON_X0 = 58; int BUTTON_Y0 = 60; int BUTTON_W0 =  116; int BUTTON_H0 = 70; int BUTTON_SPACING_X0 = 8; int BUTTON_SPACING_Y0 = 4; int BUTTON_TEXTSIZE0 =1; 

#define YP A3  // must be an analog pin, use "An" notation!
#define XM A2  // must be an analog pin, use "An" notation!
#define YM 9   // can be a digital pin
#define XP 8   // can be a digital pin
#define TS_MINX 120
#define TS_MAXX 900
#define TS_MINY 70
#define TS_MAXY 920




Elegoo_TFTLCD tft(LCD_CS, LCD_CD, LCD_WR, LCD_RD, LCD_RESET);
TouchScreen ts = TouchScreen(XP, YP, XM, YM, 300);


Elegoo_GFX_Button buttons[14];
/* create 15 buttons, in classic candybar phone style */
uint16_t buttoncolors[14] = { ILI9341_BLACK, ILI9341_DARKGREEN, ILI9341_BLUE,
                              ILI9341_RED, ILI9341_BLUE, ILI9341_RED,
                              ILI9341_BLUE, ILI9341_RED, ILI9341_BLUE,
                              ILI9341_RED, ILI9341_BLUE, ILI9341_RED,
                              ILI9341_BLUE, ILI9341_RED};


// 8888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888
// NOW INITIALIZE ALL THE STEPPER CONTROLLER VARIABLES - THESE ARE WHAT I NEED TO CHANGE FOR NOW
#define DIR_PIN_1 22  //direction
#define STEP_PIN_1 24

#define DIR_PIN_2 26  //direction
#define STEP_PIN_2 28

#define DIR_PIN_3 30  //direction
#define STEP_PIN_3 32

#define DIR_PIN_4 34  //direction
#define STEP_PIN_4 36

#define DIR_PIN_5 38  //direction
#define STEP_PIN_5 40

#define DIR_PIN_6 42  //direction
#define STEP_PIN_6 44

#define MS2_PIN 23
#define MS2_PIN_1 25

#define MS1_PIN 27
#define MS1_PIN_1 29

#define EN_PIN 31    //enable (CFG6)
#define EN_PIN_1 33  //enable (CFG6)

// 8888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888
// START OF THE INSTANTIATION OF THE LABRUM AND BUZZER CONNECTION 

#define GH_CONNECTION A8 
#define LABRUM_CONNECTION A9
#define BUZZER A10 
#define LED_GREEN A11
#define LED_RED A12


// 8888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888
// START OF THE SETUP  + THE CODE FOR THE SCREEN 



void setup(void) {
  Serial.begin(9600);
  Serial.println(F("TFT LCD test"));

#ifdef USE_Elegoo_SHIELD_PINOUT
  Serial.println(F("Using Elegoo 2.8\" TFT Arduino Shield Pinout"));
#else
  Serial.println(F("Using Elegoo 2.8\" TFT Breakout Board Pinout"));
#endif

  Serial.print("TFT size is "); Serial.print(tft.width()); Serial.print("x"); Serial.println(tft.height());

  tft.reset();

  uint16_t identifier = tft.readID();
  if (identifier == 0x9325) {
    Serial.println(F("Found ILI9325 LCD driver"));
  } else if (identifier == 0x9328) {
    Serial.println(F("Found ILI9328 LCD driver"));
  } else if (identifier == 0x4535) {
    Serial.println(F("Found LGDP4535 LCD driver"));
  } else if (identifier == 0x7575) {
    Serial.println(F("Found HX8347G LCD driver"));
  } else if (identifier == 0x9341) {
    Serial.println(F("Found ILI9341 LCD driver"));
  } else if (identifier == 0x8357) {
    Serial.println(F("Found HX8357D LCD driver"));
  } else if (identifier == 0x0101) {
    identifier = 0x9341;
    Serial.println(F("Found 0x9341 LCD driver"));
  } else {
    Serial.print(F("Unknown LCD driver chip: "));
    Serial.println(identifier, HEX);
    Serial.println(F("If using the Elegoo 2.8\" TFT Arduino shield, the line:"));
    Serial.println(F("  #define USE_Elegoo_SHIELD_PINOUT"));
    Serial.println(F("should appear in the library header (Elegoo_TFT.h)."));
    Serial.println(F("If using the breakout board, it should NOT be #defined!"));
    Serial.println(F("Also if using the breakout, double-check that all wiring"));
    Serial.println(F("matches the tutorial."));
    identifier = 0x9341;
  }

  tft.begin(identifier);
  tft.setRotation(2);
  tft.fillScreen(ILI9341_DARKGREY);
  

  buttons[0].initButton(&tft, 58,
                        20,  // x, y, w, h, outline, fill, text
                        BUTTON_W1, BUTTON_H1, ILI9341_WHITE, buttoncolors[0], ILI9341_WHITE,
                        buttonlabels0[0], BUTTON_TEXTSIZE1);
  buttons[0].drawButton();

  buttons[1].initButton(&tft, 182,
                        20,  // x, y, w, h, outline, fill, text
                        BUTTON_W1, BUTTON_H1, ILI9341_WHITE, buttoncolors[1], ILI9341_WHITE,
                        buttonlabels0[1], BUTTON_TEXTSIZE1);
  buttons[1].drawButton();


buttoncolors[2] = ILI9341_NAVY; buttoncolors[4] = ILI9341_NAVY;
buttoncolors[3] = ILI9341_MAROON; buttoncolors[5] = ILI9341_MAROON;
 
  for (uint8_t row = 1; row < 3; row++) {
                for (uint8_t col = 0; col < 2; col++) {
                  buttons[col + row * 2].initButton(&tft, BUTTON_X0 + col * (BUTTON_W0 + BUTTON_SPACING_X0),
                                                    BUTTON_Y0 + row * (BUTTON_H0 + BUTTON_SPACING_Y0),  // x, y, w, h, outline, fill, text
                                                    BUTTON_W0, BUTTON_H0, ILI9341_WHITE, buttoncolors[col + row * 2], ILI9341_WHITE,
                                                    buttonlabels0[col + row * 2], BUTTON_TEXTSIZE0);
                  buttons[col + row * 2].drawButton();
                }
          }

  // create 'text field'
  tft.drawRect(TEXT_X, TEXT_Y, TEXT_W, TEXT_H, ILI9341_DARKGREY);


// 8888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888
// START CODE FOR THE CONTROL OF THE STEPPER MOTORS

  pinMode(EN_PIN, OUTPUT);
  pinMode(EN_PIN_1, OUTPUT);

  digitalWrite(EN_PIN, HIGH);  //deactivate driver (LOW active)
  digitalWrite(EN_PIN_1, HIGH);


  pinMode(DIR_PIN_1, OUTPUT);  //   pinMode(DIR_PIN_2, OUTPUT);  pinMode(DIR_PIN_3, OUTPUT);  pinMode(DIR_PIN_4, OUTPUT);
  pinMode(DIR_PIN_2, OUTPUT);  //   pinMode(DIR_PIN_2, OUTPUT);  pinMode(DIR_PIN_3, OUTPUT);  pinMode(DIR_PIN_4, OUTPUT);
  pinMode(DIR_PIN_3, OUTPUT);  //   pinMode(DIR_PIN_2, OUTPUT);  pinMode(DIR_PIN_3, OUTPUT);  pinMode(DIR_PIN_4, OUTPUT);
  pinMode(DIR_PIN_4, OUTPUT);  //   pinMode(DIR_PIN_2, OUTPUT);  pinMode(DIR_PIN_3, OUTPUT);  pinMode(DIR_PIN_4, OUTPUT);
  pinMode(DIR_PIN_5, OUTPUT);  //   pinMode(DIR_PIN_2, OUTPUT);  pinMode(DIR_PIN_3, OUTPUT);  pinMode(DIR_PIN_4, OUTPUT);
  pinMode(DIR_PIN_6, OUTPUT);  //   pinMode(DIR_PIN_2, OUTPUT);  pinMode(DIR_PIN_3, OUTPUT);  pinMode(DIR_PIN_4, OUTPUT);

  //digitalWrite(DIR_PIN_1, LOW); //LOW to CCW
  digitalWrite(DIR_PIN_1, HIGH);  // digitalWrite(DIR_PIN_2, HIGH); digitalWrite(DIR_PIN_4, HIGH); digitalWrite(DIR_PIN_4, HIGH);
  digitalWrite(DIR_PIN_2, HIGH);  // digitalWrite(DIR_PIN_2, HIGH); digitalWrite(DIR_PIN_4, HIGH); digitalWrite(DIR_PIN_4, HIGH);
  digitalWrite(DIR_PIN_3, HIGH);  // digitalWrite(DIR_PIN_2, HIGH); digitalWrite(DIR_PIN_4, HIGH); digitalWrite(DIR_PIN_4, HIGH);
  digitalWrite(DIR_PIN_4, HIGH);  // digitalWrite(DIR_PIN_2, HIGH); digitalWrite(DIR_PIN_4, HIGH); digitalWrite(DIR_PIN_4, HIGH);
  digitalWrite(DIR_PIN_5, HIGH);  // digitalWrite(DIR_PIN_2, HIGH); digitalWrite(DIR_PIN_4, HIGH); digitalWrite(DIR_PIN_4, HIGH);
  digitalWrite(DIR_PIN_6, HIGH);  // digitalWrite(DIR_PIN_2, HIGH); digitalWrite(DIR_PIN_4, HIGH); digitalWrite(DIR_PIN_4, HIGH);
  //HIGH to CW

  pinMode(STEP_PIN_1, OUTPUT);  // pinMode(STEP_PIN_2, OUTPUT);  pinMode(STEP_PIN_3, OUTPUT);  pinMode(STEP_PIN_4, OUTPUT);
  pinMode(STEP_PIN_2, OUTPUT);  // pinMode(STEP_PIN_2, OUTPUT);  pinMode(STEP_PIN_3, OUTPUT);  pinMode(STEP_PIN_4, OUTPUT);
  pinMode(STEP_PIN_3, OUTPUT);  // pinMode(STEP_PIN_2, OUTPUT);  pinMode(STEP_PIN_3, OUTPUT);  pinMode(STEP_PIN_4, OUTPUT);
  pinMode(STEP_PIN_4, OUTPUT);  // pinMode(STEP_PIN_2, OUTPUT);  pinMode(STEP_PIN_3, OUTPUT);  pinMode(STEP_PIN_4, OUTPUT);
  pinMode(STEP_PIN_5, OUTPUT);  // pinMode(STEP_PIN_2, OUTPUT);  pinMode(STEP_PIN_3, OUTPUT);  pinMode(STEP_PIN_4, OUTPUT);
  pinMode(STEP_PIN_6, OUTPUT);  // pinMode(STEP_PIN_2, OUTPUT);  pinMode(STEP_PIN_3, OUTPUT);  pinMode(STEP_PIN_4, OUTPUT);

  digitalWrite(STEP_PIN_1, LOW);  //  digitalWrite(STEP_PIN_2, LOW);  digitalWrite(STEP_PIN_3, LOW);  digitalWrite(STEP_PIN_4, LOW);
  digitalWrite(STEP_PIN_2, LOW);  //  digitalWrite(STEP_PIN_2, LOW);  digitalWrite(STEP_PIN_3, LOW);  digitalWrite(STEP_PIN_4, LOW);
  digitalWrite(STEP_PIN_3, LOW);  //  digitalWrite(STEP_PIN_2, LOW);  digitalWrite(STEP_PIN_3, LOW);  digitalWrite(STEP_PIN_4, LOW);
  digitalWrite(STEP_PIN_4, LOW);  //  digitalWrite(STEP_PIN_2, LOW);  digitalWrite(STEP_PIN_3, LOW);  digitalWrite(STEP_PIN_4, LOW);
  digitalWrite(STEP_PIN_5, LOW);  //  digitalWrite(STEP_PIN_2, LOW);  digitalWrite(STEP_PIN_3, LOW);  digitalWrite(STEP_PIN_4, LOW);
  digitalWrite(STEP_PIN_6, LOW);  //  digitalWrite(STEP_PIN_2, LOW);  digitalWrite(STEP_PIN_3, LOW);  digitalWrite(STEP_PIN_4, LOW);


  pinMode(MS1_PIN, OUTPUT);
  pinMode(MS1_PIN_1, OUTPUT);
  pinMode(MS2_PIN, OUTPUT);
  pinMode(MS2_PIN_1, OUTPUT);

  digitalWrite(MS1_PIN, HIGH);
  digitalWrite(MS1_PIN_1, HIGH);

  digitalWrite(MS2_PIN, LOW);
  digitalWrite(MS2_PIN_1, LOW);

  digitalWrite(EN_PIN, LOW);  //activate driver
  digitalWrite(EN_PIN_1, LOW);  //activate driver

  Serial.println(EN_PIN);
  Serial.println(EN_PIN_1);


// 8888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888
// SETUP THE BUZZER + LABRUM CONNECTIONS 


  pinMode(LABRUM_CONNECTION, INPUT_PULLUP);
  pinMode(GH_CONNECTION, INPUT_PULLUP);
  pinMode(LED_GREEN, OUTPUT);
  pinMode(LED_RED, OUTPUT);

}


// 8888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888
// START OF THE  LOOP + THE CODE FOR THE SCREEN 

#define MINPRESSURE 10
#define MAXPRESSURE 1000

void loop(void) {
  digitalWrite(13, HIGH);
  TSPoint p = ts.getPoint();
  digitalWrite(13, LOW);
  pinMode(XM, OUTPUT);
  pinMode(YP, OUTPUT);

  if (p.z > MINPRESSURE && p.z < MAXPRESSURE) {
    // scale from 0->1023 to tft.width
    p.x = map(p.x, TS_MINX, TS_MAXX, tft.width(), 0);
    p.y = (tft.height() - map(p.y, TS_MINY, TS_MAXY, tft.height(), 0));
  }

  // Loop through two buttons 
      for (uint8_t b = 0; b < 2; b++) {
        if (buttons[b].contains(p.x, p.y)) {
          buttons[b].press(true);  // tell the button it is pressed
        } else {
          buttons[b].press(false);  // tell the button it is NOT pressed
        }
      }

      // now we can see if the button state (trainer mode has changed)
    
      for (uint8_t b = 0; b < 2; b++) {
        if (buttons[b].justReleased()) {
          buttons[b].drawButton();  // draw normal
          for (int i = 0; i < strlen(textfield); i++) {
            textfield[i] = ' ';
          }
        }

        // TRY SEEING IF THIS PART IS NECCESSARY - WE ALREADY LOOP THROUGH THIS SHIT LATER ... IT MIGHT JUST SLOW DOWN PROGRAM ID K
        // I THINK ALL YOU WOULD HAVE TO DO IS INSTANTIATE MANUAL STATE AS SOMETHING RANDOM THAT WAS THE SAME AS BEFORE, CREATEA A NEW MANUAL STATE IN THE LATER LOOP, AND SET A NEW LASTMANUALSTATE at the end of the loop so its compared at the beggining of the next loop  
        if (buttons[b].justPressed()) {
          buttons[b].drawButton(true);  // draw invert!
          if (b == 1) { //this invokes manual mode 
            manualState = 1; 
          }
          if (b == 0){
            manualState = 0;
          }
          delay(100);  // UI debouncing - mess around with this to see if it makes a difference 
        }
      }


  if (lastManualState != manualState) {
    if (manualState == 1) {
          tft.fillScreen(ILI9341_LIGHTGREY);
          buttoncolors[2] = ILI9341_BLUE; buttoncolors[4] = ILI9341_BLUE;
          buttoncolors[3] = ILI9341_RED; buttoncolors[5] = ILI9341_RED;
          buttons[0].initButton(&tft, 58,
                            20,  // x, y, w, h, outline, fill, text
                          BUTTON_W1, BUTTON_H1, ILI9341_WHITE, buttoncolors[0], ILI9341_WHITE,
                          buttonlabels1[0], BUTTON_TEXTSIZE1);
          buttons[0].drawButton();

          buttons[1].initButton(&tft, 182,
                                20,  // x, y, w, h, outline, fill, text
                                BUTTON_W1, BUTTON_H1, ILI9341_WHITE, buttoncolors[1], ILI9341_WHITE,
                                buttonlabels1[1], BUTTON_TEXTSIZE1);
          buttons[1].drawButton();


 
          // create 'text field'
          tft.drawRect(TEXT_X, TEXT_Y, TEXT_W, TEXT_H, ILI9341_WHITE);
          for (uint8_t row = 1; row < 7; row++) {
            for (uint8_t col = 0; col < 2; col++) {
              buttons[col + row * 2].initButton(&tft, BUTTON_X1 + col * (BUTTON_W1 + BUTTON_SPACING_X1),
                                                BUTTON_Y1 + row * (BUTTON_H1 + BUTTON_SPACING_Y1),  // x, y, w, h, outline, fill, text
                                                BUTTON_W1, BUTTON_H1, ILI9341_WHITE, buttoncolors[col + row * 2], ILI9341_WHITE,
                                                buttonlabels1[col + row * 2], BUTTON_TEXTSIZE1);
              buttons[col + row * 2].drawButton();
            }
          }
      
    } 
    if(manualState == 0) { //Changed to trainer mode, instantiate buttons and loop through

            tft.fillScreen(ILI9341_DARKGREY);
            Serial.print("LMS"); Serial.println(lastManualState);
            Serial.print("MS"); Serial.println(manualState);
            buttoncolors[2] = ILI9341_NAVY; buttoncolors[4] = ILI9341_NAVY;
            buttoncolors[3] = ILI9341_MAROON; buttoncolors[5] = ILI9341_MAROON;

          buttons[0].initButton(&tft, 58,
                                  20,  // x, y, w, h, outline, fill, text
                                  BUTTON_W1, BUTTON_H1, ILI9341_WHITE, buttoncolors[0], ILI9341_WHITE,
                                  buttonlabels0[0], BUTTON_TEXTSIZE1);
          buttons[0].drawButton();

          buttons[1].initButton(&tft, 182,
                                  20,  // x, y, w, h, outline, fill, text
                                  BUTTON_W1, BUTTON_H1, ILI9341_WHITE, buttoncolors[1], ILI9341_WHITE,
                                  buttonlabels0[1], BUTTON_TEXTSIZE1);
          buttons[1].drawButton();
 
 
          for (uint8_t row = 1; row < 3; row++) {
              for (uint8_t col = 0; col < 2; col++) {
                  buttons[col + row * 2].initButton(&tft, BUTTON_X0 + col * (BUTTON_W0 + BUTTON_SPACING_X0),
                                                    BUTTON_Y0 + row * (BUTTON_H0 + BUTTON_SPACING_Y0),  // x, y, w, h, outline, fill, text
                                                    BUTTON_W0, BUTTON_H0, ILI9341_WHITE, buttoncolors[col + row * 2], ILI9341_WHITE,
                                                    buttonlabels0[col + row * 2], BUTTON_TEXTSIZE0);
                  buttons[col + row * 2].drawButton();
              }
          }



          tft.drawRect(TEXT_X, TEXT_Y, TEXT_W, TEXT_H, ILI9341_WHITE);
                
      } 
  } 
  //Always invoke this - looping through different button configurations based on the button state 
  if(manualState == 1){  
      for (uint8_t b = 0; b < 14; b++) {
        if (buttons[b].contains(p.x, p.y)) {
          //Serial.print("Pressing: "); Serial.println(b);
          buttons[b].press(true);  // tell the button it is pressed
        } else {
          buttons[b].press(false);  // tell the button it is NOT pressed
        }
      }
      // now we can ask the buttons if their state has changed
          for (uint8_t b = 0; b < 14; b++) {
            if (buttons[b].justReleased()) {
              buttons[b].drawButton();  // draw normal
              for (int i = 0; i < strlen(textfield); i++) {
                textfield[i] = ' ';
              }
            }

          if (buttons[b].justPressed()) {
            buttons[b].drawButton(true);  // draw invert!

            // if a numberpad button, append the relevant # to the textfield
            if (b >= 2) {
              for (int i = 0; i < strlen(buttonlabels1[b]); i++) {
                textfield[i] = buttonlabels1[b][i];
              }

            switch(b){
              case 2:
                Serial.print("Invoke button "); Serial.print(b); Serial.print(" of action "); Serial.println(buttonlabels1[b]);
                for(int i = 0; i < 100; i ++){
                  digitalWrite(DIR_PIN_1, HIGH); digitalWrite(STEP_PIN_1, HIGH); delay(1); digitalWrite(STEP_PIN_1, LOW); delay(1); 
                }
              break;
              case 3:
                Serial.print("Invoke button "); Serial.print(b); Serial.print(" of action "); Serial.println(buttonlabels1[b]);
                for(int i = 0; i < 100; i ++){
                  digitalWrite(DIR_PIN_1, LOW); digitalWrite(STEP_PIN_1, HIGH); delay(1); digitalWrite(STEP_PIN_1, LOW); delay(1); 
                }
              break;
              case 4:
                Serial.print("Invoke button "); Serial.print(b); Serial.print(" of action "); Serial.println(buttonlabels1[b]);
                for(int i = 0; i < 100; i ++){
                  digitalWrite(DIR_PIN_2, HIGH); digitalWrite(STEP_PIN_2, HIGH); delay(1); digitalWrite(STEP_PIN_2, LOW); delay(1); 
                }
              break;
              case 5:
                Serial.print("Invoke button "); Serial.print(b); Serial.print(" of action "); Serial.println(buttonlabels1[b]);
                for(int i = 0; i < 100; i ++){
                  digitalWrite(DIR_PIN_2, LOW); digitalWrite(STEP_PIN_2, HIGH); delay(1); digitalWrite(STEP_PIN_2, LOW); delay(1); 
                }
              break;
              case 6:
                Serial.print("Invoke button "); Serial.print(b); Serial.print(" of action "); Serial.println(buttonlabels1[b]);
                for(int i = 0; i < 100; i ++){
                  digitalWrite(DIR_PIN_3, HIGH); digitalWrite(STEP_PIN_3, HIGH); delay(1); digitalWrite(STEP_PIN_3, LOW); delay(1); 
                }
              break;
              case 7:
                Serial.print("Invoke button "); Serial.print(b); Serial.print(" of action "); Serial.println(buttonlabels1[b]);
                for(int i = 0; i < 100; i ++){
                  digitalWrite(DIR_PIN_3, LOW); digitalWrite(STEP_PIN_3, HIGH); delay(1); digitalWrite(STEP_PIN_3, LOW); delay(1); 
                }
              break;
              case 8:
                Serial.print("Invoke button "); Serial.print(b); Serial.print(" of action "); Serial.println(buttonlabels1[b]);
                for(int i = 0; i < 100; i ++){
                  digitalWrite(DIR_PIN_4, HIGH); digitalWrite(STEP_PIN_4, HIGH); delay(1); digitalWrite(STEP_PIN_4, LOW); delay(1); 
                }
              break;
              case 9:
                Serial.print("Invoke button "); Serial.print(b); Serial.print(" of action "); Serial.println(buttonlabels1[b]);
                for(int i = 0; i < 100; i ++){
                  digitalWrite(DIR_PIN_4, LOW); digitalWrite(STEP_PIN_4, HIGH); delay(1); digitalWrite(STEP_PIN_4, LOW); delay(1); 
                }
              break;
              case 10:
                Serial.print("Invoke button "); Serial.print(b); Serial.print(" of action "); Serial.println(buttonlabels1[b]);
                for(int i = 0; i < 100; i ++){
                  digitalWrite(DIR_PIN_5, HIGH); digitalWrite(STEP_PIN_5, HIGH); delay(1); digitalWrite(STEP_PIN_5, LOW); delay(1); 
                }
              break;
              case 11:
                Serial.print("Invoke button "); Serial.print(b); Serial.print(" of action "); Serial.println(buttonlabels1[b]);
                for(int i = 0; i < 100; i ++){
                  digitalWrite(DIR_PIN_5, LOW); digitalWrite(STEP_PIN_5, HIGH); delay(1); digitalWrite(STEP_PIN_5, LOW); delay(1); 
                }  
              break;
              case 12:
                Serial.print("Invoke button "); Serial.print(b); Serial.print(" of action "); Serial.println(buttonlabels1[b]);
                for(int i = 0; i < 100; i ++){
                  digitalWrite(DIR_PIN_6, HIGH); digitalWrite(STEP_PIN_6, HIGH); delay(1); digitalWrite(STEP_PIN_6, LOW); delay(1); 
                }  
              break;    
              case 13:
                Serial.print("Invoke button "); Serial.print(b); Serial.print(" of action "); Serial.println(buttonlabels1[b]);
                for(int i = 0; i < 100; i ++){
                  digitalWrite(DIR_PIN_6, LOW); digitalWrite(STEP_PIN_6, HIGH); delay(1); digitalWrite(STEP_PIN_6, LOW); delay(1); 
                }
              break;                   
              default:
                Serial.println("err");
              break;

            }






            }
            /*
            if (b == 1) { //this invokes manual mode 
            manualState = 1; 
            }
            if (b == 0){
            manualState = 0;
            }
            */
            // update the current text field
            //Serial.println(textfield);
            tft.setCursor(TEXT_X + 10, TEXT_Y + 10);
            tft.setTextColor(TEXT_TCOLOR, ILI9341_OLIVE);
            tft.setTextSize(TEXT_TSIZE);
            tft.print(textfield); 
            delay(100);  // UI debouncing
          }
        }
      }
      else{
        for (uint8_t b = 0; b < 6; b++) {
          if (buttons[b].contains(p.x, p.y)) {
            //Serial.print("Pressing: "); Serial.println(b);
            buttons[b].press(true);  // tell the button it is pressed
          } else {
            buttons[b].press(false);  // tell the button it is NOT pressed
          }
        }
      for (uint8_t b = 0; b < 6; b++) {
        if (buttons[b].justReleased()) {
          buttons[b].drawButton();  // draw normal
          for (int i = 0; i < strlen(textfield); i++) {
            textfield[i] = ' ';
          }
        }

        if (buttons[b].justPressed()) {
          buttons[b].drawButton(true);  // draw invert!
          // if a numberpad button, append the relevant # to the textfield
          if (b >= 2) {
            for (int i = 0; i < strlen(buttonlabels0[b]); i++) {
              textfield[i] = buttonlabels0[b][i];
            }

                switch(b){ // prob gonna have to debug with some print statements 
                    case 2:
                      if(EDS == 0){
                          Serial.println("Changing from non-EDS to EDS condition"); // LOOSEN EVERYTHING 
                          for(int i = 0; i < 100; i ++){
                            digitalWrite(DIR_PIN_1, LOW); digitalWrite(STEP_PIN_1, HIGH); delay(1); digitalWrite(STEP_PIN_1, LOW); delay(1);
                            digitalWrite(DIR_PIN_2, LOW); digitalWrite(STEP_PIN_2, HIGH); delay(1); digitalWrite(STEP_PIN_2, LOW); delay(1);
                            digitalWrite(DIR_PIN_3, LOW); digitalWrite(STEP_PIN_3, HIGH); delay(1); digitalWrite(STEP_PIN_3, LOW); delay(1);
                            digitalWrite(DIR_PIN_4, LOW); digitalWrite(STEP_PIN_4, HIGH); delay(1); digitalWrite(STEP_PIN_4, LOW); delay(1);
                            digitalWrite(DIR_PIN_5, LOW); digitalWrite(STEP_PIN_5, HIGH); delay(1); digitalWrite(STEP_PIN_5, LOW); delay(1);
                            digitalWrite(DIR_PIN_6, LOW); digitalWrite(STEP_PIN_6, HIGH); delay(1); digitalWrite(STEP_PIN_6, LOW); delay(1);         
                          }                      
                      }
                      if(EDS == 2){
                          Serial.println("Changing from non-EDS to EDS condition"); // LOOSEN EVERYTHING 
                          for(int i = 0; i < 1000; i ++){
                            digitalWrite(DIR_PIN_1, HIGH); digitalWrite(STEP_PIN_1, HIGH); delay(1); digitalWrite(STEP_PIN_1, LOW); delay(1);
                            digitalWrite(DIR_PIN_2, HIGH); digitalWrite(STEP_PIN_2, HIGH); delay(1); digitalWrite(STEP_PIN_2, LOW); delay(1);
                            digitalWrite(DIR_PIN_3, HIGH); digitalWrite(STEP_PIN_3, HIGH); delay(1); digitalWrite(STEP_PIN_3, LOW); delay(1);
                            digitalWrite(DIR_PIN_4, HIGH); digitalWrite(STEP_PIN_4, HIGH); delay(1); digitalWrite(STEP_PIN_4, LOW); delay(1);
                            digitalWrite(DIR_PIN_5, HIGH); digitalWrite(STEP_PIN_5, HIGH); delay(1); digitalWrite(STEP_PIN_5, LOW); delay(1);
                            digitalWrite(DIR_PIN_6, HIGH); digitalWrite(STEP_PIN_6, HIGH); delay(1); digitalWrite(STEP_PIN_6, LOW); delay(1);         
                          }                     
                      }
                      EDS = 1; 
                    break;
                    case 3:
                      if(EDS == 1){
                          Serial.println("Changing from EDS to non-EDS   condition"); // TIGHTEN EVERYTHING 
                          for(int i = 0; i < 100; i ++){
                            digitalWrite(DIR_PIN_1, HIGH); digitalWrite(STEP_PIN_1, HIGH); delay(1); digitalWrite(STEP_PIN_1, LOW); delay(1);
                            digitalWrite(DIR_PIN_2, HIGH); digitalWrite(STEP_PIN_2, HIGH); delay(1); digitalWrite(STEP_PIN_2, LOW); delay(1);
                            digitalWrite(DIR_PIN_3, HIGH); digitalWrite(STEP_PIN_3, HIGH); delay(1); digitalWrite(STEP_PIN_3, LOW); delay(1);
                            digitalWrite(DIR_PIN_4, HIGH); digitalWrite(STEP_PIN_4, HIGH); delay(1); digitalWrite(STEP_PIN_4, LOW); delay(1);
                            digitalWrite(DIR_PIN_5, HIGH); digitalWrite(STEP_PIN_5, HIGH); delay(1); digitalWrite(STEP_PIN_5, LOW); delay(1);
                            digitalWrite(DIR_PIN_6, HIGH); digitalWrite(STEP_PIN_6, HIGH); delay(1); digitalWrite(STEP_PIN_6, LOW); delay(1);
                          }                      
                      }
                      if(EDS == 2){
                          Serial.println("Changing from non-EDS to EDS condition"); // LOOSEN EVERYTHING 
                          for(int i = 0; i < 700; i ++){
                            digitalWrite(DIR_PIN_1, HIGH); digitalWrite(STEP_PIN_1, HIGH); delay(1); digitalWrite(STEP_PIN_1, LOW); delay(1);
                            digitalWrite(DIR_PIN_2, HIGH); digitalWrite(STEP_PIN_2, HIGH); delay(1); digitalWrite(STEP_PIN_2, LOW); delay(1);
                            digitalWrite(DIR_PIN_3, HIGH); digitalWrite(STEP_PIN_3, HIGH); delay(1); digitalWrite(STEP_PIN_3, LOW); delay(1);
                            digitalWrite(DIR_PIN_4, HIGH); digitalWrite(STEP_PIN_4, HIGH); delay(1); digitalWrite(STEP_PIN_4, LOW); delay(1);
                            digitalWrite(DIR_PIN_5, HIGH); digitalWrite(STEP_PIN_5, HIGH); delay(1); digitalWrite(STEP_PIN_5, LOW); delay(1);
                            digitalWrite(DIR_PIN_6, HIGH); digitalWrite(STEP_PIN_6, HIGH); delay(1); digitalWrite(STEP_PIN_6, LOW); delay(1);         
                          }                     
                      }
                      EDS = 0; 
                    break;
                    case 4: // SUBLUX - ACTIVATE INTERNAL ROTATOR AND 2 OTHER MECHANISMS
                          for(int i = 0; i < 1000; i ++){
                            digitalWrite(DIR_PIN_1, HIGH); digitalWrite(STEP_PIN_1, HIGH); delay(1); digitalWrite(STEP_PIN_1, LOW); delay(1);
                            digitalWrite(DIR_PIN_2, HIGH); digitalWrite(STEP_PIN_2, HIGH); delay(1); digitalWrite(STEP_PIN_2, LOW); delay(1);
                            digitalWrite(DIR_PIN_3, HIGH); digitalWrite(STEP_PIN_3, HIGH); delay(1); digitalWrite(STEP_PIN_3, LOW); delay(1);
                            digitalWrite(DIR_PIN_4, LOW); digitalWrite(STEP_PIN_1, HIGH); delay(1); digitalWrite(STEP_PIN_1, LOW); delay(1);
                            digitalWrite(DIR_PIN_5, LOW); digitalWrite(STEP_PIN_2, HIGH); delay(1); digitalWrite(STEP_PIN_2, LOW); delay(1);
                            digitalWrite(DIR_PIN_6, LOW); digitalWrite(STEP_PIN_3, HIGH); delay(1); digitalWrite(STEP_PIN_3, LOW); delay(1);
                          }  
                    break;
                    case 5: // OTHER IDEAS -- LOOSEN TENSION IN 3 - CREATE MORE TENSION IN OTHER THREE, OR JUST EXACERBATE TENSION IN ONLY THREE AS WE'RE DOING BELOW
                          for(int i = 0; i < 1000; i ++){
                            digitalWrite(DIR_PIN_1, LOW); digitalWrite(STEP_PIN_1, HIGH); delay(1); digitalWrite(STEP_PIN_1, LOW); delay(1);
                            digitalWrite(DIR_PIN_2, LOW); digitalWrite(STEP_PIN_2, HIGH); delay(1); digitalWrite(STEP_PIN_2, LOW); delay(1);
                            digitalWrite(DIR_PIN_3, LOW); digitalWrite(STEP_PIN_3, HIGH); delay(1); digitalWrite(STEP_PIN_3, LOW); delay(1);
                            digitalWrite(DIR_PIN_4, HIGH); digitalWrite(STEP_PIN_1, HIGH); delay(1); digitalWrite(STEP_PIN_1, LOW); delay(1);
                            digitalWrite(DIR_PIN_5, HIGH); digitalWrite(STEP_PIN_2, HIGH); delay(1); digitalWrite(STEP_PIN_2, LOW); delay(1);
                            digitalWrite(DIR_PIN_6, HIGH); digitalWrite(STEP_PIN_3, HIGH); delay(1); digitalWrite(STEP_PIN_3, LOW); delay(1);
                          }  
                    break;                  
                    default:
                      Serial.println("err");
                    break;
                }



          }
            /*          
            if (b == 1) { //this invokes manual mode 
            manualState = 1; 
            }
            if (b == 0){
              manualState = 0;
            }
          */

          tft.setCursor(TEXT_X + 10, TEXT_Y + 10);
          tft.setTextColor(TEXT_TCOLOR, ILI9341_DARKGREY);
          tft.setTextSize(TEXT_TSIZE);
          tft.print(textfield); 



          delay(100);  // UI debouncing
        }
      }
      }
      lastManualState = manualState;



      // 8888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888
      // LABRUM CONNECTION PROCESSING

  byte labrum = digitalRead(LABRUM_CONNECTION);
  Serial.print("Labrum byte is "); Serial.println(labrum);
  if(labrum == 0){
      tone(BUZZER,440, 100);
      digitalWrite(LED_RED, HIGH);
  } 
  else{
    digitalWrite(LED_RED,LOW);
  }

  byte GH = digitalRead(GH_CONNECTION);
  Serial.print("Glenohumeral byte is "); Serial.println(GH);
  if(GH == 0){
      digitalWrite(LED_GREEN, HIGH);
  } 
  else{
    digitalWrite(LED_GREEN,LOW);
  }

    }


```

#### Final Production Equivalent
The final iteration was thereby an accumulation of all of these improvements. Functionally, it was able to walk the user through reducing an anterior shoulder subluxation that closely mimicked both non-EDS and EDS morphology and gave real-time feedback for improvement. 

{{< youtube 96FUYL5U1jE >}}
{{< vs >}}

When presenting at expo, the final design was topped off with the addition of the external housing unit which appeared as such 

{{< img src="/posts/academic-projects/senior_design/final_box.JPEG" align="center" title="Final Box">}}


## Regulatory Considerations, Hazard and Risk Analysis, Other Insights


#### Regulatory Considerations 
The delineation of the regulatory class is integral to medical product design. This can be made easier through the identification of predicate products that are substantially equivalent (SE). The determination of susbtantial equivalence is not only useful here, but applies to the decision of which regulatory pathway to pursue as well. 

Substantial equivalence is drawn when a product shares the same intended use and technological characteristics. We could not identify a substantially equivalent product, and thus could not determine the regulatory class initially. Typically in this case a product will be elevated to Class III, the highest risk category, and undergo the most stringest regulatory pathway, premarket approval. Due to the low risk nature of our device (it has no therapeutic effect, nor does it interact with patients), we reasoned it would be classified as Class I under the De Novo pathway - a recent pathway used to get very low risk medical device products approved more swiftly.



#### Hazard and Risk Analysis
Hazard and risk analysis was another critical point of the class. Below I outline some memorable tools that were used to perform this analysis, as well as my own contributions in accounting for risk in our engineering design controls. 



##### FTA
Fault tree analysis is a method of analyzing faults/hazards that the system produces from the highest level. It extends top down, that is, the user breaks initial hazards down to the consituent parts that could potentially lead to it. I helped perform this analysis. Issues with this method are the reliance on the experience of  the operator to identify probable hazards, among others. An image has been produced from our document. The miro board is perfect for constructing these  

{{< img src="/posts/academic-projects/senior_design/fta.png" align="center" title="FTA">}}

##### FMEA
Failure mode and effects analysis acts in the opposite direction - evaluating the failure at each small subcomponent and seeing what risks they could amalgamate too. There is much less reliance on experience, but far more easy to get lost in the grand scheme of things (as our professor, Dr.Gartner has made aware to us). I also contributed to this 

{{< img src="/posts/academic-projects/senior_design/fmea.png" align="center" title="FMEA">}}



##### Ways to Control Risk
Voltage spikes were one risk I identified and was particularly worried about. The 12V power supply being used to power the stepper has the potential of spiking the voltage and damaging crucial electrical components. A 47uF decoupling capacitor inserted between the power supply Vin and ground was used to mitigate this risk.

Another potent risk are exposed electrical components. Although not accounted for yet, we plan to encase the electronics in a custom 3D printed housing set.

The exposed wires that come from the muscle insertions have the potential of getting wrapped up and harming the patient. In our production equivalent prototype, we intend to mitigate this by making the glenohumeral joint encased in a clear housing that would allow visualization of the joint, but not direct interaction.


## Verification and Validation
A critical component of this project was conducting verification to ensure that the device met the specifications we set, and validation to ensure that it was what the user wanted. 

#### Verification 
Verification was split 5 ways among my group members because of the amount of verification we had to perform. Generally, as the amount of features in a device increases, so does the amount of verification tests. I conducted three on my own. 

The first was to ensure that the muscle fibers would not break over time. The second was to ensure that the device could stably produce a subluxation that was analagous to a clinical correlate and thereby >= 1cm in translation within the GH joint. The final verification test was to ensure that the shoulder essentially "felt" like a normal human shoulder. We used a model developed by our mentor, Dr.Debski, to identify whether our device was performly adequately. Essentially, for a normal shoulder we wanted to mimic the following sigmoidal curve:

{{< img src="/posts/academic-projects/senior_design/debski.png" align="center" title="Normal Shoulder Physiology">}}

Furthermore, to approximate the EDS condition we accentuated the slopes of the curve and increased the extremes that the displacement vaues plateued at. Hypermobile joints displace translationally will less load application, and we made the following adjustment according to expert guidance as such. 
{{< img src="/posts/academic-projects/senior_design/EDScurve.png" align="center" title="EDS Shoulder Physiology">}}

The following methodology was undertaken to evaluate our device: 
{{< img src="/posts/academic-projects/senior_design/testprotocol.png" align="center" title="VE Test Protocol">}}

Here were the non-EDS and the EDS results. The green shows the admissable error range (within 20% in either direction). The black bars are confidence bands determined from the three trials of each that were performed.

{{< img src="/posts/academic-projects/senior_design/nonEDSresult.png" align="center" title="non-EDS Shoulder Results">}}

{{< img src="/posts/academic-projects/senior_design/edsresult.png" align="center" title="EDS Shoulder Results">}}

As such, the design failed as it did not meet the acceptance criteria. It did, however, perform qualitively well and would require further iterations to ensure that the current specifications are set for each muscle fiber. 

#### Validation
Validation was performed with practicing physical therapists at the Jewish Community Center and with physical therapists students. We evaluated which interventions they would perform, and if this device was a satisfactory teaching implement. Although I attended nearly all of the validation sessions, I did not develop the protocol, nor record the results and as such this will be excluded.

Other experiments were done for the course - including FEA analysis, the establishment of a QMS system via greenlight guru, SOPs, and several financial analysis. However, for the purpose of this project, and my contributions, they came through verification and device development mainly. 

## Design Expo Results

#### Design Expo First Semester
We placed 2nd in a design expo fo the Swanson School of Engineering, Bioengineering Divison. We intend to place first next time, and have decided the below improvements, among other, would greatly improve our project and propel us to win. 


* Collecting gyroscopic and position-based data from experts in reducing shoulder subluxations. Then, performing a real-time statistical test to detect whether the user is performing a movement similar to the expert
* Refining the design so everything is cleaner
* Developing a UI such that the stepper motors can be controlled individually, away from the computer and easily
* Allowing for dislocation sensing as well, to help physical therapists get much needed practice reducing dislocations AND subluxations
* Integrating the emotional aspect with our current device. Real-time feedback integrated into our visual novel. Add a gameifying element to show improvement and promote learning


Regardless, we're still proud of our work. 

{{< img src="/posts/academic-projects/senior_design/team_pico.jpg" align="center" title="Team Picture during Expo Award">}}



#### Design Expo Second Semester

The previous excerpt has been kept as it was at the time of writing (last semester). This it to show that we had full intention of improving and winning upon the final semester. Thankfully, we were able to place as best project in the bioengineering category 
{{< img src="/posts/academic-projects/senior_design/bestbioe.jpg" align="center" title="Best Bioegineering Project">}}

and best overall project as well. We were more rehearsed in our delivery and our product was not only functional, but appealing and impressive as well. I'm incredibly proud of our achievement. It took a monumental amount of effort, and I'm humbled by the fact that the judges liked us amidst so many incredible, incredible design projects and teams. Thank you 

{{< img src="/posts/academic-projects/senior_design/bestoverall.jpg" align="center" title="Best OVerall Proejct">}}
