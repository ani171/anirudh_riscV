# anirudh_riscV

## Digital Logic with TL-Verilog and Makerchip

<summary>Logic Gates</summary>

<details>

- Basic Logic gates
![image](https://github.com/ani171/anirudh_riscV/assets/97838595/6cdd0770-0171-468a-a179-f982d60f097b)

- Boolean operators

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/77084ecf-baed-438b-81eb-cb7f67276076)

</details>

<summary>Basic MUX Implementation </summary>

<details>

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/f20b8793-6d45-4d02-a7de-1b3b0e6895e6)

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/30ac7884-1eaf-49a6-a48b-88d20ab29bb4)

- Ternary operator or a conditional operator, is a shorthand way of writing a conditional expression.

`condition ? expression_if_true : expression_if_false`

  - The condition is evaluated first.
  - If the condition is true, the expression immediately after the ? is executed and returned as the result.
  - If the condition is false, the expression immediately after the : is executed and returned as the result.

#### Chaining Ternary operator

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/341c404f-beb6-46fa-b796-310c6973886c)

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/07aac60a-9dd7-4300-ba10-dfb96de3ee0b)

- Equivalent Implementation

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/8f274141-37be-4eff-8c92-6301a702328d)

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/104fe22b-7e7c-413e-9ca6-fe9c028ee571)

</details>


<summary>Makerchip</summary>

<details>

- An online platform and integrated development environment (IDE) designed for digital design and hardware description language development.

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/df180a0c-6323-4327-a829-957e573b1175)

- Log file - to provide a historical record of what happened during the execution of Makerchip, thus helpful for diagnosing issues, understanding the sequence of events, and ensuring that your digital designs are behaving as expected.

- A Pythagorean example

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/5aee2572-463e-4230-9587-0e0d940d1d10)

- Inverter

 ![image](https://github.com/ani171/anirudh_riscV/assets/97838595/91bc303d-d8a3-4322-a403-af47f4b8f6d2)

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/940d4deb-abeb-4129-b6eb-ab46ce7e20c9)

- AND Gate

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/a1cd5603-1301-48f5-9399-29c95e784a7f)

 - Arithmetic Operations (using vectors)

`$out [4:0] = $in1[3:0] + $in2 [3:0]`

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/8ee419f6-37de-4ed4-a579-9b537651a361)

- Multiplexer

`$out = $sel ? $in1: $in2 `

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/5ec6ec2a-66da-4d5a-a64e-ced983832a38)

`$out[7:0] = $sel ? $in1 [7:0]: $in2[7:0]`

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/864c6474-a49e-4f28-938a-9f4fb33c50a6)

</details>

<summary>Sequential Logic </summary>

<details>

- Sequential Logic is sequenced by a clock signal
- D-flipflop
  - Q Output: This is the main output of the flip-flop and represents the state of the D input at the last clock edge. It reflects the data stored in the flip-flop.
  - Q' (Q-bar) Output: This is the complement of the Q output. If Q is 1, then Q' is 0, and vice versa.
  - The D flip-flop also has a Reset input that can be used to reset the flip-flop to a specific state.

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/b55393e5-a0cc-4823-99e5-1aa09f38c2f3)

- Fibonacci Series
  - 1,1,2,3,5,8,13,....
  - `$val[15:0] = $reset ? 1 : >>1$val + >>2$val`
![image](https://github.com/ani171/anirudh_riscV/assets/97838595/1ba11e1d-654d-4dc1-8679-fd4cb59cd644)

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/19f7bb02-265d-4a7b-b199-e42927bd88ec)

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/0b1a1e46-1cbf-4ccb-8ffc-ae2b1f52c7b2)

</details>

<summary> Pipelined logic </summary>

<details>

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/bca318c1-02f7-4ef8-aa75-b6dbfa20f47e)

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/ca33cb62-ef6f-46c9-83b0-4254aee5a969)

- Distributing this calculation over three cycles, as the logic is too deep to fit into a single cycle

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/701e4bfb-7f6d-4a04-96bf-7dec632183c3)

- In TLV this division can be accessed via the timing abstract

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/bdbdc2ab-5b7f-415c-a2a3-8a575375100e)

```
   @1
      $aa_sq[31:0] = $aa * $aa;
      $bb_sq[31:0] = $bb * $bb;
   @2
      $cc_sq[31:0] = $aa_sq + $bb_sq;
   @3
      $cc[31:0] = sqrt($cc_sq);
```

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/93a9d438-94d3-4ed9-b705-c737204a93a1)

- for the below case
```
   |calc
      
      @0
         $aa_sq[7:0] = $aa[3:0] ** 2;
         $bb_sq[7:0] = $bb[3:0] ** 2;
      @2
         $cc_sq[8:0] = $aa_sq + $bb_sq;
      @4
         $cc[4:0] = sqrt($cc_sq);
```

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/223bd1ef-514d-487c-b5e2-834182cd6a37)

- TL-Verilog is at a higher level of abstraction than SystemVerilog or VHDL and allows for more concise and expressive descriptions of digital circuits.
<br>
- Advantages of Pipelining

  - In a non-pipelined system, an operation may take several clock cycles to complete. With pipelining, each stage of the operation is performed in one clock cycle. Therefore, by combining pipelining with a higher clock frequency, you can significantly reduce the time it takes to complete an operation.
  - Pipelining allows multiple stages of an operation to be executed in parallel. Each stage can be completed in a shorter time, which means that the overall operation can be completed more quickly. This increased throughput can be leveraged in combination with a higher clock frequency to process more operations per unit of time.

- Counter and Calculator
```
\TLV
   
   |calc
      @1
         $reset = *reset;
         $cnt[1:0] = $reset ? (0) : (>>1$cnt[1:0] + 1) ;
         
         $val1[31:0] = >>1$out;
         $val2[31:0] = $rand1[3:0];
         $sum = $val1 + $val2;
         $diff = $val1 - $val2;
         $prod = $val1 * $val2;
         $quot = $val1 / $val2;
         $out = $reset ? ( $op[1]?($op[0] ? $quot : $prod):($op[0] ? $diff : $sum) ) : 0;
   
   // $out = op[1]?(op[0] ? $quot : $prod):(op[0] ? $diff : $sum);
```
![image](https://github.com/ani171/anirudh_riscV/assets/97838595/f4be39a0-7917-4bd9-9521-2be17dc9df8b)
![image](https://github.com/ani171/anirudh_riscV/assets/97838595/b512be11-adda-448f-aee5-8370340e3271)

- 2-cycle calculator
```
\TLV
   
   |calc
      @1
         $val1[31:0] = >>2$out;
         $val2[31:0] = $rand1[3:0];
         $sum[31:0] = $val1[31:0] + $val2[31:0];
         $diff[31:0] = $val1[31:0] - $val2[31:0];
         $prod[31:0] = $val1[31:0] * $val2[31:0];
         $quot[31:0] = $val1[31:0] / $val2[31:0];
         

      @2
         $reset = *reset;
         $valid = $reset ? (0) : (>>1$valid + 1) ;
         $op[1:0] = $reset | $valid ;
         $out[32:0] = $op[1] ? ($op[0] ? $quot[31:0] : $prod[31:0]) : ($op[0] ? $diff[31:0] : $sum[31:0]) ;
   // $out = op[1]?(op[0] ? $quot : $prod):(op[0] ? $diff : $sum);
   
   
   
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
```
![image](https://github.com/ani171/anirudh_riscV/assets/97838595/1983be7a-fdfe-46ed-83c3-7d5bab30c2fa)

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/99ca19d1-f6f3-4658-a439-af4b328cddb1)


</details>

<summary>Identifiers</summary>

<details>

![image](https://github.com/ani171/anirudh_riscV/assets/97838595/4c1eae50-e4db-4830-9b11-1b82ab303d0c)

- $lower_case : pipe signal
- $CamelCase: state signal
- $UPPER_CASE: keyword signal
- $base64_value: good
- $bad_name_5: bad
- `>>1`: ahead by 1
  
</details>

<summary>Validity</summary>

<details>

-  Advantages of design validity
  - Easier Debug: helps identify and fix issues or bugs in a digital system before it's implemented in hardware
  - Cleaner Design: Verification processes often involve writing test benches, creating formal specifications, and documenting the design's behavior. This leads to a more structured and cleaner design.
  - Better Error Checking: Through verification, you can systematically check your design against expected behaviors and requirements. Error-checking mechanisms, such as assertions and formal methods, can be used to validate the design's correctness.
  - Automated Clock Gating: used to reduce power consumption in digital systems by selectively disabling clock signals to unused or idle components.

- Clock gating
  - Clock gating is a power-saving technique in digital design.
  - It selectively enables clock signals only when necessary, saving power during clock distribution.
  - In conventional systems, clocks are distributed to every flip-flop, causing power consumption as clocks toggle twice per cycle.
  - Clock gating avoids unnecessary clock toggles, optimizing power usage.
  - This technique contributes to more energy-efficient digital systems.

- Makerchip file structure
  - m5_TLV_version 1d: The version of Makerchip and potentially TL-Verilog being used
  - tl-x.org: Web address that leads to documentation and resources related to TL-Verilog
  - m5: described as a macro language used for processing. In the context of digital design, macros can be used to automate repetitive tasks and streamline the design process
  - m5_makerchip_module: This term indicates a module or component in Makerchip that expands the inputs and outputs in the NAV file
  - \sv: This typically stands for SystemVerilog codes

- Distance accumulator
  - This is a component or mechanism added to a pipeline to keep track of the accumulated distances during a series of valid transactions.
  - Each valid transaction within the pipeline represents a hop
  - $aa represents the distance associated with the forward movement of a hop. It could be the distance traveled in a straight line.
  - $bb represents the lateral distance, which is often the distance traveled perpendicular to the forward movement.
  - $cc is the computed total distance for a hop. It's the sum of both the forward-facing and lateral distances, providing the overall distance traveled in that hop.
  - The accumulator in the pipeline continuously adds up the $cc values from each valid transaction, providing a running total distance.
  - This accumulation allows you to keep track of the total distance traveled as you process each hop.
 
![image](https://github.com/ani171/anirudh_riscV/assets/97838595/f40f8475-726d-4dc0-862a-ed067701f537)

```
\SV
`include "sqrt32.v";

\TLV
   $reset = *reset;
   
   |calc
      @1
         $reset = *reset ;
      ?$valid
         @1
            $aa_sq[31:0] = $aa * $aa;
            $bb_sq[31:0] = $bb * $bb;

         @2
            $cc_sq[31:0] = $aa_sq + $bb_sq;
         @3
            $cc[31:0] = sqrt($cc_sq);
      @4
         $tot_dst = $reset ? 0 : ($valid ? >>1$tot_dst + $cc : >>1$tot_dst) ;
```


</details>
