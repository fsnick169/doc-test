## treasury
 
 approvals(): `Vec<u32>`
- **interface**: `treasury.approvals`
- **summary**:    Proposal indices that have been approved but not yet awarded. 
 
 deactivated(): `u128`
- **interface**: `treasury.deactivated`
- **summary**:    The amount which has been reported as inactive to Currency. 
 
 lastSpendPeriod(): `Option<u32>`
- **interface**: `treasury.lastSpendPeriod`
- **summary**:    The blocknumber for the last triggered spend period. 
 
 proposalCount(): `u32`
- **interface**: `treasury.proposalCount`
- **summary**:    Number of proposals that have been made. 
 
 proposals(`u32`): `Option<PalletTreasuryProposal>`
- **interface**: `treasury.proposals`
- **summary**:    Proposals that have been made. 
 
 spendCount(): `u32`
- **interface**: `treasury.spendCount`
- **summary**:    The count of spends that have been made. 
 
 spends(`u32`): `Option<PalletTreasurySpendStatus>`
- **interface**: `treasury.spends`
- **summary**:    Spends that have been approved and being processed. 