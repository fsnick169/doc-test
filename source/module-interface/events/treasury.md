## treasury
 
 AssetSpendApproved(`u32`, `FrameSupportTokensFungibleUnionOfNativeOrWithId`, `u128`, `AccountId32`, `u32`, `u32`)
- **interface**: `treasury.AssetSpendApproved`
- **summary**:    A new asset spend proposal has been approved. 
 
 AssetSpendVoided(`u32`)
- **interface**: `treasury.AssetSpendVoided`
- **summary**:    An approved spend was voided. 
 
 Awarded(`u32`, `u128`, `AccountId32`)
- **interface**: `treasury.Awarded`
- **summary**:    Some funds have been allocated. 
 
 Burnt(`u128`)
- **interface**: `treasury.Burnt`
- **summary**:    Some of our funds have been burnt. 
 
 Deposit(`u128`)
- **interface**: `treasury.Deposit`
- **summary**:    Some funds have been deposited. 
 
 Paid(`u32`, `Null`)
- **interface**: `treasury.Paid`
- **summary**:    A payment happened. 
 
 PaymentFailed(`u32`, `Null`)
- **interface**: `treasury.PaymentFailed`
- **summary**:    A payment failed and can be retried. 
 
 Rollover(`u128`)
- **interface**: `treasury.Rollover`
- **summary**:    Spending has finished; this is the amount that rolls over until next spend. 
 
 SpendApproved(`u32`, `u128`, `AccountId32`)
- **interface**: `treasury.SpendApproved`
- **summary**:    A new spend proposal has been approved. 
 
 Spending(`u128`)
- **interface**: `treasury.Spending`
- **summary**:    We have ended a spend period and will now allocate funds. 
 
 SpendProcessed(`u32`)
- **interface**: `treasury.SpendProcessed`
- **summary**:    A spend was processed and removed from the storage. It might have been successfully  paid or it may have expired. 
 
 UpdatedInactive(`u128`, `u128`)
- **interface**: `treasury.UpdatedInactive`
- **summary**:    The inactive funds of the pallet have been updated. 