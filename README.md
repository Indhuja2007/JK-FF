# JK-FF
AIM:

To implement JK flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED: Quartus prime

THEORY

JK Flip-Flop

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

1
This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

2
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State

3
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

4
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

## PROGRAM:
```
module jk_flip_flop (
    input  wire clk, rst, J, K,
    output reg  Q
);
    always @(posedge clk or posedge rst) begin
        if (rst)
            Q <= 1'b0;        // Reset
        else begin
            case ({J,K})
                2'b00: Q <= Q;        // Hold
                2'b01: Q <= 1'b0;     // Reset
                2'b10: Q <= 1'b1;     // Set
                2'b11: Q <= ~Q;       // Toggle
            endcase
        end
    end
endmodule
```
IMAGE: 
<img width="1920" height="1080" alt="Screenshot (73)" src="https://github.com/user-attachments/assets/4f27fff7-06df-4ca6-9a94-7a68e874db71" />

WAVEFORM:
<img width="1488" height="634" alt="JK-FF" src="https://github.com/user-attachments/assets/de4015f3-2f25-49be-8046-0b038601a44e" />


NAME: INDHUJA K

REF NO: 25018219

RESULT: Implementation of JK flipflop using verilog and validating their functionality using their functional tables is executed and the output is verified successfully.

