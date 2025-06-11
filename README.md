# comp311-lab-3-solved
**TO GET THIS SOLUTION VISIT:** [Comp311 Lab 3 Solved](https://mantutor.com/product/comp311-its-time-to-put-our-knowledge-of-combinational-logic-sequential-logic-timing-and-memory-to-the-test-in-part-1-of-this-lab-you-will-be-designing-a-4-bit-alu-that-can-perform-addition-s/)


---

**For Custom/Order Solutions:** **Email:** mantutorcodes@gmail.com  

*We deliver quick, professional, and affordable assignment help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;115128&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;Comp311 Lab 3 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
It’s time to put our knowledge of combinational logic, sequential logic, timing, and memory to the test! In part 1 of this lab you will be designing a 4 bit ALU that can perform addition, subtraction, and logical operations (AND and OR). In part 2 of this lab you will be designing a digital RAM component that can read in a memory address, and either write or read to/from that address.

That’s right: no k-maps in this lab :raised_hands: :partying_face:!

In the next lab we’ll be able to put these concepts together, so don’t worry if they seem a little disjointed right now!

Part 1: Constructing a 4-bit ALU

To recap:

An arithmetic logic unit (ALU) is a digital circuit used to perform arithmetic and logic operations. It represents the fundamental building block of the central processing unit (CPU) of a computer

Most of the operations of a CPU are performed by one or more ALUs, which load data from input registers. A register is a small amount of memory that is a component of a CPU. In this lab we’ll be using 3 registers (A, B, and C). A and B will be the register that the ALU reads from, and C will be the register that the ALU writes to.

Additionally, a set of control bits tells the ALU what operation to perform on the data, and the ALU stores the result in output register C.

In this portion of the lab you’ll get experience working with several components such as register, an ALU, and a clock. As we learned in class timing is needed to perform ALU operations. For example, writing the values to registers A &amp; B will take one clock cycle (the first rising edge), and then writing the output of the ALU operation to register C will take 1 clock cycle (the second rising edge). See the image below:

Thus, when you construct your ALU you should observe a time delay from when the input is read from registers A and B, and the output is written to register C. The ALU time delay should be much less than the one clock cycle (or clock period). Ask yourself: why don’t we need a clock cycle (in our representation) to perform the operation that happens inside the ALU?

To-Do:

Your task is to succesfully implement a working ALU that can performing addition, subtraction, logical AND, and logical OR. The ALU should function based on the control table below:

|Math | Sub | Function | |—|—-|—-| |1 |0 |Addition | |1 |1 |Subtraction | |0 |0 | Logical AND | |0 |1 | Logical OR |

Let’s get started. If you open the ‘Lab03_ALU.dig’ file you will see a that all input/output components have been provided for you. Let’s go through them:

In the top left you will see two components “CLK” and “Enable”. These two components are crucial and must be connected to each of the registers in the circuit (12 in total). They should be connected to “C” and “En” respectively on each register. The “Enable” bit is what allows data to be written to the register, e.g., if it is set to 1, then the next rising-edge clock event the register will store the data. The enable bit is the same as the “in” bit we discussed in class. The CLK component is our clock.

To the right of these components you will see eight inputs (A0 – A3 and B0 – B3) which represent the four bits that go to register A and four bits that go to register B. Under them, you will see eight registers (four for A, and four for B). We could have simply used two 4-bit registers, but spliting it up in eight 1-bit registers simplifies the circuit creation on your end. The input component should be connected to the “D” input on the register, and “Q” is the output of the register. These eight “Q” outputs will be inputs to the ALU.

On the left-hand side you will see two additional inputs “Math” and “Sub”. These are the control bits that will be used inside your ALU. Remember, the function of your ALU is determined by these two control bits, and the function table above. Hint: If you remember from class, these control bits are the input to multiplexers within the ALU that determine what result is passed to the output register. Lastly, at the bottom, you will see four registers, and four outputs (C0 – C3) that represent the output from the ALU.

After you complete the part, go through this checklist to see if your ALU is up to spec:

Does your ALU perform operations and write to the C register only when the enable bit is 1? If writing occurs when enable is 0, you’ve done something wrong.

Does your ALU correctly perform binary addition, subtraction, logical AND, and logical OR with the input from the A and B registers? Example: If A is 0000, B is 1111, math is 0, sub is 1, and enable is 1, then on the first rising edge your ALU should read the inputs A and B, and on the next rising edge, your ALU should write “1111” to registers C0 – C3. This was a logical OR operation.

When you change input values, does it take 2 clock cycles to change the output to the C register? Remember we need a full clock cycle to write information to registers A and B from inputs A and B, and then a full clock cycle to write to register C. Ask yourself: why don’t we need a clock cycle (in our representation) to perform the operation that happens inside the ALU?

You can simulate rising and falling edges yourself by right-clicking the CLK component, and unchecking the “start real-time clock” button.

Now when you simulate the circuit, when you press the CLK component that is a rising edge and when you press again that is a falling edge. Here’s what you should see when you simulate:

First start the circuit

Then turn on the enable bit and the control bits that you want selected

Then set your input bits A0-A3 and B0-B3 to whatever you want them to be

When you press the CLK component once (rising edge), you should see that the data from the input registers has traveled into your ALU

(the wires will light up bright green)

When you press the CLK component again (falling edge), nothing should happen

When you press the CLK component again (rising edge), the output should have been written to the C register.

Notice how the whole operation took 2 rising edges, or in other words, 2 clock cycles. Once you get this working hopefully it helps you understand how timing works within an ALU. You can then recheck the “start real-time clock” button on the CLK component, to automate the rising and falling edges.

Once you think your ALU is working, commit your changes, and move on to the next part of the lab!

Part 2: Constructing an Efficient 4-bit ALU

Two clock cycles?? Horrific! Blasphemous! Not in today’s world of efficiency! :scream: :exploding_head:

In this part of the lab you will edit your circuit from part 1 to run operations (reading from A &amp; B registers, and writing to C register) within ONE clock cycle. To do this please make a new Digital file in the same directory as your previous file called ‘Lab03_ALU_Efficient.dig’ and copy your entire circuit from the previous part.

You’ll need to make one small (and when I say small, I mean small. Don’t go changing your entire circuitry from the previous section) change to your previous circuit to support this efficiency.

Hint: Notice how in the previous part, on step 5, we “do nothing” on the falling edge. How inefficient….

Notice how one small change can cut our operational time in half! Incredible! :astonished:

Once you have your operations working correctly within 1 clock cycle, commit your changes and move on to the next part of the lab!

Part 3: Constructing a Digital RAM Component

Time to completely switch gears. In this part of the lab we are going to implement a a digital RAM component. What is RAM?

Random access memory (RAM) is one of the most important components in determining your systemâ€™s performance. RAM gives applications a place to store and access data on a short-term basis. It stores the information your computer is actively using so that it can be accessed quickly.

RAM is memory, and in our lab we will be implementing a circuit that allows you to both read from memory, and write to memory. In our case, our RAM chip will support 4 bits. What does this mean?

Every piece of information that is stored in RAM is at a specific Memory Address. This address is what is used to read/write data to and from.

For example, if I want to store the number “2” in memory, I need to tell my RAM chip where to store that “2”, this is the memory address. Conversely, if I wanted to read data from a specific memory address, I could tell the RAM chip to give me the data that is stored in a specific memory address. For a 4-bit RAM, we can have 16 unique binary combinations of 4 digits, and thus we can have 16 unique memory addresses.

Open the file ‘Lab03_RAM.dig’, let’s go through it:

In this circuit we have 3 main components:

1. A “Memory Address Register” or MAR. This is the leftmost register that you see in this circuit. The purpose of the MAR is to provide the memory address to the RAM chip for either a write instruction or a read instruction. The data that the MAR sends to the RAM chip determines where the RAM will read/write in memory. For instance if the MAR sends 0000 to the RAM chip, the RAM chip knows to either read or write to memory address 0000.

2. The RAM chip. This is the center chip between the two registers. This chip is what controls reading and writing to the 16 memory addresses.

3. The “Memory Data Register” or MDR. The MDR is only used when you want to lookup or read a value from memory. For instance if the MAR sends 0000 to the RAM chip, and you want to lookup the value stored in memory address 0000, then the RAM chip will send the data in memory address 0000 to the MDR.

Notice how even though we are constructing a 4-bit RAM, there are only 2 registers, not 8 like in part 1 of this lab. This is because each register is set to accept 4 input bits, and output 4 bits as well. The RAM is also configured to accept and output 4 bits. You can see this by ctrl-clicking the components and seeing that the data bits are set to 4.

We also have a slew of input components. Let’s go through them:

1. ADR: This is a 4-bit input (ctrl-click and see that the data bits are set to 4) that is responsible for specifying the memory address you want to read from or write to. When you simulate the circuit and click on this input you’ll actually be able to change the binary value of the 4 bits.

2. ADRRegEnable: This a 1-bit input that specifies whether the MAR is active. If 1, the MAR can be written to, if 0 it cannot

3. Write: This is a 1-bit input that specifies whether we want to write data to memory. If 1, we are writing to memory, if 0 we are not writing.

4. Lookup: This is a 1-bit input that specifies whether we want to read data from memory. If 1, we want to read from memory, if 0 we do not.

5. Data: This is a 4-bit input that determines what value will be written to memory. This component does not matter if write is set to 0.

6. DataRegEnable: This ia a 1-bit input that specifies whether the MDR is active. If 1, the MDR can be written to, if 0 it cannot.

7. CLK: This is our clock, remember that writing can only only on rising clock edges.

Lastly we have the output component on the right side that will display the value of the MDR if we are reading from RAM.

1. The ADRRegEnable input should always be set to 1 (we should always have the option of writing to the memory address register)

2. When ‘Write’ is 1, the 4 bit input from ‘Data’ should be written to the memory address specified by ‘ADR’. You can check this during the simulation by clicking on the RAM component, which will show the 16 memory address’ and their respective data. Remember that reading/writing should only happen on rising clock edges, you can simulate this by doing what you did in part 1 with the clock input.

3. When ‘Lookup’ is 1, and DataRegEnable is 1, the output component should display the data value in memory at the memory address specified by ADR.

Let’s walk through scenarios 1 &amp; 2 to see if your circuit is working.

Scenario 1 (Writing)

1. Start the simulation

2. The CLK should be pulsing

3. Click on ADR and set the value to 3, either by typing 3 in the textbox or checking the corresponding binary boxes at the bottom 4. Set ADRRegEnable to 1

5. Set Write to 1

6. Click on the Data component and set the value to 5, either by typing 5 in the textbox or checking the corresponding binary boxes at the bottom

7. Click on the RAM component, you should see that in address 0x3, the value is 5.

8. Stop the simulation

Scenario 2 (Reading) 1. Repeat steps 1-8 from Scenario 1 above 2. Set Write to 0 3. Set Lookup to 1 4. Set DataRegEnable to 1 5. The output component should display 5 6. Stop the simulation

Notice how there’s a slight delay when trying to display values, that’s how the timing works in a RAM chip, remember we can only write on rising clock edges

If this is working congratulations! You’ve constructed a simple 4-bit RAM module! You now have the ability to store data in memory and access it using control bits that you specify.

To ensure your RAM module is working correctly, input the following data at the corresponding addresses given this address/data table (the values are in hex, your input components use binary, you need to convert, ie: for address 0x0 the correspoding ADR input should be 0000):

|Address | Data | |—|—-| |0x0 |0x3 | |0x1 |0x7 | |0x2 |0x6 | |0x3 |0xA | |0x4 |0xE | |0x5 |0x2 | |0x6 |0x1 | |0x7 |0x4 | |0x8 |0x6 | |0x9 |0xD | |0xA |0xB | |0xB |0x2 | |0xC |0xF | |0xD |0x4 | |0xE |0xE | |0xF |0x9 |

Once you have input this data, click on the RAM chip to see that it was all stored correctly.

To ensure you will pass the autograders tests, try to see the values in the output component by using the lookup input (make sure Write is 0)! You should be able to set ADR to each of the 16 addresses, and see the corresponding value in the output component (following the steps from Scenario 2).

In the next lab we’ll actually be connecting our ALU and our RAM module to take the information that was processed by the ALU and store it in memory! Once you’ve finished this part of the lab save &amp; commit your changes!

When you finish everything save and commit all your changes!

Submit your assignment

Assignment submissions will be made through GradeScope.

1. Submit modifications using the commit Github Desktop instructions.

2. Update remote (origin) repository using the push Github Desktop instructions.

3. Go to the COMP 311 course in GradeScope and click on the assignment called Lab 03.

5. You should see a list of your public repositories. Select the one named lab-03-yourname and submit it.

6. Your assignment should be autograded within a few seconds and you will receive feedback.
