## grandpa
 
 maxAuthorities: `u32`
- **interface**: `grandpa.maxAuthorities`
- **summary**:    Max Authorities in use 
 
 maxNominators: `u32`
- **interface**: `grandpa.maxNominators`
- **summary**:    The maximum number of nominators for each validator. 
 
 maxSetIdSessionEntries: `u64`
- **interface**: `grandpa.maxSetIdSessionEntries`
- **summary**:    The maximum number of entries to keep in the set id to session index mapping. 

   Since the `SetIdSession` map is only used for validating equivocations this  value should relate to the bonding duration of whatever staking system is  being used (if any). If equivocation handling is not enabled then this value  can be zero. 