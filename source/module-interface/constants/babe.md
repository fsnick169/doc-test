## babe
 
 epochDuration: `u64`
- **interface**: `babe.epochDuration`
- **summary**:    The amount of time, in slots, that each epoch should last.  NOTE: Currently it is not possible to change the epoch duration after  the chain has started. Attempting to do so will brick block production. 
 
 expectedBlockTime: `u64`
- **interface**: `babe.expectedBlockTime`
- **summary**:    The expected average block time at which BABE should be creating  blocks. Since BABE is probabilistic it is not trivial to figure out  what the expected average block time should be based on the slot  duration and the security parameter `c` (where `1 - c` represents  the probability of a slot being empty). 
 
 maxAuthorities: `u32`
- **interface**: `babe.maxAuthorities`
- **summary**:    Max number of authorities allowed 
 
 maxNominators: `u32`
- **interface**: `babe.maxNominators`
- **summary**:    The maximum number of nominators for each validator. 