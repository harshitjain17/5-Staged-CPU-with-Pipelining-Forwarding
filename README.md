# Disclaimer: This work is strictly for my personal use. If you are a CMPEN 331 student, you are solely responsible for any kind of plagiarism.

# 5-Staged-CPU-with-Pipelining-Forwarding
Designed using Xilinx Vivado Design Package, a Verilog-based 5-stage 32-bit pipelined and forwarded CPU, which handles Load word, Add, and Jump MIPS format instructions with Forwarding and Writeback units to handle data hazards, reduce possible stalls, and improve performance by 10%.

The project involved the implementation which ensures the data hazards are avoided given instructions that can induce them. The processor works by having stages, which is the instruction fetch (IF), instruction decode (ID), execution (EXE), memory access (MEM), and write back (WB), as shown on Figure below. Between each stage are registers that take in the outputs of the stage before it and delivers the values for the inputs for the stage after it. It is storing the previous stage’s output values so it can feed it to the next stage. This is beneficial since it is needed in order to have an implementation that uses several clock cycles per instruction. As one instruction is in the IF stage, another instruction is in the ID stage and another in the EXE stage. This allows five instructions to be running at the same time, which allows our program to run faster, taking advantage of parallelism. This is possible due to the values being stored in the registers so they can be used by the next stages.
# Here is the detailed circuit of the pipelined CPU:
![CPU](https://user-images.githubusercontent.com/90932614/167201901-41212fba-c8e7-4a57-bf97-423bc7f0b27e.jpg)
