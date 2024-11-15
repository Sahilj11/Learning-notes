## Mealy and Moore Machine 
- Mealy machine is a finite-state machine whose output values are determined both by its current state and the current inputs. 
- This is in contrast to a Moore machine, whose output values are determined solely by its current state. A Mealy machine is a deterministic finite-state transducer: for each state and input, at most one transition is possible.
- When the outputs depend on current states then the FSM can be named as Moore state machine
### Mealy 
![](../../statics/Pasted%20image%2020241113180712.png)
![](../../statics/Pasted%20image%2020241113180724.png)

### Moore 
![](../../statics/Pasted%20image%2020241113180740.png)
![](../../statics/Pasted%20image%2020241113180750.png)

### Difference b/w mealy and moore

| **Feature**                   | **Moore Machine**                                    | **Mealy Machine**                                   |
| ----------------------------- | ---------------------------------------------------- | --------------------------------------------------- |
| **Output Dependency**         | Depends only on the present state                    | Depends on both the present state and present input |
| **Output Change with Input**  | Output does not change immediately with input change | Output changes immediately with input change        |
| **Number of States Required** | Requires more states                                 | Requires fewer states                               |
| **Hardware Requirement**      | Less hardware required for circuit implementation    | More hardware required for circuit implementation   |
| **Response to Input Changes** | Reacts slower (one clock cycle later)                | Reacts faster to input changes                      |
| **Output Generation**         | Synchronous output and state generation              | Asynchronous output generation                      |
| **Output Placement**          | Output is associated with states                     | Output is associated with transitions               |
| **Ease of Design**            | Easier to design                                     | Generally more complex to design                    |

### From Moore to mealy

### From mealy to Moore

## Finite State machine 
![](../../statics/Pasted%20image%2020241113174550.png)
- In the FSM, the outputs, as well as the next state, are a present state and the input function. This means that the selection of the next state mainly depends on the input value and strength lead to more compound system performance