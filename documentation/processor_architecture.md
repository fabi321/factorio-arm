# Instruction decoder

| Instruction | Encoding | Signal | Parameters| Notes |
|-------------|----------|--------|-----------|-------|
| ADC (register) | T1 | Wooden chest | M: Rdn; D: Rm | |
| ADD (immediate) | T1 | Iron chest | D: Rd; N: Rn; I: imm3 | |
| ADD (immediate) | T2 | Steel chest | I: imm8; D: Rdn | |
| ADD (register) | T1 | Storage tank | D: Rd; N: Rn; M: Rm | |
| ADD (register) | T2 | Transport belt | D: DN:Rdn; M: Rm | Does not happen if D or M are == 13 |
| ADD (SP plus immediate) | T1 | Fast transport belt | I: imm8<<2; D: Rd | |
| ADD (SP plus immediate) | T2 | Express transport belt | I: imm7<<2 | |
| ADD (SP plus immediate) | T1 | Underground belt | D: DM:Rdm | Special case for ADD (register) T2 M == 13 |
| ADD (SP plus register) | T2 | Fast underground belt | D: Rm | Special case for ADD (register) T2 D == 13 |
| ADR | T1 | Express underground belt | I: imm8<<2; D: Rd | |
| AND (register) | T1 | Splitter | D: Rdn; M: Rm | |
| ASR (immediate) | T1 | Fast splitter | D: Rd; M: Rm; I: imm5 | I == 0 => I = 32 |
| ASR (register) | T1 | Express splitter | D: Rdn; M: Rm | |
| B | T1 | Burner inserter | I: imm8:0; C: cond | I is signed |
| B | T2 | Inserter | I: imm11:0 | I is signed |
| BIC (register) | T1 | Long-handed inserter | D: Rdn; M: Rm | |
| BKPT | T1 | Fast inserter | -- | imm8 is ignored by hardware |
| BL | T1 | Filter inserter | not implemented | 32bit instruction handling not finished |
| BLX | T1 | Stack inserter | M: Rm | |
| BX | T1 | Stack filter inserter | M: Rm | |
| CMN (register) | T1 | Small electric pole | D: Rn; M: Rm | |
| CMP (immediate) | T1 | Medium electric pole | I: imm8; N: Rn | |
| CMP (register) | T1 | Big electric pole | N: Rn | M; Rm | |
