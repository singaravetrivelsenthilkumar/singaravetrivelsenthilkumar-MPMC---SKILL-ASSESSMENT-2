# 1-ms-Delay-Using-Timer-0-Mode-1

## AIM:
To write an Assembly Language Program (ALP) in 8051 to calculate the sum of 5 numbers stored sequentially in memory and store the result in another memory location.

## APPARATUS REQUIRED:
1.Keil µVision Software / 8051 Simulator

2.Personal Computer

## ALGORITHM:
1.Start the program.

2.Load the TMOD register with 01H to select Timer 0 in Mode 1 (16-bit mode).

3.Load the TH0 and TL0 registers with initial values 0FCH and 066H respectively to get approximately 1 ms delay.

4.Set the TR0 bit to start Timer 0.

5.Continuously check the TF0 (Timer 0 overflow flag) until it becomes 1.

6.When TF0 = 1, the delay is completed.

7.Clear TR0 to stop the timer.

8.Clear TF0 for future use.

9.End the program.

## PROGRAM:
```
ORG 0000H
MOV TMOD, #01H
MOV TH0, #0FCH
MOV TL0, #066H
SETB TR0
WAIT: JNB TF0, WAIT
CLR TR0
CLR TF0
END
```

## OUTPUT:

<img width="1920" height="1079" alt="Screenshot 2025-11-03 115148" src="https://github.com/user-attachments/assets/e1d3f981-2de3-4897-8bcf-c76c70aaa665" />



## RESULT:
The program has been successfully executed.
