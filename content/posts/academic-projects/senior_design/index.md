---
title: "Bioengineering Senior Design: Developing A Feedback-Oriented Trainer for Reducing Shoulder Subluxations "
date: 2022-12-01T08:06:25+06:00
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

#### Final Iteration 
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

#### Role as Team Lead 

The most I've learned personally from this experience is in the management of people. There were several issues that originated at the start of the year which were alleviated through better management, and understanding our specific group dynamic, and general group characteristics.

Among those, these are the most resounding takeaways
- Look towards yourself first in failure. When a group member failed to produce results that I asked for, I redirected the issue to myself. I realized I wasn't communicating the expectations clearly and since then, those issues have been remediated
- Understand your group mates' goals from the beginning. We have a wide array of students, with different goals. This caused particular conflict when choosing a project topic. After speaking one-on-one with group members, I realized that most of them were oriented towards performing well in the class, and achieving something that was more technical, and had less likelihood of being implemented in the real world. This would position them better when applying in the engineering industry, versus my goal of medical school where the engineering would be in the backdrop. This was one of the main reasons we changed our project topic
- Problem identification is too commonly overlooked. In the beginning, we would generalize problems like "PTs don't get experience treating EDS". We wouldn't ask 
    - "Is the principal issue unawareness/inability to identify EDS, or lack of knowledge on how to treat those patients?"
    - "Do PTs make an effort to get better at treating EDS? If so, do they have proper equipment?"
    - "Do PTs have ANY experience reducing a dislocation on a patient before their first experience? If not, why are the outcomes alright with non-EDS patients but hazardous when applied to EDS patients?"
- Don't be afraid to delegate. Early assignments were dominated by group members who got to work early, and had initiative. This pattern was very unfair. Clearly delegating responsibilities for each week and explicitly asking for a progress report was greatly beneficial
- Create an agenda/schedule for everything. I was not used to this prior to this semester. However group meetings would frequently devolve into unfocused, although project-oriented, conversations that drained time from important topics. 
- Emphasize transparency. When delegating, we ran into issues with certain group members not being aware of other's actions. Furthermore, a lack of communication and cross-talk, with respect to code, 3D printer files, manufacturing ideas, was very inconvenient. Still have not come up with a solution. We tried transitioning to text over GroupMe, calling over the phone, and better file sharing to limited benefit. More meetings that are technically oriented is likely the solution



#### Design Expo
We placed 2nd in a design expo fo the Swanson School of Engineering, Bioengineering Divison. We intend to place first next time, and have decided the below improvements, among other, would greatly improve our proejct and propel us to win. 


* Collecting gyroscopic and position-based data from experts in reducing shoulder subluxations. Then, performing a real-time statistical test to detect whether the user is performing a movement similar to the expert
* Refining the design so everything is cleaner
* Developing a UI such that the stepper motors can be controlled individually, away from the computer and easily
* Allowing for dislocation sensing as well, to help physical therapists get much needed practice reducing dislocations AND subluxations
* Integrating the emotional aspect with our current device. Real-time feedback integrated into our visual novel. Add a gameifying element to show improvement and promote learning


Regardless, we're still proud of our work. 

{{< img src="/posts/academic-projects/senior_design/team_pico.jpg" align="center" title="Team Picture during Expo Award">}}