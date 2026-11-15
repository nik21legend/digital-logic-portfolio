# 2:4 Decoder (Gate-Level, CircuitVerse)

A 2-to-4 decoder built from basic gates and verified in CircuitVerse.

## Design
- Inputs: I1, I0
- Outputs: Y0-Y3 (one output high for each input code)
- Equivalent to the 1x4 DEMUX with its data input tied to 1

| I1 | I0 | Y3 | Y2 | Y1 | Y0 |
|----|----|----|----|----|----|
| 0  | 0  | 0  | 0  | 0  | 1  |
| 0  | 1  | 0  | 0  | 1  | 0  |
| 1  | 0  | 0  | 1  | 0  | 0  |
| 1  | 1  | 1  | 0  | 0  | 0  |

Y0 = I1'.I0', Y1 = I1'.I0, Y2 = I1.I0', Y3 = I1.I0

Gates: 2 NOT, 4 AND (2-input)

## Verification
- I1I0=00 -> only Y0 on
- I1I0=01 -> only Y1 on
- I1I0=10 -> only Y2 on
- I1I0=11 -> only Y3 on

Screenshots are in this folder (named by capture time).

## Tools
CircuitVerse (circuitverse.org/simulator)
