# SYNCHRONOUS_UP_COUNTER
AIM:

To implement 4 bit synchronous up counter and validate functionality.

SOFTWARE REQUIRED:

Quartus prime

THEORY

4 bit synchronous UP Counter

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/8138ecb3-a317-4c80-9a98-67c18ad73ba7" />


Each flip-flop in this circuit will be clocked at exactly the same time. The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.” Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse. Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time. The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed. However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

PROGRAM

```

module synchronous_up_counter(
    input  wire clk,
    input  wire rst,      // synchronous reset
    output reg  [2:0] q
);

always @(posedge clk) begin
    if (rst)
        q <= 3'b000;
    else
        q <= q + 1'b1;
end

endmodule
```

Developed by: Karthi V

RegisterNumber: 25017522

RTL LOGIC UP COUNTER:
[RTL Viewer.pdf](https://github.com/user-attachments/files/24172208/RTL.Viewer.pdf)



TIMING DIAGRAM FOR IP COUNTER:
[wave (1).pdf](https://github.com/user-attachments/files/24172214/wave.1.pdf)



RESULTS:
We got the successful output
