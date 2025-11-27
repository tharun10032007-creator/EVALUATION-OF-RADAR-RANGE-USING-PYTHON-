# EVALUATION-OF-RADAR-RANGE-USING-PYTHON-

__Aim__:

To calculate the maximum range of a radar system using the Radar Range Equation and verify the results 
through Python programming.

__Theory__:

The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum 
range at which a radar can detect a target. It is given by:

<img width="573" height="442" alt="image" src="https://github.com/user-attachments/assets/ba374d30-d11f-41e5-a4fc-a42dde71d8e7" />

__Procedure__:

1. Set Up the Python Environment: Ensure that Python is installed on your system. You can use 
Anaconda for managing Python packages and environments, or any other Python IDE of your choice. 
2. Import Necessary Libraries: Import the math library in Python. 
3. Define the Radar Range Equation Function: Create a function to calculate the maximum range using 
the Radar Range Equation. 
4. Input Parameters for the Radar System: Define the input parameters such as transmitted power, 
transmitter gain, receiver gain, radar frequency, radar cross section, and minimum detectable power. 
5. Calculate the Maximum Range: Use the function to calculate the maximum range of the radar. 
6. Execute the Program: Run the Python script to calculate and display the maximum range of the radar.


 ___Program__:
 ```
clc
clear;
close;

Pt = 1000;
G = 40;
lambda = 0.05;
sigma = 10;
pi4 = (4*%pi)^3;

R = linspace(1e3, 200e3, 500);
Pr_R = (Pt .* G^2 .* lambda^2 .* sigma) ./ (pi4 .* R.^4);
figure(1);
Pr_R_dB = 10 .* log10(Pr_R);
plot(R/1000, Pr_R_dB);
xlabel("Power Received");
ylabel("Range");

Pt_values = linspace(100, 10000, 500);
R_fixed = 50e3;
Pr_Pt = (Pt_values .* G^2 .* lambda^2 .* sigma) ./ (pi4 .* R_fixed.^4);
figure(2);
plot(Pt_values, Pr_Pt);
xlabel("Power Received");
ylabel("Power Transmitted");

G_values = linspace(5, 60, 500);
Pt_fixed = 3000;
Pr_G = (Pt_fixed .* G_values.^2 .* lambda^2 .* sigma) ./ (pi4 .* R_fixed.^4);
figure(3);
plot(G_values, Pr_G);
xlabel("Power Received");
ylabel("Gain");
```
__Tabulation__:
![WhatsApp Image 2025-11-22 at 08 41 02_e617d062](https://github.com/user-attachments/assets/3e4be87a-09de-4257-8843-33cf187c2342)



 __Output__:
   
<img width="1838" height="965" alt="Screenshot 2025-11-18 112705" src="https://github.com/user-attachments/assets/573f497e-b974-4e7b-9362-d92e2212ac0c" />

<img width="1841" height="972" alt="Screenshot 2025-11-18 112807" src="https://github.com/user-attachments/assets/898e5c14-b1d7-4171-96a0-62d8f2073c15" />

<img width="1835" height="963" alt="Screenshot 2025-11-18 112857" src="https://github.com/user-attachments/assets/7ac4e949-ac32-4229-8ff6-b2d90f0467df" />

 __Result__:
 The maximum radar detection range was calculated using the Radar Range Equation, and the Python implementation validated the result. Thus, radar range evaluation was successfully completed.
 
   




