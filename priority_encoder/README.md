# 4:2 Priority Encoder (Gate-Level, CircuitVerse)

A 4-to-2 priority encoder built from basic gates and verified in CircuitVerse. When more than one input is high, the highest-numbered input wins.

## Design
- Inputs: D3..D0 (D3 has the highest priority)
- Outputs: A1, A0 (binary code of the highest active input)

| D3 | D2 | D1 | D0 | A1 | A0 |
|----|----|----|----|----|----|
| 0  | 0  | 0  | 0  | 0  | 0  |
| 0  | 0  | 0  | 1  | 0  | 0  |
| 0  | 0  | 1  | X  | 0  | 1  |
| 0  | 1  | X  | X  | 1  | 0  |
| 1  | X  | X  | X  | 1  | 1  |

A1 = D3 + D2
A0 = D3 + D2'.D1

Gates: 1 NOT, 1 AND, 2 OR

## Why priority
A plain encoder (A1 = D2 + D3, A0 = D1 + D3) gives 11 when D1 = D2 = 1, which wrongly reads as input 3 (derived from the equations, plain version not built). The priority version gives 10, so D2 wins over D1. This is shown in screenshot 154347.

## Limitation
There is no valid bit, so D0 alone and no input at all both give 00.

## Verification
Inputs set by hand, outputs read from the LEDs:

| D3 D2 D1 D0 | A1 A0 | Shows | Screenshot |
|-------------|-------|-------|------------|
| 1 1 0 0 | 1 1 | D3 beats D2 | 154337 |
| 0 1 1 0 | 1 0 | D2 beats D1 | 154347 |
| 1 0 1 0 | 1 1 | D3 beats D1 | 154404 |
| 1 1 1 1 | 1 1 | all high | 154411 |
| 0 0 0 1 | 0 0 | D0 only | 154525 |
| 0 0 1 0 | 0 1 | D1 only | 154545 |
| 0 0 1 1 | 0 1 | D1 beats D0 | 154609 |
| 0 1 0 0 | 1 0 | D2 only | 154616 |

Screenshots are in this folder (named by capture time, 2026-11-01).

## Tools
CircuitVerse (circuitverse.org/simulator)
