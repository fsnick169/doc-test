## balances
 
 BalanceSet(`AccountId32`, `u128`)
- **interface**: `balances.BalanceSet`
- **summary**:    A balance was set by root. 
 
 Burned(`AccountId32`, `u128`)
- **interface**: `balances.Burned`
- **summary**:    Some amount was burned from an account. 
 
 Deposit(`AccountId32`, `u128`)
- **interface**: `balances.Deposit`
- **summary**:    Some amount was deposited (e.g. for transaction fees). 
 
 DustLost(`AccountId32`, `u128`)
- **interface**: `balances.DustLost`
- **summary**:    An account was removed whose balance was non-zero but below ExistentialDeposit,  resulting in an outright loss. 
 
 Endowed(`AccountId32`, `u128`)
- **interface**: `balances.Endowed`
- **summary**:    An account was created with some free balance. 
 
 Frozen(`AccountId32`, `u128`)
- **interface**: `balances.Frozen`
- **summary**:    Some balance was frozen. 
 
 Issued(`u128`)
- **interface**: `balances.Issued`
- **summary**:    Total issuance was increased by `amount`, creating a credit to be balanced. 
 
 Locked(`AccountId32`, `u128`)
- **interface**: `balances.Locked`
- **summary**:    Some balance was locked. 
 
 Minted(`AccountId32`, `u128`)
- **interface**: `balances.Minted`
- **summary**:    Some amount was minted into an account. 
 
 Rescinded(`u128`)
- **interface**: `balances.Rescinded`
- **summary**:    Total issuance was decreased by `amount`, creating a debt to be balanced. 
 
 Reserved(`AccountId32`, `u128`)
- **interface**: `balances.Reserved`
- **summary**:    Some balance was reserved (moved from free to reserved). 
 
 ReserveRepatriated(`AccountId32`, `AccountId32`, `u128`, `FrameSupportTokensMiscBalanceStatus`)
- **interface**: `balances.ReserveRepatriated`
- **summary**:    Some balance was moved from the reserve of the first account to the second account.  Final argument indicates the destination balance type. 
 
 Restored(`AccountId32`, `u128`)
- **interface**: `balances.Restored`
- **summary**:    Some amount was restored into an account. 
 
 Slashed(`AccountId32`, `u128`)
- **interface**: `balances.Slashed`
- **summary**:    Some amount was removed from the account (e.g. for misbehavior). 
 
 Suspended(`AccountId32`, `u128`)
- **interface**: `balances.Suspended`
- **summary**:    Some amount was suspended from an account (it can be restored later). 
 
 Thawed(`AccountId32`, `u128`)
- **interface**: `balances.Thawed`
- **summary**:    Some balance was thawed. 
 
 TotalIssuanceForced(`u128`, `u128`)
- **interface**: `balances.TotalIssuanceForced`
- **summary**:    The `TotalIssuance` was forcefully changed. 
 
 Transfer(`AccountId32`, `AccountId32`, `u128`)
- **interface**: `balances.Transfer`
- **summary**:    Transfer succeeded. 
 
 Unlocked(`AccountId32`, `u128`)
- **interface**: `balances.Unlocked`
- **summary**:    Some balance was unlocked. 
 
 Unreserved(`AccountId32`, `u128`)
- **interface**: `balances.Unreserved`
- **summary**:    Some balance was unreserved (moved from reserved to free). 
 
 Upgraded(`AccountId32`)
- **interface**: `balances.Upgraded`
- **summary**:    An account was upgraded. 
 
 Withdraw(`AccountId32`, `u128`)
- **interface**: `balances.Withdraw`
- **summary**:    Some amount was withdrawn from the account (e.g. for transaction fees). 