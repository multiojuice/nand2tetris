# nand2tetris
My implementation and progress in the nand2tetris project. This project was created by the great people at [nand2tetris](https://www.nand2tetris.org/copy-of-about). The project is focused around self-learning and figuring things out through trial and error. The creators provide a skeleton of the project with the tools you will need to complete it.

This project consists of 13 [sub-projects](./projects/) that each have a focus and purpose in the end result. The end result is to build a computer and on top of it, write an OS and language to be compiled on this computer. In this README I will go through each sub-project and explain what was created in that section, and what I learned.

Read more about the project [here](https://www.nand2tetris.org)


# One
In this sub-project, the sole focus was to create all the simple starter gates so we can start building chips for the computer. I started with only a Nand gate, and past that, all the other gates were built either by Nand gates or from the gates I already built with the Nand gates. By "built", I mean described in a file using hdl, or [Hardware Description Language](https://en.wikipedia.org/wiki/Hardware_description_language). Once the hdl file is complete, I run it through [the Hardware Simulator](./tools/HardwareSimulator.sh), and compare it to a test file that is provided by the nand2tetris team. You can see all the gates [here](./projects/01)


# Two
Section two was a direct step up from the first section, I used the gates I described in section one to construct more complex chips. The main part of section two was to construct an ALU, or [Arithmetic logic unit](https://en.wikipedia.org/wiki/Arithmetic_logic_unit). The nand2tetris gives a truth table, and tells you to go at it. After I wrote the other chips in this section, I had to use those to implement the ALU. Those chips were different types of Adders and Incrementers. I have never done any sort of hardware development, minus some small work with Arduinos, and this is a tad bit lower level than that, so honestly I was a bit concerned getting into this section. However, just through logical thinking and debugging, my ALU gets the correct outcome for every given input. I am sure that there is a better way to implement the ALU compared to my implementation, but I am more interested in the later sections, so I was just thrilled I got this as quick as I did.

### Stuff
All the chips are operating with 16 bit arrays and are using the [Two's Complement](https://en.wikipedia.org/wiki/Two%27s_complement) to represent positive and negative integers.


# Three
RAM! This section was all about creating the components in the computer that store data. More specifically, a bit, register, then several RAM chips that differ in size. As stated earlier, our registers are 16 bits wide. To create all these parts, I used the previously created chips and gates, and combined them with a Data Flip Flop chip, or [DFF](https://en.wikipedia.org/wiki/Flip-flop_(electronics)). The coolest part of this section was figuring out how data persists within a bit, how bits scale up to registers, and the most interesting, RAM chips. Figuring out how I can find the address, and change the value of a register in a RAM chip was surprisingly more straight forward than I initially thought it would be. Simply just using bit strings, DMux and Mux gates, we can find, and change the correct info.
