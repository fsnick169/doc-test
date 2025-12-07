## balances
 
 DeadAccount
- **interface**: `balances.DeadAccount.is`
- **summary**:    Beneficiary account must pre-exist. 
 
 DeltaZero
- **interface**: `balances.DeltaZero.is`
- **summary**:    The delta cannot be zero. 
 
 ExistentialDeposit
- **interface**: `balances.ExistentialDeposit.is`
- **summary**:    Value too low to create account due to existential deposit. 
 
 ExistingVestingSchedule
- **interface**: `balances.ExistingVestingSchedule.is`
- **summary**:    A vesting schedule already exists for this account. 
 
 Expendability
- **interface**: `balances.Expendability.is`
- **summary**:    Transfer/payment would kill account. 
 
 InsufficientBalance
- **interface**: `balances.InsufficientBalance.is`
- **summary**:    Balance too low to send value. 
 
 IssuanceDeactivated
- **interface**: `balances.IssuanceDeactivated.is`
- **summary**:    The issuance cannot be modified since it is already deactivated. 
 
 LiquidityRestrictions
- **interface**: `balances.LiquidityRestrictions.is`
- **summary**:    Account liquidity restrictions prevent withdrawal. 
 
 TooManyFreezes
- **interface**: `balances.TooManyFreezes.is`
- **summary**:    Number of freezes exceed `MaxFreezes`. 
 
 TooManyHolds
- **interface**: `balances.TooManyHolds.is`
- **summary**:    Number of holds exceed `VariantCountOf<T::RuntimeHoldReason>`. 
 
 TooManyReserves
- **interface**: `balances.TooManyReserves.is`
- **summary**:    Number of named reserves exceed `MaxReserves`. 
 
 VestingBalance
- **interface**: `balances.VestingBalance.is`
- **summary**:    Vesting balance too high to send value. 