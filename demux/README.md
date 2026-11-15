# 1x4 DEMUX with Enable (Gate-Level, CircuitVerse)

A 1-to-4 demultiplexer with an enable input, built from basic gates and verified in CircuitVerse.

## Design
- Inputs: I (data), S1, S0 (select), E (enable)
- Outputs: Y0-Y3
- Select lines needed: m = log2(4) = 2
- The data input I is routed to the output chosen by S1S0, when E = 1

| E | S1 | S0 | Y3 | Y2 | Y1 | Y0 |
|---|----|----|----|----|----|----|
| 1 | 0  | 0  | 0  | 0  | 0  | I  |
| 1 | 0  | 1  | 0  | 0  | I  | 0  |
| 1 | 1  | 0  | 0  | I  | 0  | 0  |
| 1 | 1  | 1  | I  | 0  | 0  | 0  |

Y0 = E.I.S1'.S0', Y1 = E.I.S1'.S0, Y2 = E.I.S1.S0', Y3 = E.I.S1.S0

With E = 0 every AND gate has a 0 input, so all outputs are 0 by design (not yet tested).

Gates: 2 NOT, 4 AND (4-input)

## Verification
Tested with I = 1 and E = 1:
- S1S0=00 -> only Y0 on
- S1S0=01 -> only Y1 on
- S1S0=10 -> only Y2 on
- S1S0=11 -> only Y3 on

Screenshots are in this folder (named by capture time).

## Related
Tying I to 1 gives the 2:4 decoder (see decoder/).

## Tools
CircuitVerse (circuitverse.org/simulator)
