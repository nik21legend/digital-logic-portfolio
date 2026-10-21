# 4x1 Multiplexer (Gate-Level, CircuitVerse)

A 4-to-1 MUX built from basic gates and verified in CircuitVerse.

## Design
- Inputs: D0-D3 (data), S1, S0 (select)
- Output: Y
- Select lines needed: m = log2(4) = 2

| S1 | S0 | Y  |
|----|----|----|
| 0  | 0  | D0 |
| 0  | 1  | D1 |
| 1  | 0  | D2 |
| 1  | 1  | D3 |

Y = S1'.S0'.D0 + S1'.S0.D1 + S1.S0'.D2 + S1.S0.D3

Gates: 2 NOT, 4 AND (3-input), 1 OR (4-input).

## Verification
Each data path was tested by driving only that input high and selecting it:
- S1S0=00, D0=1 -> LED on
- S1S0=01, D1=1 -> LED on
- S1S0=10, D2=1 -> LED on
- S1S0=11, D3=1 -> LED on
- Negative checks (LED off): D2=1 with S1S0=00, 01, 11; D1=1 with S1S0=00

Screenshots are in this folder (named by capture time).

## Application: F(A,B,C) = Sigma m(1,2,6,7)
Implemented on a 4x1 MUX with A, B as select lines:
D0 = C, D1 = C', D2 = 0, D3 = 1

## Tools
CircuitVerse (circuitverse.org/simulator)
