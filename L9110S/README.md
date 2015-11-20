# L9110S / H-bridge Stepper Motor Dual DC motor Controller Board for Arduino

## Images
![Image1](images/l9110s.jpg?raw=true)

## Features
* onboard two the L9110S motor control chip
* the module can simultaneously drive two DC motors or a 4-wire 2-phase stepper motor
* the 800mA continuous current output capability per channel
* Low static work current
* Power supply voltage: DC 2.5-12V
* Each channel has 800mA continuous current output
* Low saturation pressure drop
* TTL/CMOS output level compatible, can be connected directly to the CPU
* Output built-in clamping diode, apply to the perceptual load
* Control and drive integrate in IC
* Have pin high pressure protection function
* Working temperature: 0-80 ℃
* Size: 29.2(mm)x23(mm)
 
## Test code

    #include<reg51.h>
    
    sbit MOTOR_A_1 = P0 ^ 0;
    sbit MOTOR_A_2 = P0 ^ 1;
    sbit MOTOR_B_1 = P0 ^ 2;
    sbit MOTOR_B_2 = P0 ^ 3;
    
    void delay(unsigned long cnt)
    {
        while(cnt--);
    }
    
    void forward(void)
    {
        MOTOR_A_1 = 1;
        MOTOR_A_2 = 0;
        MOTOR_B_1 = 1;
        MOTOR_B_2 = 0;
    }
    
    void backward(void)
    {
        MOTOR_A_1 = 0;
        MOTOR_A_2 = 1;
        MOTOR_B_1 = 0;
        MOTOR_B_2 = 1;
    }
    
    void main(void)
    {
        EX0 = 1;
        EX1 = 1;
        EA = 1;
        while(1)
            {
                forward();
                delay(30000);
                backward();
                delay(30000);
            }
    }
