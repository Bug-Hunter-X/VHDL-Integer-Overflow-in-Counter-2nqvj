# VHDL Counter with Integer Overflow
This repository demonstrates a common VHDL coding error: integer overflow in a counter. The `buggy_counter.vhdl` file contains a counter implementation that may experience unexpected behavior when reaching its maximum value due to the use of an integer type without proper overflow handling. The `fixed_counter.vhdl` file offers a corrected version addressing this issue.

## Problem
The original code uses an `integer` type for the counter. If the counter reaches its maximum value (15 in this example) and the clock triggers, the `internal_count` attempts to increment beyond the defined range. VHDL's integer type does not wrap around like some other languages, potentially leading to unpredictable results, including simulation errors or unexpected hardware behavior.

## Solution
The `fixed_counter.vhdl` file demonstrates a more robust solution. It uses the `unsigned` type, which is more appropriate for counters as it provides modulo arithmetic and handles overflow gracefully.  Alternatively, explicit checks can be employed to prevent exceeding the maximum count.
