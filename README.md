# 32Bit-ALU_Synthesis

## Aim:

Synthesize 32 Bit ALU design using Constraints and analyse area and Power reports.

## Tool Required:

Functional Simulation: Incisive Simulator (ncvlog, ncelab, ncsim)

Synthesis: Genus

### Step 1: Getting Started

Synthesis requires three files as follows,

◦ Liberty Files (.lib)

◦ Verilog/VHDL Files (.v or .vhdl or .vhd)

### Step 2 : Performing Synthesis

The Liberty files are present in the library path,

• The Available technology nodes are 180nm ,90nm and 45nm.

• In the terminal, initialise the tools with the following commands if a new terminal is being
used.

◦ csh

◦ source /cadence/install/cshrc

• The tool used for Synthesis is “Genus”. Hence, type “genus -gui” to open the tool.

• Genus Script file with .tcl file Extension commands are executed one by one to synthesize the netlist.
### Code:
```
module alu_32bit_tb_case;
reg [31:0]a;

reg [31:0]b;

reg [2:0]f;

wire [31:0]y;

alu_32bit_case test2(.y(y),.a(a),.b(b),.f(f));

initial

begin

a=32'h00000000;

b=32'hFFFFFFFF;

#10 f=3'b000;

#10 f=3'b001;

#10 f=3'b010;

#10 f=3'b100;

end

initial

#50 $finish;

endmodule
```

#### Synthesis RTL Schematic :
![Screenshot (140)](https://github.com/user-attachments/assets/755eba6b-5515-4b60-a998-610dcf9bb21e)

#### Area report:
![Screenshot (141)](https://github.com/user-attachments/assets/56c1b419-128b-4c1c-9beb-0e627233d240)

#### Power Report:
![Screenshot (142)](https://github.com/user-attachments/assets/da3fba5e-b0d1-4b2d-9492-3cabea0244b7)

#### Result: 

The generic netlist of 32 bit ALU  has been created, and area, power reports have been tabulated and generated using Genus.
