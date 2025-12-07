## lottery
 
 maxCalls: `u32`
- **interface**: `lottery.maxCalls`
- **summary**:    The max number of calls available in a single lottery. 
 
 maxGenerateRandom: `u32`
- **interface**: `lottery.maxGenerateRandom`
- **summary**:    Number of time we should try to generate a random number that has no modulo bias.  The larger this number, the more potential computation is used for picking the winner,  but also the more likely that the chosen winner is done fairly. 
 
 palletId: `FrameSupportPalletId`
- **interface**: `lottery.palletId`
- **summary**:    The Lottery's pallet id 