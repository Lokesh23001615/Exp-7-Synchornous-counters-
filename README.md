# NAME : ASHWIN AKASH M
# REGISTER NUMBER: 23009906
# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

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

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
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
![upcounter](https://github.com/Lokesh23001615/Exp-7-Synchornous-counters-/assets/144979337/5241a9fc-c687-42f7-afd8-57ee829da377)


# DOWN Counter:
![downcnt](https://github.com/Lokesh23001615/Exp-7-Synchornous-counters-/assets/144979337/72a079b9-a6b5-433f-9042-b5291ddf62fb)




### TIMING DIGRAMS FOR COUNTER  

# UP Counter:
![upcounterwwf](https://github.com/Lokesh23001615/Exp-7-Synchornous-counters-/assets/144979337/30c1885f-d282-4472-9f2b-1eb8c3dd8e2e)

# DOWN Counter:
![downcounter](https://github.com/Lokesh23001615/Exp-7-Synchornous-counters-/assets/144979337/346c8c94-f8b2-422b-a2ad-c2ebc62e742e)



### TRUTH TABLE 
# UP Counter:
![down](https://github.com/Lokesh23001615/Exp-7-Synchornous-counters-/assets/144979337/6ce654da-fbc1-4e3a-8d82-667514531b06)




# DOWN Counter:


![Up](https://github.com/Lokesh23001615/Exp-7-Synchornous-counters-/assets/144979337/b5483183-a686-480f-8d06-3ae313dd7334)




### RESULTS 
Thus synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.
