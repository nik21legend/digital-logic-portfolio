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
| mux/ | 4x1 MUX (gate-level) | Y = S1'S0'D0 + S1'S0D1 + S1S0'D2 + S1S0D3; each data path tested; also used to implement F = Sigma m(1,2,6,7) |
| demux/ | 1x4 DEMUX with enable | Y = E.I.(select decode); tested all 4 select codes with I = 1, E = 1 |
| decoder/ | 2:4 decoder | One output high per input code; all 4 codes tested |
| priority_encoder/ | 4:2 priority encoder | A1 = D3 + D2, A0 = D3 + D2'.D1; 8 cases tested; fixes the plain encoder's wrong 11 on D1 = D2 = 1 |
| adders/ripple_carry_4bit/ | 4-bit ripple-carry adder | Built from XOR, AND and OR gates; 8 additions tested, including carry through all 4 bits |
| counter/ | 4-bit synchronous counter with T flip-flops | T0 = 1, T1 = Q0, T2 = Q1.Q0, T3 = Q2.Q1.Q0; run from 0000 to 1111 and wrapped back to 0000 |

## Method

1. Write the truth table by hand.
2. Derive the Boolean expression (K-map or De Morgan).
3. Build it in CircuitVerse.
4. Toggle every input combination and compare the output to the table.

## Coming next

Gray code conversion, then CMOS gate analysis.

Tool: CircuitVerse (circuitverse.org)
