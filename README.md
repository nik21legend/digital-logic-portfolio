# digital-logic-portfolio

Digital logic circuits built and simulated in CircuitVerse as part of my
VLSI roadmap (SVCE ECE). Each circuit is derived on paper first, then
built and checked against its truth table.

## Circuits

| Folder | Circuit | Notes |
|---|---|---|
| nand-only/ | NOT, AND, OR from NAND gates only | NAND is a universal gate |
| nor-only/ | NOT, OR, AND from NOR gates only | NOT = 1 NOR, OR = 2, AND = 3 |
| adders/ | Half adder and full adder | Sum = A xor B xor Cin; carry-out is 1 when at least two inputs are 1; checked on all input combinations |
| subtractors/ | Half and full subtractor | D = A xor B xor Bin; Bo = A'B + A'Bin + B.Bin; checked on all input combinations |
| comparator/ | 2-bit magnitude comparator (A>B, A=B, A<B) | Built from SOP expressions; 16 input combinations x 3 outputs |

## Method

1. Write the truth table by hand.
2. Derive the Boolean expression (K-map or De Morgan).
3. Build it in CircuitVerse.
4. Toggle every input combination and compare the output to the table.

## Coming next

Comparator, MUX/DEMUX, encoder/decoder, 4-bit ripple-carry adder, 4-bit counter.

Tool: CircuitVerse (circuitverse.org)
