## ARMv7

Table of contents:
|||||

### How to interpret flags in ARM?

Ref: https://community.arm.com/developer/ip-products/processors/b/processors-ip-blog/posts/condition-codes-1-condition-flags-and-codes

More: difference between carry flag and overflow flag
Ref: https://stackoverflow.com/questions/19301498/carry-flag-auxiliary-flag-and-overflow-flag-in-assembly

### How large can a register store a number?

Ref: https://alisdair.mcdiarmid.org/arm-immediate-value-encoding/
Ref: https://stackoverflow.com/questions/8032051/expressing-large-number-in-arm

### How to read an instruction?

### How to implement division using multiplication?

Ref: https://stackoverflow.com/questions/8348030/how-does-one-do-integer-signed-or-unsigned-division-on-arm

> Division by a constant value is done quickly by doing a 64bit-multiply and shift-right, for example, like this:

> LDR R3, =0xA151C331
> UMULL R3, R2, R1, R3
> MOV R0, R2,LSR#10
> here R1 is divided by 1625. The calculation is done like this: 64bitreg(R2:R3) = R1\*0xA151C331, then the result is the upper 32bit right shifted by 10:

> R1*0xA151C331/2^(32+10) = R1*0.00061538461545751488 = R1/1624.99999980
> You can calculate your own constants from this formula:

> x / N == (x\*A)/2^(32+n) --> A = 2^(32+n)/N
> select the largest n, for which A < 2^32

Usually, just use two different registers for the operations. See also: https://developer.arm.com/documentation/ddi0406/c/Application-Level-Architecture/The-Instruction-Sets/Data-processing-instructions/Divide-instructions
