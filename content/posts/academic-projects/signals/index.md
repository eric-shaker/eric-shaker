---
title: "Using Fourier/Laplace Transforms to Perform Signal Manipulations"
date: 2021-08-26T08:06:25+06:00
description: Projects related to coursework taken in a signals and systems course
menu:
  sidebar:
    name: Using Fourier Transforms and Convolution to Perform Signal Manipulations
    identifier: signals
    parent: academic-projects
    weight: 6
hero: bkg.jpg
tags: ["Markdown","Content Organization","Multi-lingual"]
categories: ["Basic"]
---

### Overview
This section is meant to highlight alot of the skills I learned in signals and systems, a course that familiarized me with some really basic signal manipulations. In all honesty, its just to show off some fun code I made that I had no where else to put. Its not that special, but this is my website so you don't get a choice.

I put the code below, but for reference, we can imagine the arterial system as a circuit. This "circuit" has many of the properties of a normal circuit. It has capacitors, resistors, and inductors. Therefore, it requires the integration of a second order LCCDE (linear constant coeffecient differential equation) which becomes a third order LCCDE because of the difference in peripheral and central blood pressure (think pressure at the fingerstip versus that right next to the aorta - completely different). Cc and Cp below represent the compliance Lc ineartance (pressure needed to accelerate blodo) and Rp (peripheral resistance to flow). Circuit model is shown below. This is what is calculated for. 

{{< img src="/posts/academic-projects/signals/eq1.jpg" align="center" title="eq1">}}

Below, the Bode plot and impulse response. And below that, we vary the model parameters (specifically SV, T, Cc, and Rp) 50% in both directions to notice the difference on the resulting signal we get. This is principally important in adequate arterial modelling.
{{< img src="/posts/academic-projects/signals/pic2.png" align="center" title="pic2">}}
{{< img src="/posts/academic-projects/signals/pic1.png" align="center" title="pic1">}}
### Code

```
clear
clc



%****************************Project 2*************************************
%Section 1
%To find the system function, we first manipulate our given equation using
%laplace transform techniques and properties 
%This includes obtaining the transfer function as the quotient of P(s) and
%Q(s) where Q is representative of the characteristic polynomial
%The following is the resulting expression we obtain 
%
%(Rp*s)/((Lc*Rp*Cc*Cp*s^3)+(Lc*Cc*s^2)+Rp*(Cp + Cc)*s +1)

%**************************************************************************
%Section 2
%To accomplish this, we load in our input values and our transfer
%function, and use the functions listed in the problem statement

Cc = 1.4;
Cp = 0.2;
Lc = 0.025;
Rp = 1.2;

ans = zeros(1,1000); %Initialization of an empty vector (array)
for(s = 1:1000)
    ans(s) = (Rp*s)/((Lc*Rp*Cc*Cp*s^3)+(Lc*Cc*s^2)+Rp*(Cp + Cc)*s +1);
end

figure(1)
plot(1:length(ans),ans)  %Just plotting the results of the function



numerator = [Rp];
denominator = [ Lc * Rp * Cc * Cp, Lc * Cc, Rp * ( Cp + Cc), 1];
sys = tf(numerator, denominator); %Use of the sys function which is neccessary to use the attached funtions
[H,W] = freqs(numerator, denominator, logspace(-1,1)); %No logspace? 
figure(2)
subplot(2,1,1)
plot(log(W),abs(H));
title('Magnitude');
subplot(2,1,2)
plot(log(W),unwrap(angle(H)));
title('Phase');
figure(3)
bode(sys)
figure(4)
impulse(sys)
% The variation within the graph is characteristic of an underdampened
% system. We can tell by looking at the impulse response, which is the
% system response to an impulse. The decaying oscillatory behavior of the
% output signal is indicative of an underdampened system, which is found
% using the impulse() function when fed in an input containing the system
% function


%%
%**************************************************************************
%Section 3

sampling_interval = 0.001;
u_t = zeros(1,(20 * 1/sampling_interval));
for i = 1:20
    u_t(1000*i) = 1;
end

SV = 80; %ml
T = 1; %seconds in beat length

v_t = zeros(1,(20* 1/sampling_interval));
for i = 1:((0.3 * sqrt(T))/T*length(v_t))
    v_t(i) = SV / (0.3 * sqrt(T));
end
 
result = conv(u_t, v_t);
w = conv(u_t,v_t);
figure(5)
x_axis = linspace(0,T, length(result));
subplot(1,3,1)
plot(x_axis,result)
title("Question 3 Answer");
subplot(1,3,2)
plot(linspace(0,T,length(u_t)),u_t);
title("Question 2 u_t");
subplot(1,3,3)
plot(linspace(0,T,length(v_t)),v_t);
title("Question 3 v_t");

%**************************************************************************
%Section 4

Pp = lsim(tf(numerator,denominator),w,linspace(0,21*T,length(w)));
figure(6)
plot(Pp(10000:end)),title('Pp')
%Lsim most likely functions by integrating the given system and plotting an
%(almost) infinitely small section of the function at a given time point in
%the time domain and repeating that process. Similar to find the
%convolution with a delta dirac function at every timepoint T possible


%**************************************************************************
%Section 5
%Creating a function for this will save much time - start by finding output
%w.r.t Hc(s) and Ql(s)

Cc = 1.4;
Cp = 0.2;
Lc = 0.025;
Rp = 1.2;

numerator = [Lc*Rp*Cp Lc Rp]; %reinstantiating these variables 
denominator = [Lc*Rp*Cc*Cp Lc*Cc Rp*(Cp + Cc) 1];
Pc = lsim(tf(numerator,denominator),w,linspace(0,21*T,length(w)));
figure(7)
plot(Pc(10000:end)),title('Pc')
%The results are reasonably what is to be expected
%Shape has differed though which is understandable considering the
%differences in the actual transform function pre-inverse laplace transform


%%
%**************************************************************************
%Section 6


simulator(1.5,1,1,1,'SV +50%',1);
simulator(0.5,1,1,1,'SV -50%',2);
simulator(1,1.5,1,1,'T +50%',3);
simulator(1,0.5,1,1,'T -50%',4);
simulator(1,1,1.5,1,'Cc +50%',5);
simulator(1,1,0.5,1,'Cc -50%',6);
simulator(1,1,1,1.5,'Rp +50%',7);
simulator(1,1,1,0.5,'Rp -50%',8);






function result = simulator(SV_multiplier,T_multiplier,Cc_multiplier,Rp_multiplier,plot_title,subplot_num)
Cc = 1.4;
Cp = 0.2;
Lc = 0.025;
Rp = 1.2;
SV = 80;    
T = 1;

numerator = [Rp * Rp_multiplier];
denominator = [ Lc * Rp*Rp_multiplier * Cc*Cc_multiplier * Cp, Lc * Cc*Cc_multiplier, Rp*Rp_multiplier * ( Cp + Cc*Cc_multiplier), 1];
T = T*T_multiplier;
t = [0:0.001:T];
Ts = 0.3*sqrt(T);
ts= [0:0.001:20*T];
q = zeros(size(t));
q(t<Ts) = SV_multiplier*SV/Ts;


pulsetrain = zeros(size(ts));
for i = 1:20
    pulsetrain(ts==(i*T)) = 1;
end

w = conv(pulsetrain,q);

Pp = lsim(tf(numerator,denominator),w,linspace(0,21*(T*T_multiplier),length(w)));
figure(8)
subplot(8,1,subplot_num);
plot(Pp(10000:end));
title(plot_title)
% subplot(8,1, subplot_num+1)
% plot(
end
```
### Acknowledgement
Sorry the acknowledgement is so low down, I should've thought ahead. Thanks to Dr.Muakkamala for making the project idea. All the calculations, plots, code is mine but he provided a really cool problem statement. Thanks again!

