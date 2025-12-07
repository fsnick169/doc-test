## balances
 
 existentialDeposit: `u128`
- **interface**: `balances.existentialDeposit`
- **summary**:    The minimum amount required to keep an account open. MUST BE GREATER THAN ZERO! 
 
 maxFreezes: `u32`
- **interface**: `balances.maxFreezes`
- **summary**:    The maximum number of individual freeze locks that can exist on an account at any time. 
 
 maxLocks: `u32`
- **interface**: `balances.maxLocks`
- **summary**:    The maximum number of locks that should exist on an account.  Not strictly enforced, but used for weight estimation. 
 
 maxReserves: `u32`
- **interface**: `balances.maxReserves`
- **summary**:    The maximum number of named reserves that can exist on an account. 