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
