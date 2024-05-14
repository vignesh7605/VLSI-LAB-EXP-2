**SIMULATION AND IMPLEMENTATION OF  COMBINATIONAL LOGIC CIRCUITS**

**AIM:**

 To simulate and synthesis ENCODER, DECODER, MULTIPLEXER, DEMULTIPLEXER, MAGNITUDE COMPARATOR using Vivado 2023.2.

**APPARATUS REQUIRED:**

Vivado 2023.2

**PROCEDURE:**

STEP:1 Start the Vivado, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the Behavioural Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

**ENCODER:**

**LOGIC DIAGRAM:**

![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/6987778/3cd1f95e-7531-4cad-9154-fdd397ac439e)

**VERILOG CODE:**

```
module encoder(d,a,b,c) ;
input [7:0]d;
output a,b,c;
or(a,d[4],d[5],d[6],d[7]);
or(b,d[2],d[3],d[6],d[7]);
or(c,d[1],d[3],d[5],d[7]);
endmodule
```

**OUTPUT:**

![Screenshot 2024-03-09 141737](https://github.com/Dhinesh0024/VLSI-LAB-EXP-2/assets/160568927/789f3e96-629c-4d5c-af76-3192d8efe8fc)


**DECODER:**

**LOGIC DIAGRAM:**

![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/6987778/45a5e6cf-bbe0-4fd5-ac84-e5ad4477483b)

**VERILOG CODE:**

```
module decoder_8(a,b,c,y);
input a,b,c; 
output[7:0]y; 
and gl(y[0],(~a),(~b),(~c)); 
and g2(y[1],(~a),(~b),(c)); 
and g3(y[2],(~a),(b),(~c));
and g4(y[3],(~a),(b),(c));
and g5(y[4],(a),(~b),(~c));
and g6(y[5],(a), (~b), (c));
and g7(y[6], (a), (b), (~c)); 
and g8(y[7], (a), (b), (c));
endmodule
```

**OUTPUT:**

![Screenshot 2024-03-09 143119](https://github.com/Dhinesh0024/VLSI-LAB-EXP-2/assets/160568927/7516940e-abcd-4f9f-b957-32045c0d5ddd)

**MULTIPLEXER:**

**LOGIC DIAGRAM:**

![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/6987778/427f75b2-8e67-44b9-ac45-a66651787436)

**VERILOG CODE:**

```
module mux(a,b,c,d,s0,s1,y);
input a,b,c,d,s0,s1;
output y;
assign y=s1 ?(s0?d:c):(s0?b:a);
endmodule
```

**OUTPUT:**

![mux](https://github.com/Dhinesh0024/VLSI-LAB-EXP-2/assets/160568927/6e35ad75-0ce0-4a15-b4fa-d094ec702889)

**DEMULTIPLEXER:**

**LOGIC DIAGRAM::**

![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/6987778/1c45a7fc-08ac-4f76-87f2-c084e7150557)

**VERILOG CODE:**

```
module demux(in,s0,s1,s2,d0,d1,d2,d3,d4,d5,d6,d7);
input in,s0,s1,s2;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0=(in & ~s2 & ~s1 &~s0),
d1=(in & ~s2 & ~s1 &s0),
d2=(in & ~s2 & s1 &~s0),
d3=(in & ~s2 & s1 &s0),
d4=(in & s2 & ~s1 &~s0),
d5=(in & s2 & ~s1 &s0),
d6=(in & s2 & s1 &~s0),
d7=(in & s2 & s1 &s0);
endmodule
```

**OUTPUT:**

![Screenshot 2024-03-09 145557](https://github.com/Dhinesh0024/VLSI-LAB-EXP-2/assets/160568927/fc1c76a9-da23-4998-bb7e-1da35feb0517)


**MAGNITUDE COMPARATOR:**

**LOGIC DIAGRAM:**

![image](https://github.com/navaneethans/VLSI-LAB-EXP-2/assets/6987778/b2fe7a05-6bf7-4dcb-8f5d-28abbf7ea8c2)

**VERILOG CODE:**

```
module magcomp(a,b,l,g,e);
input [3:0]a,b;
output reg l,g,e;
always @(*)
begin
if(a>b)
begin
     l=1'b0;
     g=1'b1;
     e=1'b0;
end
else if(a<b)
begin
     l=1'b1;
     g=1'b0;
     e=1'b0;
end
else
begin
     l=1'b0;
     g=1'b0;
     e=1'b1;
end
end
endmodule
```

**OUTPUT:**

![Screenshot 2024-03-09 140041](https://github.com/Dhinesh0024/VLSI-LAB-EXP-2/assets/160568927/3e5be226-14ff-462e-8d5b-995a52bf8221)
  

**RESULT:**

Hence ENCODER, DECODER, MULTIPLEXER, DEMULTIPLEXER, MAGNITUDE COMPARATOR are simulated and synthesised using Vivado 2023.2


