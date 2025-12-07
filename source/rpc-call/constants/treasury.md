## treasury
 
 burn: `Permill`
- **interface**: `treasury.burn`
- **summary**:    Percentage of spare funds (if any) that are burnt per spend period. 
 
 maxApprovals: `u32`
- **interface**: `treasury.maxApprovals`
- **summary**:    The maximum number of approvals that can wait in the spending queue. 

   NOTE: This parameter is also used within the Bounties Pallet extension if enabled. 
 
 palletId: `FrameSupportPalletId`
- **interface**: `treasury.palletId`
- **summary**:    The treasury's pallet id, used for deriving its sovereign account ID. 
 
 payoutPeriod: `u32`
- **interface**: `treasury.payoutPeriod`
- **summary**:    The period during which an approved treasury spend has to be claimed. 
 
 potAccount: `AccountId32`
- **interface**: `treasury.potAccount`
- **summary**:    Gets this pallet's derived pot account. 
 
 spendPeriod: `u32`
- **interface**: `treasury.spendPeriod`
- **summary**:    Period between successive spends. 