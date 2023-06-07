# Exercise-07-Multiplexer-and-De-multiplexer
### AIM: To implement 4 X1 multiplexer and 1X4 de multiplexer using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## What are Multiplexer and Demultiplexer?
In-network transmission, both the multiplexer and demultiplexer are combinational circuits. A multiplexer selects an input from several inputs then it is transmitted in the form of a single line. An alternative name of the multiplexer is MUX or data selector. A demultiplexer uses one input signal and generates many. So it is known as Demux or data distributor.

## What is a Multiplexer?
The multiplexer is a device that has multiple inputs and single line output. The select lines determine which input is connected to the output, and also increase the amount of data that can be sent over a network within a certain time. It is also called a data selector.

The single-pole multi-position switch is a simple example of a non-electronic circuit of the multiplexer, and it is widely used in many electronic circuits. The multiplexer is used to perform high-speed switching and is constructed by electronic components.

![image](https://user-images.githubusercontent.com/36288975/170912485-73c395c7-23c0-4e78-a53d-a2f0d07d9662.png)
          Figure-01 multiplexer block diagram 

Multiplexers are capable of handling both analog and digital applications. In analog applications, multiplexers are made up of relays and transistor switches, whereas in digital applications, the multiplexers are built from standard logic gates. When the multiplexer is used for digital applications, it is called a digital multiplexer.

4-to-1 Multiplexer
The 4X1 multiplexer comprises 4-input bits, 1- output bit, and 2- control bits. The four input bits are namely 0, D1, D2, and D3, respectively; only one of the input bits is transmitted to the output. The o/p ‘q’ depends on the value of control input AB. The control bit AB decides which of the i/p data bit should transmit the output. The following figure shows the 4X1 multiplexer circuit diagram using AND gates. For example, when the control bits AB =00, then the higher AND gates are allowed while remaining AND gates are restricted. Thus, data input D0 is transmitted to the output ‘q”
![image](https://user-images.githubusercontent.com/36288975/170912568-3598c60a-5035-41f3-b0c4-ccedba13aca5.png)


Figure2 4X1 multiplexer 
If the control input is changed to 11, then all gates are restricted except the bottom AND gate. In this case, D3 is transmitted to the output, and q=D0. If the control input is changed to AB =11, all gates are disabled except the bottom AND gate. In this case, D3 is transmitted to the output, and q = D3. The best example of a 4X1 multiplexer is IC 74153. In this IC, the o/p is the same as the i/p. Another example of a 4X1 multiplexer is IC 45352. In this IC, the o/p is the compliment of the i/p


## What is Demultiplexer?
De-multiplexer is also a device with one input and multiple output lines. It is used to send a signal to one of the many devices. The main difference between a multiplexer and a de-multiplexer is that a multiplexer takes two or more signals and encodes them on a wire, whereas a de-multiplexer does reverse to what the multiplexer does.
![image](https://user-images.githubusercontent.com/36288975/170912606-a30e4b74-1726-4430-b245-2c3c3d9c232d.png)
Figure 3 De-multiplexer 
1-4 Demultiplexer
The 1-to-4 demultiplexer comprises 1- input bit, 4-output bits, and control bits. The 1X4 demultiplexer circuit diagram is shown below.![image](https://user-images.githubusercontent.com/36288975/170912683-00fb746a-1d45-4023-91d1-3a70b841073c.png)

![image](https://user-images.githubusercontent.com/36288975/170912741-7cbd52af-7e0d-4be3-b5c6-6fb9c4eca7c9.png)

Figure4 1X4 De-multiplexer 
The i/p bit is considered as Data D. This data bit is transmitted to the data bit of the o/p lines, which depends on the AB value and the control i/p.

When the control i/p AB = 01, the upper second AND gate is permitted while the remaining AND gates are restricted. Thus, only data bit D is transmitted to the output, and Y1 = Data.

If the data bit D is low, the output Y1 is low. IF data bit D is high, the output Y1 is high. The value of the output Y1 depends upon the value of data bit D, the remaining outputs are in a low state.

If the control input changes to AB = 10, then all the gates are restricted except the third AND gate from the top. Then, data bit D is transmitted only to the output Y2; and, Y2 = Data. . The best example of 1X4 demultiplexer is IC 74155.

 
 
### Procedure
step1: Create a project with required entities.

step2: Create a module along with respective file name for both Multiplexer and De-multiplexer.

step3: Run the module and get the respective RTL outputs.

step4: Create university program(VWF) for getting timing diagram.

step5: Give the respective inputs for timing diagram and obtain the results.


### PROGRAM 
```
/*
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: RASIKA.M
RegisterNumber:  212222230117
*/
```
### 4-1 MULTIPLEXER
```
module mux(i0, i1, i2, i3, s0, s1, y);
input i0, i1, i2, i3, s0, s1;
output y;
wire p, q, r, s, s0c, s1c;
not(s0c, s0);
nor(s1c, s1);
and(p, s0c, s1c, i0);
and(q, s0c, s1, i1);
and(r, s0, s1c, i2);
and(s, s0, s1, i3);
or(y, p, q, r, s);
endmodule
```
### 1-4 DEMULTIPLEXER
```
module demux(y0, y1, y2, y3, s0, s1, i);
input s0, s1, i;
output y0, y1, y2, y3;
wire s0c, s1c;
nor(s0c, s0);
nor(s1c, s1);
and(y0, i, s0c, s1);
and(y1, i, s0c, s1c);
and(y2, i, s0, s1c);
and(y3, i, s0, s1);
endmodule
```
### RTL LOGIC  
### MULTIPLEXER
![image](https://github.com/Aishwarya-sankar/Exercise-07-Multiplexer-and-De--multiplexer/assets/121418444/74e3ecaf-eeca-4751-ad97-f462a09dfd08)
### DEMULTIPLEXER
![image](https://github.com/Aishwarya-sankar/Exercise-07-Multiplexer-and-De--multiplexer/assets/121418444/2c5aa3de-e595-4272-8b98-d72c80a5bad8)

### TIMING DIGRAMS  
### MULTIPLEXER
![image](https://github.com/Aishwarya-sankar/Exercise-07-Multiplexer-and-De--multiplexer/assets/121418444/6d369922-be15-46d9-9b59-c4b2483606c0)
### DEMULTIPLEXER
![image](https://github.com/Aishwarya-sankar/Exercise-07-Multiplexer-and-De--multiplexer/assets/121418444/764d4506-8ddf-4277-8c50-77f0d1abc803)

### TRUTH TABLE 
### MULTIPLEXER
![image](https://github.com/Aishwarya-sankar/Exercise-07-Multiplexer-and-De--multiplexer/assets/121418444/877a2f4a-7678-479f-924c-2896e8162e6a)
### DEMULTIPLEXER
![image](https://github.com/Aishwarya-sankar/Exercise-07-Multiplexer-and-De--multiplexer/assets/121418444/0d4bfe69-b121-491f-beb8-688a9ac53a0f)

### RESULTS 
Thus the implementation of Multiplexer and Demultiplexer are verified.
