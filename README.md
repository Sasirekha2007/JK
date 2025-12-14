AIM:

To implement JK flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

JK Flip-Flop



JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.


<img width="634" height="407" alt="Screenshot 2025-12-14 165354" src="https://github.com/user-attachments/assets/a49e1d1a-a59c-475a-9948-7710f4f01beb" />

This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.


<img width="488" height="379" alt="Screenshot 2025-12-14 165401" src="https://github.com/user-attachments/assets/6962d886-4e84-4bb5-b26b-1dfaa268c841" />


& Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
<img width="644" height="568" alt="Screenshot 2025-12-14 165408" src="https://github.com/user-attachments/assets/2fe91970-19eb-4b90-995b-b2f1d1628235" />



By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

<img width="337" height="263" alt="Screenshot 2025-12-14 165419" src="https://github.com/user-attachments/assets/b361d8e8-f05b-4c76-9253-c6e86112f846" />


The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)



PROGRAM
module JK (
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


 Developed by:B.SASIREKHA
 
 RegisterNumber: 25015734

RTL LOGIC FOR FLIPFLOPS

TIMING DIGRAMS FOR FLIP FLOPS

RESULTS
