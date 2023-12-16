# Vehicle Wiper control system using Simulink
![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.001.jpeg)

Project Requirements : Root Level![ref1]

**Execution Scheduler (10ms) Wiper Motor PWM Duty Cycle![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.003.png)![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.004.png)![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.005.png)**

**Wiper Mode Control** 

**Rain Sensor Error System**

**Wiper Activation Flag**

**Wiper Speed Required**

Project Requirements : System Inputs![ref1]

**Wiper Mode of operations![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.006.png)**

**0 :off**

**1 :Automatic 2 :Low Speed 3 :High Speed![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.007.png)![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.008.png)![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.009.png)**

**Rain Sensor Error**

**0 :No Error 1 :Error![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.010.png)![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.011.png)**

**Wiper Speed Required in Automatic Mode**

**8 speeds from 0 to 7![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.012.png)**

Project Requirements : System Outputs![ref1]

**Wiper Motor PWM Duty Cycle Wiper Activation Flag![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.013.png)![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.014.png)**

**PWM command to  0 :Wiper not activated**

**the wiper motor**

**1 :Wiper activated**


Project Requirements : control system logic![ref1]

If (**Wiper Mode** = off)  then

**Wiper Motor PWM Duty Cycle** = 0%

Else If (**Wiper Mode** = Low Speed)  then

**Wiper Motor PWM Duty Cycle** = 40%

Else If (**Wiper Mode** = High Speed)  then

**Wiper Motor PWM Duty Cycle** = 70%

Else If (**Wiper Mode** = Auto)  then

If (Rain Sensor Error = true)  then

**Wiper Motor PWM Duty Cycle** = 0%

Else

Select a **PWM value** from [0% 40% 50% 55% 60% 65% 70%] based on speed required [0 1 2 3 4 5 6 7] Smooth motor PWM transitions between different speeds

Simulink System Modelling: Root level![ref1]

![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.015.jpeg)

Wiper Motor Subsystem![ref1]

![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.016.jpeg)

Wiper Motor Subsystem : Modelling the logic ![ref1]

![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.017.jpeg)Wiper Motor Subsystem : Automatic Signal Smoothing:![ref1]

![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.018.jpeg)

Model Testing: Setting up the Solver![ref1]

![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.019.jpeg)

Model Testing: Creating Input signals scenario using Signal Editor![ref1]

![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.020.png)

![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.021.jpeg)

C  Code Generation![ref1]

` `![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.022.png)![](Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.023.png)

[ref1]: Aspose.Words.15a5199c-304e-43e4-9413-47e100a1cef7.002.png
