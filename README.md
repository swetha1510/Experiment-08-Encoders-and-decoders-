# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedure

### 1.Using OR gates construct 8:3 Encoder.

### 2.Repeat the same procedure for 3:8 Decoder using AND gates.

### 3.Find RTL logic and Timing diagram for both encoder and decoder.

### 4.End the program.



### PROGRAM 
```
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: SWETHA P
RegisterNumber: 22008542

### ENCODER 

module encoder(d0,d1,d2,d3,d4,d5,d6.d7,a,b,c);
input d0,d1,d2,d3,d4,d5,d6,d7;
output a,b,c;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule

### DECODER

module decoder(a,b,c,d0,d2,d3,d4,d5,d6,d7);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0=(~a&~b&~c),
       d1=(~a&~b&c),
		 d3=(~a&b&c),
		 d4=(a&~b&~c),
		 d5=(a&~b&c),
		 d6=(a&b&~c);
		 d7=(a&b&c);
endmodule
```
### ENCODER

### RTL LOGIC  
![encodertl](https://user-images.githubusercontent.com/120623583/214604316-395a0670-a434-41ab-afcc-5533c2f1725a.png)
  
### DECODER
![decodertl](https://user-images.githubusercontent.com/120623583/214604483-9b3625e5-4205-49f9-a40b-587bae60f28c.png)


### TIMING DIGRAMS  

### ENCODER 
![encodesim (2)](https://user-images.githubusercontent.com/120623583/214604611-6e55cbe7-4813-44f7-aacd-e234f24b5a8c.png)

### DECODER
![decodesim](https://user-images.githubusercontent.com/120623583/214604870-46a268f3-c4f9-4382-a7c9-8fa04083e0d4.png)


### TRUTH TABLE

###ENCODER
![encodetruth](https://user-images.githubusercontent.com/120623583/214605086-3f08d191-9c55-4c90-bbd0-d526d5e36441.png)

###DECODER
![decodetruth](https://user-images.githubusercontent.com/120623583/214605193-b0d3f545-8c33-4c67-9863-11ef1405f927.png)


### RESULTS 
Thus the Encoder and Decoder are designed and the truthtable are verified using quartus software.
