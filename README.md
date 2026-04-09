# Amplitude-Modulation-1EVEN
# Amplitude-Modulation

EXP NO: 1	GENERATION AND DETECTION OF AM

AIM:

To generate and detect the amplitude modulation and demodulation u s i n g S C I L A B and to calculate modulation index of AM.

EQUIPMENTS REQUIRED

•	Computer with i3 Processor

•	SCI LAB

THEORY:

Modulation can be defined as the process by which the characteristics of carrier wave are varied in accordance with the modulating wave (signal). Modulation is performed in a transmitter by a circuit called a modulator.
Need for modulation is as follows:
•	Avoid mixing of signals
•	Reduction in antenna height
•	long distance communication
•	Multiplexing
•	Improve the quality of reception
•	Ease of radiation.
Amplitude Modulation is the process of changing the amplitude of a relatively high frequency carrier signal in proportion with the instantaneous value of the modulating signal. The output waveform contains all the frequencies that make up the AM signal and is used to transport the information through the system. Therefore the shape of the modulated wave is called the AM envelope. With no modulating signal the output waveform is simply the carrier signal. Coefficient of modulation is a term used to describe the amount of amplitude change present in an AM waveform. There are three degrees of modulation available based on value of modulation index.
1)	Under modulation :	m<1, Em < Ec
2)	Critical modulation: m-1, Em = Ec
3)	Over modulation:	m>1, Em > Ec



Note: Keep all the switch faults in off position

Algorithm
1.	Define Parameters
First, define the parameters for your signals:
•	Carrier frequency (fc)
•	Modulating signal frequency (fm)
•	Sampling frequency (Fs)
•	Duration of the signal (T)


2.	Create a time vector based on the sampling frequency and duration.
 
3.	Create Modulating Signal
Define the modulating signal (message signal).

4.	Create Carrier Signal
Define the carrier signal.


5.	Perform Amplitude Modulation
Multiply the carrier signal by the modulating signal plus 1 (to ensure the modulation depth).


6.	Plot the Signals
Visualize the modulating, carrier, and modulated signals.


7.	Demodulate the AM Signal
To demodulate, you can use envelope detection. One way is to rectify the signal and then apply a low-pass filter.

8.	Plot the Demodulated Signal
Visualize the demodulated signal.


9.	Compare Signals
Compare the original modulating signal with the demodulated signal. PROCEDURE
•	Refer Algorithms and write code for the experiment.
•	Open SCILAB in System
•	Type your code in New Editor
•	Save the file
•	Execute the code
•	If any Error, correct it in code and execute again
•	Verify the generated waveform using Tabulation and Model Waveform

Program
```
clc;
clear;
close all;

Ac = 7.9;          // Carrier amplitude
Am = 15.8;          // Message amplitude
Fc = 3060;       // Carrier frequency (Hz)
Fm = 306;        // Message frequency (Hz)
Fs = 30600;      // Sampling frequency (Hz)

t = 0:1/Fs:2/Fm; 

// Message signal
E1 = Am * sin(2*%pi*Fm*t);
subplot(4,1,1);
plot(t, E1);
xlabel("Time (s)");
ylabel("Amplitude");
title("Message Signal");
xgrid();

// Carrier signal
E2 = Ac * sin(2*%pi*Fc*t);
subplot(4,1,2);
plot(t, E2);
xlabel("Time (s)");
ylabel("Amplitude");
title("Carrier Signal");
xgrid();

// AM modulated signal
E3 = (Ac + Am*sin(2*%pi*Fm*t)) .* sin(2*%pi*Fc*t);
subplot(4,1,3);
plot(t, E3);
xlabel("Time (s)");
ylabel("Amplitude");
title("AM Modulated Signal");
xgrid();

// Demodulation using Hilbert transform (envelope detection)
analytic_signal = hilbert(E3);
envelope = abs(analytic_signal);
demodulated_signal = envelope - Ac;

subplot(4,1,4);
plot(t, demodulated_signal);
xlabel("Time (s)");
ylabel("Amplitude");
title("Demodulated Signal");
xgrid();

```


Output Waveform
<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/930dec16-8576-4d0a-b14d-4cc7a5b58cf1" />

TABULATION:
<img width="1280" height="677" alt="image" src="https://github.com/user-attachments/assets/c2c71ae5-be6e-498d-a23d-0310375350cb" />



Calculation:

1.	ma (Theory) = am/ac =0.5
2.	ma(Practical) = (Emax-Emin)/(Emax+Emin) =0.486
   
<img width="591" height="1280" alt="image" src="https://github.com/user-attachments/assets/7d80e115-ef06-4830-9611-cef89c94eebe" />




MODEL GRAPH:
 <img width="919" height="1290" alt="image" src="https://github.com/user-attachments/assets/55326c5b-7dd5-4873-aaf6-d219bb7c4420" />

 RESULT:

 Thus the amplitude modulation and demodulation is experimentally done and the output is verified.
 


RESULT:
Thus the amplitude modulation and demodulation is experimentally done and the output is verified.
<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/a2067011-9f00-4f05-b7ad-bec21994ade3" />

