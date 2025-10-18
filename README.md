# square.c
Aim

To write a C program to generate a square wave of 50 kHz frequency at output pin P1.0 using Timer 0 in Mode 1 of the 8051 microcontroller with a 12 MHz crystal oscillator.

Apparatus Required

  1.Personal Computer
  
  2.Keil µVision Software

Program
```
#include<reg51.h>
sbit pin=P1^0;
main()
{
	P1=0x00;
	TMOD=0x09;
loop:TL0=0xF6;
	  TH0=0xFF;
	  pin=1;
	  TR0=1;
	 while(TF0==0) {}
		 TL0=0xF6;
		 TH0=0xFF;
		 pin=0;
		 while(TF0==0) {}
		goto loop;
}
````

Output
<img width="1920" height="1200" alt="Screenshot (205)" src="https://github.com/user-attachments/assets/6c3cff5b-973b-404e-b693-dfb9b03c775e" />

Result

The C program is successfully executed, and a continuous 50 kHz square wave is obtained at output pin P1.0.
The Timer 0 provides the required delay, and the output pin toggles between logic high and low states repeatedly, forming the desired square waveform.


