## vesting
 
 VestingCompleted(`AccountId32`)
- **interface**: `vesting.VestingCompleted`
- **summary**:    An \[account\] has become fully vested. 
 
 VestingUpdated(`AccountId32`, `u128`)
- **interface**: `vesting.VestingUpdated`
- **summary**:    The amount vested has been updated. This could indicate a change in funds available.  The balance given is the amount which is left unvested (and thus locked). 