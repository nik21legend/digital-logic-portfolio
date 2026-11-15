# 4-bit Ripple-Carry Adder (Gate-Level, CircuitVerse)

A 4-bit adder built from XOR, AND and OR gates, with the carry rippling from bit 0 up to the carry-out. Verified in CircuitVerse.

## Design
- Inputs: a3..a0, b3..b0 (no carry-in, so bit 0 is a half adder)
- Outputs: s3..s0 (sum), Cout (carry-out)
- Per bit: p = a XOR b (propagate), g = a AND b (generate)

s0 = p0
c1 = g0
s1 = p1 XOR c1, c2 = g1 + p1.c1
s2 = p2 XOR c2, c3 = g2 + p2.c2
s3 = p3 XOR c3, Cout = g3 + p3.c3

Gates: 7 XOR, 7 AND, 3 OR

## Verification
Inputs set by hand, sum read from the LEDs:

| A (a3..a0) | B (b3..b0) | Cout s3..s0 | Decimal | Screenshot |
|------------|------------|-------------|---------|------------|
| 0000 | 0000 | 0 0000 | 0 + 0 = 0   | 104256 |
| 1010 | 1100 | 1 0110 | 10 + 12 = 22 | 104316 |
| 1111 | 1000 | 1 0111 | 15 + 8 = 23  | 104412 |
| 0101 | 1010 | 0 1111 | 5 + 10 = 15  | 104550 |
| 0001 | 0001 | 0 0010 | 1 + 1 = 2    | 105037 |
| 0111 | 0001 | 0 1000 | 7 + 1 = 8    | 105116 |
| 1111 | 0001 | 1 0000 | 15 + 1 = 16  | 105132 |
| 0101 | 0011 | 0 1000 | 5 + 3 = 8    | 105206 |

The 0111 + 0001 and 1111 + 0001 cases make the carry ripple through 3 and then all 4 bits.

Screenshots are in this folder (named by capture time, 2026-11-01).

## Tools
CircuitVerse (circuitverse.org/simulator)
