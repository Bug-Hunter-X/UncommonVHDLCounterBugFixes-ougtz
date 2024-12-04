# Uncommon VHDL Counter Bug: Missing 'else' statement in process

This repository demonstrates a subtle but potentially problematic error in a simple VHDL counter. The bug lies in the omission of an 'else' statement within a conditional assignment inside a process.

## Bug Description

The `buggy_counter.vhdl` file contains a VHDL entity and architecture that describe a counter.  The counter is intended to increment on each rising edge of the clock signal, wrapping around from 15 to 0. However, the absence of the 'else' statement in the conditional assignment might lead to unexpected behavior or an off-by-one error if certain conditions are met in the simulation or implementation.

## Bug Solution

The solution is provided in the `buggy_counter_solution.vhdl` file. The 'else' statement is added for completeness, ensuring that the counter always updates appropriately. This addition removes the ambiguity and guarantees a predictable counter behavior.

## How to Reproduce

1.  Simulate the `buggy_counter.vhdl` code using a VHDL simulator (e.g., ModelSim, GHDL).
2. Observe the counter's behavior.  The bug might not be immediately apparent, particularly if the simulation doesn't reach the 'if internal_count = 15 then' condition frequently.
3. Compare the simulation output with the output of the corrected code in `buggy_counter_solution.vhdl`.
