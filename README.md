#### MODULE NAME
       ALU32

#### DEPENDENCIES
       MUX2, MUX4, SameBit, OneBitAdder

#### INPUTS

Name | Size(Bits)
---------|---------
A    |     32     
alu_op |     5    
B    |     32     

#### OUTPUTS

Name | Size(Bits)
---------|---------
Result |     32     

#### DESCRIPTION
       Computes  A  op  B, where A and B are 32-bit values and 'op' depends on
       the value of alu_op(see below). Stores result in a 32-bit value Result.
       alu_op  is a five bit value, consisting of the following bits in order:
       Ainvert, Binvert, CarryIn, Op1, Op0.  The following operations are sup-
       ported:

Ainvert | Binvert | CarryIn | Op1 | Op0 |  Result  
--------|---------|---------|-----|-----|----------
0    |    0    |    0    |  0  |  0  |  A \& B   
0    |    0    |    0    |  0  |  1  |  A \| B   
0    |    0    |    0    |  1  |  0  |  A \+ B   
0    |    1    |    1    |  1  |  0  |  A \- B   
0    |    1    |    1    |  1  |  1  |  A \< B   
1    |    1    |    0    |  0  |  1  | \!(A \& B)
1    |    1    |    0    |  0  |  0  | \!(A \| B)

#### AUTHOR
       Alexander T Pastoriza

#### SEE ALSO
       qms(1), modclone(1)
