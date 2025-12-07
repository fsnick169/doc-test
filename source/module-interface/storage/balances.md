## balances
 
 account(`AccountId32`): `PalletBalancesAccountData`
- **interface**: `balances.account`
- **summary**:    The Balances pallet example of storing the balance of an account. 
 
 freezes(`AccountId32`): `Vec<FrameSupportTokensMiscIdAmountRuntimeFreezeReason>`
- **interface**: `balances.freezes`
- **summary**:    Freeze locks on account balances. 
 
 holds(`AccountId32`): `Vec<FrameSupportTokensMiscIdAmountRuntimeHoldReason>`
- **interface**: `balances.holds`
- **summary**:    Holds on account balances. 
 
 inactiveIssuance(): `u128`
- **interface**: `balances.inactiveIssuance`
- **summary**:    The total units of outstanding deactivated balance in the system. 
 
 locks(`AccountId32`): `Vec<PalletBalancesBalanceLock>`
- **interface**: `balances.locks`
- **summary**:    Any liquidity locks on some account balances.  NOTE: Should only be accessed when setting, changing and freeing a lock. 
 
 reserves(`AccountId32`): `Vec<PalletBalancesReserveData>`
- **interface**: `balances.reserves`
- **summary**:    Named reserves on some account balances. 
 
 totalIssuance(): `u128`
- **interface**: `balances.totalIssuance`
- **summary**:    The total units issued in the system. 