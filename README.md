## Name:Nidhish B
## Register Number:23014111
## Experiment:06-Synchornous-counters-up counter and down counter

### AIM:
To implement 3 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:
– PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED: 
Quartus prime
### THEORY:

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

## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 3-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.

### Procedure:

1) Create a new project in Quartus2 software .
2) Name the project as uc for upcounter and dc for down counter.
3) Create a new verilog hdl file in the project file.
4) Name the module declare as dc and uc for down counter and upcounter.
5) Within the module declare input and output variables.
6) Create a loop using if-else with condition parameter as reset.
7) End the loop.
8) End the module

### PROGRAM :
## Up Counter
~~~
module up_counter(clk,q1,q2,q3);
input clk;
output reg q1,q2,q3;
always@(posedge clk)
begin
q3=(q1&q2)^q3;
q2=q1^q2;
q1=1^q1;
end 
endmodule
~~~

## Down Counter
~~~
module COUNTER(clk,q1,q2,q3);
input clk;
output reg q1,q2,q3;
always@(posedge clk)
begin
q3=((~q2)&(~q1))^q3;
q2=(~q1)^q2;
q1=1^q1;
end
endmodule
~~~

### RTL LOGIC UP COUNTER AND DOWN COUNTER :

## Up Counter

![image](https://github.com/Nidhish055/Exp-7-Synchornous-counters-/assets/145979818/11e1bd85-c509-4097-a563-7b65f735a9f7)



## Down Counter

![293361964-aea0bb57-ab87-4549-9720-c26f35609f2d](https://github.com/Nidhish055/Exp-7-Synchornous-counters-/assets/145979818/c045365f-fbe2-458c-90c3-21813ae83c2f)


### TIMING DIGRAMS FOR COUNTER :

## Up Counter

![293361908-1fa2cb7e-3c27-4c4e-a7be-71bfbca01bb6](https://github.com/Nidhish055/Exp-7-Synchornous-counters-/assets/145979818/291ad076-0141-4f35-a31a-db2c3bf1f421)


## Down Counter

![293361994-169f6ffa-5e86-4212-9451-25c5981e77b0](https://github.com/Nidhish055/Exp-7-Synchornous-counters-/assets/145979818/d5e295ba-bd33-4d27-92d1-240d9c71b6a6)


### TRUTH TABLE :

## Up Counter

![293351925-d5e809ac-c593-4471-b9cf-25ea4d19f930](https://github.com/Nidhish055/Exp-7-Synchornous-counters-/assets/145979818/27d4a62f-c76c-424f-8291-0f8642b7bf40)


## Down Counter

![293352160-a1819724-71b9-4f9a-9600-445d2de493ad](https://github.com/Nidhish055/Exp-7-Synchornous-counters-/assets/145979818/87fbbee4-08b9-4c55-a1ee-9845b894c9fe)


### RESULTS :
Thus synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.
