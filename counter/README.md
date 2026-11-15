# 4-bit Synchronous Counter with T Flip-Flops (CircuitVerse)

A 4-bit binary up counter, 0 to 15, built from four T flip-flops on one shared clock and verified in CircuitVerse.

## Design
- Outputs: Q3..Q0 (shown on LEDs)
- Each flip-flop follows Qn+1 = T xor Qn, so a bit flips only when its T = 1
- T inputs found by hand-tracing the count sequence:

T0 = 1
T1 = Q0
T2 = Q1.Q0
T3 = Q2.Q1.Q0

Gates: 4 T flip-flops, 2 AND (2-input)

## Count table (derived from the equations)

| Q3Q2Q1Q0 | T3 T2 T1 T0 | Next |
|----------|-------------|------|
| 0000 | 0 0 0 1 | 0001 |
| 0001 | 0 0 1 1 | 0010 |
| 0010 | 0 0 0 1 | 0011 |
| 0011 | 0 1 1 1 | 0100 |
| 0100 | 0 0 0 1 | 0101 |
| 0101 | 0 0 1 1 | 0110 |
| 0110 | 0 0 0 1 | 0111 |
| 0111 | 1 1 1 1 | 1000 |
| 1000 | 0 0 0 1 | 1001 |
| 1001 | 0 0 1 1 | 1010 |
| 1010 | 0 0 0 1 | 1011 |
| 1011 | 0 1 1 1 | 1100 |
| 1100 | 0 0 0 1 | 1101 |
| 1101 | 0 0 1 1 | 1110 |
| 1110 | 0 0 0 1 | 1111 |
| 1111 | 1 1 1 1 | 0000 |

## Verification
- Screenshots: counter_1111.png (all four outputs high) and counter_wrap_0000.png (all four outputs low)
- The count was run from 0000 up to 1111 and back to 0000 in a screen recording (the recording is not in this repo)

## Tools
CircuitVerse (circuitverse.org/simulator)
