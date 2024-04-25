# Digital logical Gates
## Some Definations
- Signals:- these are physical quantities which vary over time
- Binary logic deals with binary variables and with operations that assume a logical meaning. It is used to describe, in algebraic or tabular form, the manipulation and processing of binary information. 
- The manipulation of binary information is done by logic circuits called gates. Gates are blocks of hardware that produce signals of binary 1 or 0 when input logic requirements are satisfied.
## Digital vs Analog signal
Digital and analog signals are two different types of signals used to represent and transmit information in various electronic systems. Here's a breakdown of their differences and the benefits of one over the other:

**Digital Signals:**
1. **Representation**: Digital signals represent information using discrete values, typically binary (0s and 1s). Each value is called a bit. Digital signals are represented as sequences of these discrete values.
2. **Accuracy**: Digital signals are less susceptible to noise and interference compared to analog signals. They can be transmitted over longer distances without significant loss of quality.
3. **Processing**: Digital signals can be easily processed, manipulated, and analyzed using digital circuits and algorithms. They allow for precise control and manipulation of information.
4. **Storage**: Digital signals can be stored and reproduced without degradation. This makes digital storage mediums (such as hard drives, flash drives, and optical discs) reliable for long-term storage of data.
5. **Compression**: Digital signals can be compressed efficiently, allowing for the storage and transmission of large amounts of information in a compact form. This is essential for multimedia applications such as audio and video streaming.

**Analog Signals:**
1. **Representation**: Analog signals represent information using continuous values that vary over time. These values can be any real number within a certain range. Examples include voltage, current, and frequency.
2. **Resolution**: Analog signals have infinite resolution, meaning they can represent an infinite number of values within their range. This allows for smooth and continuous representation of information.
3. **Natural Representation**: Many real-world phenomena, such as sound, light, and temperature, are inherently analog in nature. Analog signals provide a natural representation of these phenomena without the need for conversion.
4. **Sensitivity**: Analog signals can capture subtle variations in input signals with high sensitivity, making them suitable for applications where fine details need to be preserved.

**Benefits of Digital over Analog:**
1. **Noise Immunity**: Digital signals are less susceptible to noise and interference, making them more reliable in noisy environments.
2. **Ease of Processing**: Digital signals can be easily processed, manipulated, and analyzed using digital circuits and algorithms, allowing for complex operations and functions.
3. **Storage and Reproduction**: Digital signals can be stored and reproduced without degradation, making them suitable for long-term storage and transmission.
4. **Compression**: Digital signals can be compressed efficiently, allowing for the storage and transmission of large amounts of information in a compact form.
**Benefits of Analog over Digital:**
1. **Resolution**: Analog signals have infinite resolution, allowing for smooth and continuous representation of information without quantization effects.
2. **Natural Representation**: Analog signals provide a natural representation of many real-world phenomena without the need for conversion, preserving the fidelity of the original information.
3. **Sensitivity**: Analog signals can capture subtle variations in input signals with high sensitivity, making them suitable for applications where fine details need to be preserved, such as in audio and video recording.
In summary, the choice between digital and analog signals depends on the specific requirements of the application. While digital signals offer advantages in terms of noise immunity, processing capabilities, and storage efficiency, analog signals excel in providing high resolution, natural representation, and sensitivity to subtle variations in input signals.

## Basic Digital circuit
### What is it 
A digital circuit is a circuit that operates using digital signals, which are discrete signals represented by binary numbers (0s and 1s). These circuits are designed to process, store, and transmit digital information using a combination of logic gates and other digital components.

Digital circuits are built from electronic components such as transistors, diodes, resistors, and capacitors. These components are interconnected to form logic gates, flip-flops, registers, counters, and other digital elements. The behavior of digital circuits is determined by the logical operations performed on binary inputs to produce binary outputs.

In a digital system there are only a few basic operations performed, irrespective of the complexities of the system.  The basic operations are AND, OR, NOT, and FLIP-FLOP(which is a basic memory element used to store binary information (one bit is stored in one FLIP-FLOP)).

**An integrated circuit (IC) is a small semiconductor chip that contains electronic components such as transistors, diodes, resistors, and capacitors, as well as interconnections between them, all fabricated onto a single piece of semiconductor material. Integrated circuits are also commonly referred to as microchips or simply chips.**
### Combinational vs Sequential circuit 
Combinational and sequential circuits are two fundamental types of digital circuits, each with distinct characteristics and applications:

**Combinational Circuits:**

1. **Definition**: Combinational circuits produce outputs solely based on the current input values, without any memory or feedback. The outputs are determined by the logical combination of the input signals.

2. **Behavior**: The outputs of a combinational circuit are purely a function of the current input values. There is no notion of time dependency or sequential behavior. These circuits are essentially "stateless" in that they do not have memory elements to retain information.

3. **Examples**: Combinational circuits include logic gates (AND, OR, NOT, etc.), multiplexers, demultiplexers, decoders, encoders, and adders.

4. **Applications**: Combinational circuits are used for tasks such as logical operations, arithmetic operations, data routing, data conversion, and encoding/decoding. They are suitable for applications where the output depends solely on the current input values and there is no need for memory or sequential behavior.

**Sequential Circuits:**

1. **Definition**: Sequential circuits contain memory elements (such as flip-flops or latches) that allow them to store information internally. The outputs of a sequential circuit depend not only on the current input values but also on the circuit's previous state.

2. **Behavior**: Sequential circuits exhibit time dependency and sequential behavior. The outputs are determined by the current input values as well as the circuit's internal state, which is influenced by past inputs and outputs.

3. **Examples**: Sequential circuits include flip-flops, registers, counters, shift registers, finite state machines (FSMs), and memory units.

4. **Applications**: Sequential circuits are used in applications where past history or sequential behavior is important, such as in digital clocks, microprocessors, memory units, control systems, and communication protocols. They are capable of storing and processing data over time, making them essential for tasks requiring memory or sequential logic.

In summary, combinational circuits produce outputs solely based on the current input values, without any memory, while sequential circuits incorporate memory elements to retain past information, resulting in outputs that depend on both current inputs and past states. Both types of circuits have unique characteristics and are used in various digital systems based on the specific requirements of the application.
![](../../statics/Pasted%20image%2020240301070837.png)

### Basic operation
![](../../statics/Pasted%20image%2020240301071351.png)


#### **AND Gate**:
   - Definition: An AND gate is a digital logic gate that produces a high (binary 1) output only when all of its inputs are high (binary 1). Otherwise, it produces a low (binary 0) output.
   - Symbol: Usually represented by the symbol "&" or a triangle with the inputs on the sides and the output at the apex.
   - Boolean expression: The output \(Y\) of an AND gate with inputs \(A\) and \(B\) is given by \(Y = A \times B\).
![](../../statics/Pasted%20image%2020240301071934.png)
![](../../statics/Pasted%20image%2020240301071946.png)
#### **OR Gate**:
   - Definition: An OR gate is a digital logic gate that produces a high (binary 1) output if at least one of its inputs is high (binary 1). It produces a low (binary 0) output only if all inputs are low.
   - Symbol: Often represented by the symbol "∨" or a rounded shape with the inputs on the sides and the output at the apex.
   - Boolean expression: The output \(Y\) of an OR gate with inputs \(A\) and \(B\) is given by \(Y = A + B\).
![](../../statics/Pasted%20image%2020240301071959.png)
#### **NOT Gate (Inverter)**:
   - Definition: A NOT gate, also known as an inverter, is a digital logic gate that produces an output that is the logical negation of its input. It converts a high input to a low output and vice versa.
   - Symbol: Represented by a triangle with a small circle at the input side.
   - Boolean expression: The output \(Y\) of a NOT gate with input \(A\) is given by \(Y = \overline{A}\).
![](../../statics/Pasted%20image%2020240301072033.png)
#### **NAND Gate**:
   - Definition: A NAND gate is a digital logic gate that produces a low (binary 0) output only when all of its inputs are high (binary 1). Otherwise, it produces a high (binary 1) output.
   - Symbol: Usually represented by an AND gate followed by a small circle (inversion) at the output.
   - Boolean expression: The output \(Y\) of a NAND gate with inputs \(A\) and \(B\) is given by \(Y = \overline{A \times B}\).
![](../../statics/Pasted%20image%2020240301072339.png)
![](../../statics/Pasted%20image%2020240301072816.png)
#### **NOR Gate**:
   - A NOR gate is a digital logic gate that produces a high (binary 1) output only when all of its inputs are low (binary 0). It produces a low (binary 0) output if at least one input is high.
   - Symbol: Often represented by an OR gate followed by a small circle (inversion) at the output.
   - Boolean expression: The output \(Y\) of a NOR gate with inputs \(A\) and \(B\) is given by \(Y = \overline{A + B}\).
![](../../statics/Pasted%20image%2020240301073001.png)
#### **XOR Gate (Exclusive OR)**:
   - Definition: An XOR gate is a digital logic gate that produces a high (binary 1) output if the number of high inputs is odd. It produces a low (binary 0) output if the number of high inputs is even.
   - Symbol: Represented by a curved line with inputs on both sides and the output at the apex.
   - Boolean expression: The output \(Y\) of an XOR gate with inputs \(A\) and \(B\) is given by \(Y = A \oplus B\), where \(\oplus\) denotes XOR operation.
![](../../statics/Pasted%20image%2020240301073023.png)
These logical gates serve as the basic building blocks of digital circuits, allowing for the manipulation and processing of binary data in various electronic systems.

# Boolean algebra
The number of gates and the number of input terminals for the gates required for the realization of a
logical expression, in general, get reduced considerably if the expression can be simplified. Therefore, the simplification of logical expression is very important as it saves the hardware required to design a specific system
### Approaches to design combinational circuit
The two approaches to the design of combinational circuits that you've described represent different methodologies for achieving the desired logic functionality. Let's explore each approach in more detail:

1. **Traditional Method**:
   - In the traditional method, the design process involves simplifying the given Boolean expression or truth table using standard methods such as Karnaugh maps, Boolean algebra, or Boolean simplification techniques.
   - Once the expression is simplified, it is implemented using basic logic gates such as AND, OR, NOT, NAND, NOR, XOR, and XNOR gates.
   - The simplified expression leads to a circuit design that typically consists of a combination of these basic logic gates interconnected to achieve the desired logic function.
   - This approach requires expertise in Boolean algebra and logic simplification techniques and often results in circuits with a minimal number of gates, making them efficient in terms of cost and space.
- The following methods can be used to simplify the Boolean function:
	1. Algebraic method,
	2. Karnaugh map technique,
	3. Variable entered aping (VEM) technique, and
	4. Quino-McCluskey method.
2. **Direct Use of Complex Logic Functions in MSI/LSI**:
   - In this approach, the design process skips the step of simplifying the logical expression or truth table. Instead, complex logic functions available in Medium Scale Integrated Circuits (MSI) or Large Scale Integrated Circuits (LSI) are directly utilized.
   - MSI and LSI components contain pre-designed, ready-to-use logic functions such as multiplexers, decoders, encoders, adders, subtractors, and comparators.
   - Designers select appropriate MSI or LSI components based on the required logic functions without necessarily simplifying the logic expression beforehand.
   - This approach can simplify the design process and reduce design time, as designers can leverage pre-designed and pre-optimized complex logic functions.
   - However, it may lead to less efficient use of resources compared to the traditional method, as the selected MSI or LSI components may include unnecessary logic elements or functionalities.

In summary, the traditional method involves simplifying the logical expression before implementation using basic logic gates, whereas the direct use of complex logic functions in MSI or LSI skips the simplification step and utilizes pre-designed logic functions directly. Both approaches have their advantages and drawbacks, and the choice between them depends on factors such as design complexity, resource constraints, and design goals.

### Boolean Algebra intro
Boolean algebra is a mathematical discipline that deals with the manipulation and analysis of logical expressions and functions.deals with binary values, where variables and expressions can take on only two possible values: true (often represented as 1 or "high") and false (often represented as 0 or "low").

# Combinational Circuit
## Design procedure of CC
The design procedure of a combinational circuits starts from the verbal outline of the
problem and ends in a logic circuit diagram. The procedure involves the following steps:
1. The problem is stated.
2. The input and output variables are assigned letter symbols.
3. The truth table that defines the relationship between inputs and outputs is derived.
4. The simplified Boolean functions for each output are obtained.
5. The logic diagram is drawn.

## Adder (Example of arithemetic circuit)
In many computers and other types of processors, adders are used to calculate addresses, similar operations and table indices in the ALU and also in other parts of the processors. 

### Types 
#### Half adder
A combinational circuit that performs the arithmetic addition of two bits is called a halfadder. One that performs the addition of three bits (two significant bits and a previous carry) is called a full-adder.
![](../../statics/Pasted%20image%2020240302071058.png)
The input variables of a half-adder are called the augend and addend bits. The output variables the sum and carry
#### Full adder
A full adder is a combinational circuit used in digital electronics to perform addition of two binary numbers. Unlike a half adder, which can only add two single bits, a full adder can also take into account a carry bit from a previous addition operation, allowing it to add three bits: two bits from the numbers being added (typically denoted as x and y), and a carry-in bit (denoted as z).
![](../../statics/Pasted%20image%2020240302071643.png)

## Subtractor 
Subtractor circuits take two binary numbers as input and subtract one binary number
input from the other binary number input. Similar to adders, it gives out two outputs,
difference and borrow (carry-in the case of Adder).
### Half subtractor 
Half subtractor is a combination circuit with two inputs and two outputs (difference and borrow). It produces the difference between the two binary bits at the input and also produces an output (Borrow) to indicate if a 1 has been borrowed. In the subtraction (AB), A is called as Minuend bit and B is called as Subtrahend bit.
![](../../statics/Pasted%20image%2020240302071845.png)

### Full Subtractor
The disadvantage of a half subtractor is overcome by full subtractor. The full subtractor is a combinational circuit with three inputs A,B,C and two output D and C'. A is the 'minuend', B is 'subtrahend', C is the 'borrow' produced by the previous stage, D is the difference output and C' is the borrow output.
![](../../statics/Pasted%20image%2020240302072009.png)

## Decoder
A decoder is a combinational circuit in digital electronics that takes binary-coded inputs and converts them into a corresponding set of output signals. Each unique combination of input bits corresponds to a specific output signal.
Used to convert binary to other codes :
1. Binary to octal
2. Binary to Hexa
3. Binary to Decimal

***The decoders presented in this section are called n-to-m-line decoders, where m ≤ 2n. Their purpose is to generate the 2n (or fewer) binary combinations of the n input variables. A decoder has n inputs and m outputs and is also referred to as an n x m decoder.***
![](../../statics/Pasted%20image%2020240302075608.png)

here for each input combination  a single output line is active
### NAND Decoder
Some decoders are constructed with NAND instead of AND gates. Since a NAND gate produces the AND operation with an inverted output, it becomes more economical to generate the decoder outputs in their complement form. 

By using NAND gates, the need for separate inverters to generate output complements is eliminated. This simplifies the overall circuit design and reduces the number of components required, resulting in a more economical solution.
![](../../statics/Pasted%20image%2020240302075544.png)

### Decoder expansion
There are occasions when a certain-size decoder is needed but only smaller sizes are available. When this occurs it is possible to combine two or more decoders with enable inputs to form a larger decoder
![](../../statics/Pasted%20image%2020240302080727.png)

## Encoder
An encoder is a digital circuit that performs the inverse operation of the decoder. An encoder has 2n (or less) input lines and n output lines. The output lines generate the binary code corresponding to the input value
![](../../statics/Pasted%20image%2020240302080911.png)
## Multiplexer
It is a combinational circuit that has 2<sup>n</sup> input lines and single output line
it is a electronic switch that connect 1 out of n input to output
it is functionally complete , all boolean function can be realised using one multiplexer without any other gates
![](../../statics/Pasted%20image%2020240303072829.png)
![](../../statics/Pasted%20image%2020240303072849.png)
## De-multiplexer
A demultiplexer, often abbreviated as "demux," is a digital circuit or device used in digital electronics and telecommunications. It takes a single input signal and directs it to one of several possible output lines based on the state of its control inputs.
![](../../statics/Pasted%20image%2020240303073053.png)

Demultiplexers are essentially the opposite of multiplexers. While multiplexers combine multiple input signals into a single output, demultiplexers take a single input and distribute it to multiple outputs.

Demultiplexers are commonly used in various applications, including:

1. Data transmission: In digital communication systems, demultiplexers are used to route individual data streams from a single transmission line to multiple receivers.

2. Memory systems: Demultiplexers can be used to select specific memory locations or address lines in memory devices.

3. Display systems: In display technology, demultiplexers help in selecting individual segments or pixels in a display matrix.

4. Address decoding: Demultiplexers are used to decode address lines in microprocessor systems, enabling the selection of specific peripheral devices or memory locations.

Demultiplexers come in various configurations, such as 1-to-2, 1-to-4, 1-to-8, etc., depending on the number of output lines they have. They are essential components in digital circuits and play a crucial role in routing and managing data and signals.

![](../../statics/Pasted%20image%2020240303073205.png)

# Sequential Logic
## Intro
A sequential circuit is an interconnection of flip-flops and gates. The gates by themselves constitute a combinational circuit, but when included with the flip-flops, the overall circuit is classified as a sequential circuit.
![](../../statics/Pasted%20image%2020240303073627.png)

## Latch and flip flop
Latches and flip-flops are both sequential logic circuits used in digital electronics to store binary data. They serve similar functions but have some key differences in their operation and behavior.

**1. Latch:**

- A latch is a basic memory element that stores one bit of data.
- It operates transparently, meaning it continuously updates its output based on the input as long as the enable signal is active.
- Latches can be level-sensitive or edge-sensitive. Level-sensitive latches respond to the input as long as the enable signal remains in a certain state (e.g., high or low). Edge-sensitive latches respond to a specific edge transition (e.g., rising or falling edge) of the enable signal.
- The most common type of latch is the SR latch (Set-Reset latch), which has two inputs: S (set) and R (reset). When S is high and R is low, the output is set to 1; when S is low and R is high, the output is reset to 0; when both S and R are low, the latch maintains its previous state; and when both S and R are high, it enters an invalid state.

**2. Flip-Flop:**

- A flip-flop is a more complex memory element that also stores one bit of data.
- It has a clock input in addition to the data input, which allows it to change its state only at specific clock transitions.
- Flip-flops are edge-triggered devices, meaning they capture and store input data only at the rising or falling edge of the clock signal.
- Common types of flip-flops include D flip-flops, JK flip-flops, and T flip-flops, each with its specific behavior and applications.
- For example, in a D flip-flop, the input data (D) is captured and stored at the rising or falling edge of the clock signal, depending on the flip-flop's configuration. The stored data remains unchanged until the next clock transition.

**Key Differences:**

- Latches are level-sensitive and continuously update their output based on the input, while flip-flops are edge-triggered and store data only at specific clock transitions.
- Latches are simpler and require fewer components, making them suitable for simpler applications, while flip-flops provide more precise timing control and are commonly used in more complex sequential circuits.

In summary, while both latches and flip-flops serve as memory elements in digital circuits, they differ in their operation, timing control, and complexity, making them suitable for different applications.

## Flip Flops
- it is a binary cell capable of storing one bit of data
- it is a sequential circuit
- contains memory element to store past output
- has two outputs 
	- normal 
	- complement
- A flip-flop maintains a binary state until directed by a clock pulse to switch states. The difference among various types of flip-flops is in the number of inputs they possess and in the manner in which the inputs affect the binary state

### Use of clock signal in flip flop
In the context of flip-flops, a "clock" refers to a signal that controls the timing of when the flip-flop changes its state. Flip-flops are sequential logic circuits that store binary data in the form of a one-bit memory. The clock signal acts as a trigger for the flip-flop to read the input data and either latch or change its state accordingly.

When the clock signal transitions from one state to another (e.g., from low to high or high to low, depending on the type of flip-flop and its configuration), the flip-flop samples the input data and updates its output accordingly. This sampling process typically occurs on the rising or falling edge of the clock signal, depending on the specific design of the flip-flop.

The use of a clock signal allows for synchronized operation of multiple flip-flops within a digital circuit, ensuring that data is processed and transferred at the correct times. It also helps in controlling the timing of operations and prevents race conditions that can occur in asynchronous systems.

Different types of flip-flops, such as D flip-flops, JK flip-flops, and T flip-flops, utilize the clock signal in slightly different ways, but in all cases, the clock serves as a crucial timing element for the proper functioning of the flip-flop circuit.

Different types of flip-flops use the clock signal in slightly different ways. Here's how some common types of flip-flops utilize the clock signal:

1. **D Flip-Flop**:
   - In a D flip-flop (Data flip-flop), the input data (D) is sampled and transferred to the output (Q) on the rising or falling edge of the clock signal, depending on whether it's a positive-edge-triggered or negative-edge-triggered flip-flop.
   - On the rising edge of the clock, the value of the D input is transferred to the output. The output remains stable until the next rising edge of the clock.
   - This type of flip-flop is useful for applications where data needs to be latched or stored at specific clock intervals.

2. **JK Flip-Flop**:
   - A JK flip-flop has two control inputs: J (set) and K (reset), in addition to the clock input. The output of a JK flip-flop changes state on the clock edge only if the J and K inputs are both high.
   - The clock signal determines when the flip-flop reads the J and K inputs. The output changes state based on the inputs and the current state of the flip-flop on the rising or falling edge of the clock.
   - JK flip-flops are versatile and can be used for toggling, frequency division, and various other sequential logic operations.

3. **T Flip-Flop**:
   - A T flip-flop (Toggle flip-flop) toggles its output state whenever the clock signal transitions from one state to another (e.g., from low to high or high to low), provided the T input is high.
   - When the clock transitions occur and the T input is high, the output switches to its complemented state (i.e., if the output was high, it becomes low, and vice versa).
   - T flip-flops are often used in applications where a single signal needs to alternate between two states at each clock pulse, such as in frequency division circuits.

Each type of flip-flop utilizes the clock signal in a specific manner to control the timing of data transfer and state changes, allowing for various functionalities in digital circuits.
### Types
#### In simple language

1. **SR Flip-Flop (Set-Reset Flip-Flop):**
   - Think of an SR flip-flop like a simple light switch with two buttons: "Set" (S) and "Reset" (R).
   - When you press the "Set" button, the flip-flop turns on (1). It stays on until you press the "Reset" button, which turns it off (0).
   - If both buttons are pressed at the same time, it might cause confusion, and the flip-flop may end up in an unpredictable state.

2. **JK Flip-Flop:**
   - A JK flip-flop is like an SR flip-flop but with a bit more intelligence. It has two inputs: J and K.
   - It behaves somewhat like the SR flip-flop, but it has an additional feature: toggling.
   - If you press the "J" button, it sets the flip-flop (turns it on). If you press the "K" button, it resets the flip-flop (turns it off).
   - But if you press both "J" and "K" simultaneously, the flip-flop toggles its state. So, if it was off, it turns on, and if it was on, it turns off.

3. **D Flip-Flop (Data Flip-Flop):**
   - The D flip-flop is the simplest one. It's like having a single button labeled "D" for data.
   - When you press the "D" button, the flip-flop remembers that state until the next time you press it.
   - It's like a light switch that you flip once to turn on and flip again to turn off. The flip-flop keeps the last state you set until you change it.

4. **T Flip-Flop (Toggle Flip-Flop):**
   - The T flip-flop is like a button labeled "T" for toggle.
   - Each time you press the "T" button, it toggles the state of the flip-flop. So, if it was off, it turns on, and if it was on, it turns off.
   - It's like a light switch that changes its state every time you flick it, regardless of its previous state.

These flip-flops are fundamental building blocks in digital circuits, used for storing and manipulating binary data. They're like switches but with added intelligence to remember and control their state based on specific input signals.
#### SR Flip Flop
- SET RESET flip flop is designed with help of two NAND gate or two NOR gate. these are also called SR Latch
- The operation of the SR flip-flop is as follows. If there is no signal at the clock input C, the output of the circuit cannot change irrespective of the values at inputs S and R. Only when the clock signal changes from 0 to 1 can the output be affected according to the values in inputs S and R. If S = 1 and R = 0 when C changes from 0 to 1, output Q is cleared to 0. If both S and R are 0 during the clock transition, the output does not change. When both S and R are equal to 1, the output is unpredictable and may go to either 0 or 1, depending on internal timing delays that occur within the circuit
![](../../statics/Pasted%20image%2020240303074815.png)

![](../../statics/Pasted%20image%2020240303074700.png)
here t+1 represent Present output and t is past output
The SR flip-flop should not be pulsed when S = R = 1 since it produces an indeterminate next state. This indeterminate condition makes the SR flip-flop difficult to manage and therefore it is seldom used in practice.

#### D Flip Flop
The D (data) flip-flop is a slight modification of the SR flip-flop. An SR flip-flop is converted to a D flip-flop by inserting an inverter between S and R and assigning the symbol D to the single input. The D input is sampled during the occurrence of a clock transition from 0 to 1. If D = 1, the output of the flip-flop goes to the 1 state, but if D = 0, the output of the flip-flop goes to the 0 state.
![](../../statics/Pasted%20image%2020240303075425.png)

Characteristic equation:- Q(t + 1) = D

#### JK Flip Flop
A JK flip-flop is a refinement of the SR flip-flop in that the indeterminate condition of the SR type is defined in the JK type. Inputs J and K behave like inputs S and R to set and clear the flip-flop, respectively. When inputs J and K are both equal to 1, a clock transition switches the outputs of the flip-flop to their complement state
![](../../statics/Pasted%20image%2020240303075746.png)

#### T Flip Flop
Another type of flip-flop found in textbooks is the T (toggle) flip-flop. This flip-flop, shown in Figure 4-5, is obtained from a JK type when inputs J and K are connected to provide a single input designated by T. The T flip-flop therefore has only two conditions.
![](../../statics/Pasted%20image%2020240303080005.png)

### Excitation table
The characteristic tables of flip-flops specify the next state when the inputs and the present state are known. During the design of sequential circuits we usually know the required transition from present state to next state and wish to find the flip-flop inpu-t conditions that will cause the required transition. For this reason we need a table that lists the required input combinations for a given change of state. Such a table is called a flipflop excitation table.

## Registers
- Flip flop is 1-bit memory cell
- To increase the storage capacity . we have to use group of flip flop . this group of FF is known as registers
- N-bit of register consists of n number of flip flop and is capable of storing n-bit of word
### Types of registers
Registers are digital circuits used in computer systems for storing binary data temporarily. They come in various types, each designed for specific functions or applications. Here are some common types of registers:

1. **Data Register (D-Register):**
   - A data register stores data temporarily during processing. It can hold a single binary value or a group of binary values.
   - Data registers are used in arithmetic and logic operations, data movement, and other general-purpose tasks within a computer's central processing unit (CPU) or other parts of the system.

2. **Address Register:**
   - An address register holds memory addresses. It is used for accessing specific locations in memory or other storage devices.
   - Address registers are essential for memory management and addressing modes in computer architecture.

3. **Program Counter (PC):**
   - The program counter register stores the memory address of the next instruction to be fetched and executed in a program.
   - It is incremented after each instruction fetch, effectively pointing to the next instruction in the program sequence.
   - The program counter is crucial for controlling the program flow during execution.

4. **Instruction Register (IR):**
   - The instruction register holds the currently fetched instruction from memory during the instruction execution cycle.
   - It temporarily stores the opcode and operands of the instruction being executed by the CPU.
   - The instruction register is used for decoding and executing instructions in the CPU.

5. **Index Register:**
   - An index register is used for indexed addressing in memory access operations.
   - It holds an offset value that is added to a base address to calculate the effective memory address.
   - Index registers are commonly used in array processing and data structures.

6. **Stack Pointer (SP):**
   - The stack pointer register holds the memory address of the top of the stack in a stack-based memory organization.
   - It is used for pushing data onto the stack and popping data from the stack during subroutine calls and context switching.

7. **Flag Register:**
   - A flag register, also known as a status register, stores various status flags that indicate the outcome of arithmetic and logic operations.
   - Common flags include zero flag, carry flag, sign flag, overflow flag, and parity flag.
   - Flag registers are used for conditional branching and decision-making in program execution.

These are just a few examples of the types of registers commonly found in computer systems. Depending on the architecture and design of the system, there may be additional types of registers with specialized functions.

### Shift registers

A register capable of shifting its binary information in one or both directions is called a shift register. The logical configuration of a shift register consists of a chain of flip-flops in cascade, with the output of one flip-flop connected to the input of the next flip-flop. All flip-flops receive common clock pulses that initiate the shift from one stage to the next.

D flip flop used here commonly 

These are used to perform arithmetic operation

There are several types of shift registers:

1. **Serial-in, Serial-out (SISO) Shift Register:**
   - In a Serial-in, Serial-out shift register, data is inputted serially (one bit at a time) and shifted through the register, appearing one bit at a time at the output.
   - This type of shift register is often used for serial data communication and conversion between serial and parallel data formats.

2. **Serial-in, Parallel-out (SIPO) Shift Register:**
   - In a Serial-in, Parallel-out shift register, data is inputted serially and shifted through the register, but the output is available in parallel at the register's outputs.
   - This type of shift register is useful for converting serial data to parallel data, often used in interfacing with parallel devices or systems.

3. **Parallel-in, Serial-out (PISO) Shift Register:**
   - In a Parallel-in, Serial-out shift register, data is inputted in parallel (multiple bits simultaneously) and then shifted out serially.
   - This type of shift register is commonly used for parallel-to-serial data conversion.

4. **Parallel-in, Parallel-out (PIPO) Shift Register:**
   - In a Parallel-in, Parallel-out shift register, data is inputted and outputted in parallel, without any shifting operation.
   - It's useful for temporary storage of parallel data.

![](../../statics/Pasted%20image%2020240303083943.png)

Shift registers are versatile and find applications in various areas, including:
- Serial data communication: Used in serial communication protocols such as SPI (Serial Peripheral Interface) and UART (Universal Asynchronous Receiver-Transmitter).
- Serial-to-parallel and parallel-to-serial conversion: Converting data between serial and parallel formats for interfacing with different types of devices.
- Data storage and manipulation: Temporary storage and manipulation of data within digital systems.

Shift registers are fundamental building blocks in digital circuits and are widely used in both hardware and software implementations for various applications.

## Counter 
A register that goes through a predetermined sequence of states upon the application of input pulses is called a counter. The input pulses may be clock pulses or may originate form an external source. They may occur at uniform intervals of time or at random. Counters are found in almost all equipment containing digital logic. They are used for counting the number of occurrences of an event and are useful for generating timing signals to control the sequence of operations in digital computers.

A counter that follows the binary number sequence is called a binary counter. An n-bit binary counter is a register of n flip-flops and associated gates that follows a sequence of states according to the binary count of n bits, from 0 to 2n – 1.

Finding mode value of counter :- just count the different states
To find number of filp flops (n) required to design counter having mode value m :- 2<sup>n</sup> >= m

### Sync vs Async counter

| Feature                    | Synchronous Counter                                                       | Asynchronous Counter                                                           |
| -------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Clocking                   | All flip-flops are clocked by the same common clock signal.               | Flip-flops are clocked by individual or separate clock signals.                |
| Timing Control             | All flip-flops change state simultaneously at each clock pulse.           | Flip-flops change state independently, based on their individual clock pulses. |
| Timing Constraints         | Synchronization ensures precise timing and avoids timing hazards.         | Lack of synchronization may lead to timing hazards and glitches.               |
| Design Complexity          | Typically more complex due to synchronization requirements.               | Generally simpler design compared to synchronous counters.                     |
| Speed Performance          | Can operate at higher speeds due to synchronous operation.                | May be limited in speed due to potential timing hazards.                       |
| Power Consumption          | May consume more power due to simultaneous switching of all flip-flops.   | Often consumes less power compared to synchronous counterparts.                |
| Implementation Flexibility | Suitable for applications requiring precise timing and synchronization.   | Suitable for simpler applications or where synchronization is not critical.    |
| Circuit Size               | Generally larger due to additional synchronization logic.                 | Can be more compact due to simpler design and fewer components.                |
| Application Examples       | Microprocessors, digital signal processing, critical timing applications. | Simple counting tasks, clock dividers, frequency dividers.                     |

# Basic Computer organisation and Design 
a "word" typically refers to a basic unit of data that a computer's central processing unit (CPU) can process or manipulate in a single operation. The size of a word is determined by the architecture of the CPU and often corresponds to the width of the CPU's internal data bus.

## Operation and microoperation
In the context of computer architecture and digital systems:

1. **Operation:**
   - An operation refers to a high-level task or action that a computer performs. It represents a meaningful task that contributes to the execution of a program or instruction.
   - Examples of operations include addition, subtraction, multiplication, division, logical operations (AND, OR, NOT), data movement (loading, storing), comparison, branching (jumping to a different instruction based on a condition), and many more.
   - In programming, operations are specified through instructions, which are encoded commands that tell the computer's central processing unit (CPU) what to do.

2. **Microoperation:**
   - A microoperation, on the other hand, represents a small, low-level operation or action performed by the hardware components within a CPU to execute an instruction.
   - Microoperations are the basic building blocks of instruction execution and are typically implemented as simple operations on data within the CPU's registers and other internal components.
   - These operations are usually very elementary, such as loading data from a register, performing arithmetic or logic operations on data, storing data into a register, shifting bits, incrementing or decrementing a value, and transferring control signals within the CPU.
   - Each instruction executed by the CPU typically involves a sequence of microoperations that collectively achieve the desired high-level operation specified by the instruction.

In summary, while an operation represents a higher-level task or action that a computer performs, a microoperation is a low-level action performed by the hardware components within the CPU to execute the instruction associated with the operation. Microoperations are the fundamental operations that enable the CPU to carry out the instructions of a program.
## Overview of how computer work
Alright, let's break down the key points in simpler terms:

1. **What's Inside a Computer?**
   A computer is made up of tiny operations called microoperations. These operations happen inside the computer's registers.

2. **How Do Computers Work?**
   Computers follow instructions to perform tasks. These instructions are like a recipe, telling the computer what to do step by step.

3. **What's a Program?**
   A program is a set of instructions that tells the computer what to do. It includes operations (like adding or subtracting) and the order in which they should happen.

4. **How Do Computers Understand Instructions?**
   Instructions are written in binary code, which is a series of 0s and 1s. The computer reads these instructions from its memory and then follows them.

5. **What's in an Instruction?**
   An instruction has different parts. The most important part is the operation code, which tells the computer what to do (like add or subtract).

6. **How Does the Computer Know What Operation to Perform?**
   The operation code is like a special code that the computer understands. For example, if the code is 110010, it might mean "add." When the computer sees this code, it knows to add something.

7. **What Happens Next?**
   Once the computer knows what operation to perform, it starts doing tiny operations inside itself. These tiny operations are called microoperations.

8. **Where Does the Data Come From?**
   The instructions also tell the computer where to find the data it needs to work with. This could be in the computer's memory or its internal registers.

9. **Putting It All Together**
   Every computer has its own way of understanding instructions. Computer designers create instruction codes to make sure the computer knows what to do with each instruction.

10. **Why Does This Matter?**
   Understanding how instructions work helps us understand how computers process information and perform tasks. It's like knowing the language of computers.

## Stored Program organisation
The simplest way to organize a computer is to have one processor register and instruction code format with two parts. The first part specifies the operation to be performed and the second specifies an address. The memory address tells the control where to find an operand in memory. This operand is read from memory and used as the data to be operated on together with the data stored in the processor register.

opcode(operation code)
![](../../statics/Pasted%20image%2020240303150418.png)
 Instructions are stored in one section of memory and data in another. For a memory unit with 4096 words we need 12 bits to specify an address since 2<sup>12</sup> = 4096. If we store each instruction code in one 16-bit memory word, we have available four bits for the operation code (abbreviated op code) to specify one out of 16 possible operations, and 12 bits to specify the address of an operand. 
 
 The control reads a 16-bit instruction from the program portion of memory. It uses the 12-bit address part of the instruction to read a 16-bit operand from the data portion of memory. It then executes the operation specified by the operation code.

## Direct vs Indirect vs Immediate (Operand Mode)

1. **Immediate Operand**: In this mode, the instruction includes the actual value of the operand rather than its memory address. This means that the data needed for the operation is directly embedded within the instruction itself. For example, if you have an instruction to add the number 5 to a register, the value 5 would be part of the instruction.

2. **Direct Address**: Here, the instruction includes the memory address where the operand is stored. So instead of providing the actual data, the instruction provides the location in memory where the data can be found. For instance, if you have an instruction to add the contents of memory address 100 to a register, the instruction would specify the memory address 100 as the operand.

3. **Indirect Address**: This mode is a bit more complex. In indirect addressing, the instruction includes the memory address where the address of the operand is stored, rather than the operand itself. This means that the CPU needs to first fetch the address from memory and then fetch the actual operand from the address stored in memory. It's like having a pointer to the actual data. For example, if you have an instruction to add the contents of the memory address stored in location 200 to a register, the instruction would specify the memory address 200, which holds the address of the actual operand.

To distinguish between direct and indirect addressing modes, one bit in the instruction code can be used. This bit indicates whether the address provided in the instruction is the actual operand (direct address) or a pointer to the operand (indirect address). This distinction allows for flexibility in how instructions access data in memory, depending on the specific needs of the program being executed.
![](../../statics/Pasted%20image%2020240303151255.png)
here I is used as mode bit ,if it is 0 then direct and 1 is for indirect

The accumulator register, often abbreviated as "AC," is a crucial component of a computer's central processing unit (CPU). It's a special-purpose register designed to temporarily store data during arithmetic and logic operations.

## Register
![](../../statics/Pasted%20image%2020240303151650.png)

## Common Bus System
a bus refers to a communication system that transfers data between different components of a computer system. The bus acts as a pathway or a set of parallel conductors that allow information to travel between various hardware components such as the CPU, memory, input/output devices, and other peripherals.

![](../../statics/Pasted%20image%2020240303154707.png)
In this computer system setup, multiple registers and memory are connected to a common bus. The specific register or memory output that is selected for the bus lines at any given time is determined by the binary value of selection variables \( S2, S1, \) and \( S0 \). These variables indicate which register's or memory's data should be transferred onto the bus.

Each register has control inputs for loading (LD), incrementing (INR), and clearing (CLR). Some registers only have a load (LD) input. These registers function similarly to binary counters with parallel load and synchronous clear operations.

There are four registers (DR, AC, IR, and TR) with 16-bit data, and two registers (AR and PC) with 12-bit data, used for memory addresses. When the contents of AR or PC are placed on the 16-bit bus, the four most significant bits are set to zeros. When data is transferred from the bus to AR or PC, only the 12 least significant bits are transferred into the register.

The input register (INPR) and output register (OUTR) have 8 bits each. INPR communicates with the least significant bits of the bus, providing data from an input device to be transferred to AC. OUTR can only receive data from the bus, delivering it to an output device.

The memory unit's input and output data are connected to the common bus. However, the memory address is connected to the address register (AR). Therefore, AR specifies the memory address. This setup eliminates the need for a separate address bus. Any register can be used to specify the memory data input during a write operation, and any register except AC can receive data from memory after a read operation.

The accumulator register (AC) receives inputs from an adder and logic circuit. These inputs come from the outputs of AC itself, the data register (DR), and the input register (INPR). The inputs from DR and AC are used for arithmetic and logic operations, such as addition and logical AND. The result of an addition is transferred to AC, and the carry-out of the addition is transferred to a flip-flop named E (extended AC bit).

Overall, this system allows for efficient communication between various registers and memory through the common bus, with control over which data is transferred based on selection variables.
## Instruction code
- Group of bits that tells computer what to do basically
- contains two thing :- opcode(operation code like ADD , SUB) and address(address of operand on which operation will be performed);

### Types of Instruction
- Memory reference instructions
- Register reference instructions
- Input output Instruction

![](../../statics/Pasted%20image%2020240413165952.png)
![](../../statics/Pasted%20image%2020240413170115.png)
![](../../statics/Pasted%20image%2020240413170338.png)
## Instruction Cycle
![](../../statics/Pasted%20image%2020240413170541.png)
![](../../statics/Pasted%20image%2020240413170919.png)
![](../../statics/Pasted%20image%2020240413171008.png)
![](../../statics/Pasted%20image%2020240413171038.png)

# CPU
## Intro
The CPU is made up of three major parts, as shown in Figure 6-1. The register set stores intermediate data used during the execution of the instructions. The arithmetic logic unit (ALU) performs the required microoperations for executing the instructions. The control unit supervises the transfer of information among the registers and instructs the ALU as to which operation to perform.
![](../../statics/Pasted%20image%2020240313203715.png)

## Types of CPU Organisation
Single Accumulator Organization:
In a single accumulator organization, there is a single central accumulator register that is used for arithmetic and logical operations. All operations are performed between the accumulator and another operand, typically fetched from memory or another register. After performing an operation, the result is stored back in the accumulator. This organization simplifies the CPU design and instruction set but may require more memory accesses for certain operations.

General Register Organization:
In a general register organization, the CPU has multiple general-purpose registers that can hold data and addresses. These registers are used for storing operands, intermediate results, and memory addresses during program execution. General register organization allows for faster execution of instructions as operands can be accessed directly from registers, reducing the need for memory accesses. It also enables more flexible and efficient programming but may require a more complex CPU design.

Stack Organization:
In stack organization, a stack data structure is used to store data and addresses. The stack grows and shrinks dynamically as data is pushed onto or popped off the stack. The CPU typically includes a special-purpose register called the stack pointer (SP) that points to the top of the stack. Operations such as push and pop are used to add data to and remove data from the stack, respectively. Stack organization is commonly used for function calls, parameter passing, local variable storage, and managing program execution flow. It provides a simple and efficient way to manage data storage and retrieval but may require careful management to avoid stack overflow or underflow.


## Control Word
A control word, also known as a control register or control status register, is a special-purpose register in a computer's CPU or other hardware components that contains control information used to configure or control the behavior of the processor or device.

Control words typically consist of a set of bits, each representing a specific control or configuration option. These bits can be set or cleared by software instructions or by hardware signals to enable or disable certain features, select operating modes, or configure various parameters of the processor or device.

There are 14 binary selection inputs in the unit, and their combined value specifies a control word.

## Flynn 
![](../../statics/Pasted%20image%2020240313205258.png)
![](../../statics/Pasted%20image%2020240313205310.png)
![](../../statics/Pasted%20image%2020240313205353.png)
![](../../statics/Pasted%20image%2020240313205435.png)
![](../../statics/Pasted%20image%2020240313205520.png)
![](../../statics/Pasted%20image%2020240313205537.png)
## System attribute 
![](../../statics/Pasted%20image%2020240313205651.png)
![](../../statics/Pasted%20image%2020240313205659.png)
![](../../statics/Pasted%20image%2020240313210024.png)![](../../statics/Pasted%20image%2020240313210328.png)
![](../../statics/Pasted%20image%2020240313210409.png)

# Unit 4
## Memory Hierarchy
![](../../statics/Pasted%20image%2020240413171929.png)
## Main Memory
![](../../statics/Pasted%20image%2020240413172105.png)
![](../../statics/Pasted%20image%2020240413172207.png)

### Type of access mode
1. **Sequential Access**: In this mode, data is accessed in a sequential order, meaning one after the other in a sequence. Imagine a list of items stored in a file or on a tape. To access data, you have to start from the beginning and read through the data sequentially until you find the desired piece. It's like reading a book from start to finish without skipping pages. Sequential access is often slower compared to random access, especially when you need to access data that is located far from the current position because you have to read through all the preceding data.

2. **Random Access**: In contrast to sequential access, random access allows you to access any piece of data directly without having to read through the preceding data. Think of it as jumping to a specific page in a book without having to flip through the pages sequentially. Random access is faster for accessing individual pieces of data, but the speed doesn't depend on the location of the data within the storage medium.

3. **Direct Access**: Also known as indexed access or relative access, direct access combines aspects of both sequential and random access. It allows accessing any piece of data directly like random access, but the way to access the data is determined by an index or key value, similar to how you'd look up a word in a dictionary. This mode is efficient for accessing specific data items without having to read through the entire dataset sequentially. Direct access is commonly used in databases where data is organized and accessed using indexes.
![](../../statics/Pasted%20image%2020240413173816.png)
![](../../statics/Pasted%20image%2020240413173728.png)

# UNIT 3

## Instruction set based processor classification (RISC and CISC)
An instruction set is a collection of instructions that a processor can execute. These instructions define the operations that the processor can perform, such as arithmetic operations (addition, subtraction, multiplication, division), data movement (loading data from memory, storing data to memory), control flow (branching, jumping), and various other tasks.
![](../../statics/Pasted%20image%2020240425191957.png)
## Stack organisation
![](../../statics/Pasted%20image%2020240425193131.png)
![](../../statics/Pasted%20image%2020240425193155.png)
SP :- stack pointer , DR :- data register

![](../../statics/Pasted%20image%2020240425193249.png)
PC :- program counter , AR:- address register
## Instruction format
![](../../statics/Pasted%20image%2020240425193525.png)
![](../../statics/Pasted%20image%2020240425193558.png)
![](../../statics/Pasted%20image%2020240425193834.png)
![](../../statics/Pasted%20image%2020240425194400.png)

![](../../statics/Pasted%20image%2020240425194657.png)
![](../../statics/Pasted%20image%2020240425194711.png)
![](../../statics/Pasted%20image%2020240425195047.png)
![](../../statics/Pasted%20image%2020240425195105.png)
## Addressing modes
![](../../statics/Pasted%20image%2020240425195935.png)
![](../../statics/Pasted%20image%2020240425200207.png)
![](../../statics/Pasted%20image%2020240425200720.png)
![](../../statics/Pasted%20image%2020240425200753.png)
![](../../statics/Pasted%20image%2020240425200818.png)
![](../../statics/Pasted%20image%2020240425200833.png)
![](../../statics/Pasted%20image%2020240425200914.png)
![](../../statics/Pasted%20image%2020240425200938.png)
![](../../statics/Pasted%20image%2020240425201028.png)
![](../../statics/Pasted%20image%2020240425201113.png)
![](../../statics/Pasted%20image%2020240425201616.png)
![](../../statics/Pasted%20image%2020240425201706.png)
![](../../statics/Pasted%20image%2020240425201725.png)
![](../../statics/Pasted%20image%2020240425201752.png)
![](../../statics/Pasted%20image%2020240425201808.png)

## Interrupts
- High priority instruction generated by hardware device or software program instruction to get immediate attention of cpu
- it is request from hardware device or software program for immediate service by the processor
- As interrupts is generated the processor provides the requested service by executing interrupt service routine

### types 
![](../../statics/Pasted%20image%2020240425203651.png)
![](../../statics/Pasted%20image%2020240425203831.png)
![](../../statics/Pasted%20image%2020240425203906.png)

## Parallelism
![](../../statics/Pasted%20image%2020240425211549.png)

![](../../statics/Pasted%20image%2020240425212033.png)
### Goals of parallelism
#### Throuput enhancement
Throughput refers to the rate at which a system can process and complete tasks or transactions within a given period of time. It is a measure of the system's efficiency in handling workloads and is often expressed in terms of tasks completed per unit of time (e.g., transactions per second, instructions per cycle).

Enhancing throughput involves improving the system's ability to process tasks more quickly and efficiently. Here are some techniques commonly used to enhance throughput:

1. **Parallelism**: Parallelism involves executing multiple tasks simultaneously to increase overall throughput. This can be achieved at various levels, including task-level parallelism (executing independent tasks concurrently), data-level parallelism (processing multiple data elements simultaneously), and instruction-level parallelism (simultaneously executing multiple instructions within a single processor core).

2. **Pipeline Processing**: Pipeline processing divides a task into a series of stages, with each stage performing a specific operation. By overlapping the execution of multiple tasks in different stages of the pipeline, throughput can be increased. Pipeline processing is commonly used in processors, where instructions are executed in multiple stages (instruction fetch, decode, execute, etc.).

3. **Caching**: Caching involves storing frequently accessed data or instructions in fast-access memory locations (caches) closer to the processing units. By reducing the time required to access data from slower memory, caching improves overall system throughput.

4. **Prefetching**: Prefetching anticipates future memory accesses and retrieves data in advance, placing it in caches before it is actually needed. This helps to reduce memory access latency and improve overall throughput by ensuring that data is readily available when required.
6. **Concurrency Control**: In systems with multiple users or processes accessing shared resources, concurrency control techniques such as locking, synchronization, and transaction management are used to ensure efficient utilization of resources and prevent contention, which can degrade throughput.

7. **Load Balancing**: Load balancing distributes tasks evenly across processing units or resources to ensure that no single component becomes a bottleneck. By optimizing resource utilization and minimizing idle time, load balancing improves overall system throughput.
## Instruction level parallelism 
Instruction-Level Parallelism (ILP) refers to the simultaneous execution of multiple instructions within a single processor core to improve performance. It aims to exploit opportunities for parallel execution at the instruction level, allowing multiple instructions to be processed concurrently instead of sequentially.

### Scaler Architecture
Scalar architecture refers to a type of computer architecture where each instruction operates on a single data item at a time. In scalar processors, instructions typically perform arithmetic, logic, or data movement operations on individual data elements, one at a time. This contrasts with vector architectures, where instructions can operate on multiple data elements simultaneously.

Key characteristics of scalar architecture include:

1. **Single Data Stream**: Scalar processors process one data element at a time. Instructions operate on scalar values, which are individual data items (e.g., integers, floating-point numbers) rather than arrays or vectors of data.

2. **Sequential Execution**: Instructions are executed sequentially, with each instruction completing before the next one begins. There is no inherent parallelism at the instruction level within a single processor core.

3. **Limited Parallelism**: While scalar processors may include multiple execution units capable of performing different types of operations (e.g., arithmetic, logic), instructions are typically executed one at a time in program order.

4. **Instruction Pipelining**: Scalar processors often employ instruction pipelining to improve performance by overlapping the execution of multiple instructions. However, each instruction progresses through the pipeline stages independently, and there is no simultaneous execution of multiple instructions.
![](../../statics/Pasted%20image%2020240425213003.png)

### Super scaler
1. Superscalar processors are designed to execute multiple instructions simultaneously within a single clock cycle. This is achieved by having multiple execution units, each capable of handling different types of instructions (e.g., arithmetic, load/store, branch).
2. **Instruction-Level Parallelism (ILP)**: The primary goal of superscalar architectures is to exploit ILP, which involves identifying and executing independent instructions in parallel to improve overall performance. This is done by analyzing the instruction stream to identify dependencies and scheduling instructions for concurrent execution whenever possible.
3. **Dynamic Instruction Scheduling**: Superscalar processors typically employ dynamic instruction scheduling techniques to identify and exploit parallelism at runtime. Instructions are dispatched to execution units dynamically, based on availability of resources and data dependencies.
4. **Out-of-Order Execution**: Superscalar processors often support out-of-order execution, where instructions are executed as soon as their operands are available, rather than strictly following program order. This allows the processor to overlap the execution of independent instructions and maximize resource utilization.

![](../../statics/Pasted%20image%2020240425205833.png)
here each time 2 instruction is execution and when a single stage of these instruction is completed new two instructions are taken for execution

#### Feature of super scalar 
- Instruction level parallel
- Single processor
- RISC Processor
- Instructions should be independent
- Multiple pipeline 
- Multiple instruction are executed per clock cycle

### Pipelining 
![](../../statics/Pasted%20image%2020240425210502.png)
![](../../statics/Pasted%20image%2020240425210519.png)
![](../../statics/Pasted%20image%2020240425210909.png)
![](../../statics/Pasted%20image%2020240425210930.png)
