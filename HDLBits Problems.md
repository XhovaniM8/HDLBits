# Getting Started

We're going to start with a small bit of HDL to get familiar with the interface used by HDLBits. Here's the description of the circuit you need to build for this exercise:

Build a circuit with no inputs and one output. That output should always drive 1 (or logic high).

```verilog
module top_module( output one );

// Insert your code here
    assign one = [fixme];

endmodule
```

MY SOLUTION

```verilog
module top_module( output one );

// Insert your code here
    assign one = 1;

endmodule
```

# Zero

Build a circuit with no inputs and one output that outputs a constant 0

Now that you've worked through the previous problem, let's see if you can do a simple problem without the hints.

HDLBits uses Verilog-2001 ANSI-style port declaration syntax because it's easier to read and reduces typos. You may use the older Verilog-1995 syntax if you wish. For example, the two module declarations below are acceptable and equivalent:  

```verilog
module top_module ( zero );
    output zero;

endmodule
```

_**Expected solution length:** Around 1 line._

```verilog
module top_module ( zero );
    output zero;

	assign zero = 0;
	
endmodule
```
# Simple Wire

``` verilog
module top_module( input in, output out );
    assign out = in;
endmodule
```

# Four Wires
```verilog
module top_module( 
    input a,b,c,
    output w,x,y,z );

    assign w = a;
    assign x = b;
    assign y = b;
    assign z = c;
endmodule
```
# 7458 Chip
![[Pasted image 20231107205844.png]]
```verilog
module top_module ( 
    input p1a, p1b, p1c, p1d, p1e, p1f,
    output p1y,
    input p2a, p2b, p2c, p2d,
    output p2y );

    wire a = p2a & p2b;
    wire b = p2c & p2d;
    
    wire c = p1c & p1b & p1a;
    wire d = p1f & p1e & p1d;
    
    assign p2y = a | b;
    assign p1y = c | d;
    

endmodule
```