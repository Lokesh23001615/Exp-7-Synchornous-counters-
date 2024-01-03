NAME : LOKESH M

REGISTER NUMBER: 23001615
# Exp-6-Synchornous-counters - up counter and down counter 
### AIM:
To implement 3 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED: 
– PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED: 
Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 3 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, three-bit count:

 
 

three-bit “Up” Counter

![up](https://github.com/Lokesh23001615/Exp-7-Synchornous-counters-/assets/144979337/dfd5d2c7-2e0d-4f01-b5dc-19e36560bd45)




## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.

![down](https://github.com/Lokesh23001615/Exp-7-Synchornous-counters-/assets/144979337/3912462d-68b3-42ed-b643-dcc53f57a1d1)


3-bit Count Down Counter
### Procedure
Step 1:Create a new project in Quartus2 software .

Step 2:Name the project as uc for upcounter and dc for down counter.

Step 3:Create a new verilog hdl file in the project file.

Step 4:Name the module declare as dc and uc for down counter and upcounter.

Step 5:Within the module declare input and output variables.

Step 6:Create a loop using if-else with condition parameter as reset.

Step 7:End the loop.

Step 8:End the module



### PROGRAM 
# UP Counter:
```
Module upcounter(clk,a);
input clk;
output reg[3:0];
always @(posedge clk)
begin
a[3]=(a[2]&a[1]&a[0])^a[3];
a[2]=(a[1]&a[0])^a[2];
a[1]=(a[0]^a[1]);
a[0]= ^a[0];
end
endmodule
```
# DOWN Counter:
```
Module downcounter(clk,a);
input clk;
output reg[3:0]a;
always @(posedge clk)
begin
a[3]=(~a[2]&~a[1]&~a[0])^a[3];
a[2]=(~a[1]&~a[0])^a[2];
a[1]=(~a[0]^a[1]);
a[0]=1^a[0];
end
endmodule
```



### RTL LOGIC UP COUNTER AND DOWN COUNTER  
# UP Counter:
![Screenshot 2023-12-30 112138](https://github.com/Lokesh23001615/Exp-7-Synchornous-counters-/assets/144979337/cf7324da-8f7f-419c-93b6-88671a4c9566)



# DOWN Counter:
![Screenshot 2023-12-30 112201](https://github.com/Lokesh23001615/Exp-7-Synchornous-counters-/assets/144979337/99b5a94e-0a2d-425d-82a7-c98154f778af)










### TRUTH TABLE 
# UP Counter:
![Screenshot 2023-12-30 at 13 07 47_8b33cf00](https://github.com/Lokesh23001615/Exp-7-Synchornous-counters-/assets/144979337/31a6013d-d2bf-41df-a286-c9b71e6d48f6)








# DOWN Counter:
![Screenshot 2023-12-30 at 13 08 06_6f0911e1](https://github.com/Lokesh23001615/Exp-7-Synchornous-counters-/assets/144979337/6728f5f4-e4ab-4184-b3f2-3e6b572b2a9e)


### TIMING DIGRAMS FOR COUNTER  

# UP Counter:
![Screenshot](https://github.com/Lokesh23001615/Exp-7-Synchornous-counters-/assets/144979337/940156d1-3105-4aef-b109-d94d3b3a47fd)




# DOWN Counter:
![image](https://github.com/Lokesh23001615/Exp-7-Synchornous-counters-/assets/144979337/785074a4-b65f-45a0-b20f-ebcc296d27ce)







### RESULTS 
Thus synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.
