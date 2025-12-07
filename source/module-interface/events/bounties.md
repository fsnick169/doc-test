## bounties
 
 BountyApproved(`u32`)
- **interface**: `bounties.BountyApproved`
- **summary**:    A bounty is approved. 
 
 BountyAwarded(`u32`, `AccountId32`)
- **interface**: `bounties.BountyAwarded`
- **summary**:    A bounty is awarded to a beneficiary. 
 
 BountyBecameActive(`u32`)
- **interface**: `bounties.BountyBecameActive`
- **summary**:    A bounty proposal is funded and became active. 
 
 BountyCanceled(`u32`)
- **interface**: `bounties.BountyCanceled`
- **summary**:    A bounty is cancelled. 
 
 BountyClaimed(`u32`, `u128`, `AccountId32`)
- **interface**: `bounties.BountyClaimed`
- **summary**:    A bounty is claimed by beneficiary. 
 
 BountyExtended(`u32`)
- **interface**: `bounties.BountyExtended`
- **summary**:    A bounty expiry is extended. 
 
 BountyProposed(`u32`)
- **interface**: `bounties.BountyProposed`
- **summary**:    New bounty proposal. 
 
 BountyRejected(`u32`, `u128`)
- **interface**: `bounties.BountyRejected`
- **summary**:    A bounty proposal was rejected; funds were slashed. 
 
 CuratorAccepted(`u32`, `AccountId32`)
- **interface**: `bounties.CuratorAccepted`
- **summary**:    A bounty curator is accepted. 
 
 CuratorProposed(`u32`, `AccountId32`)
- **interface**: `bounties.CuratorProposed`
- **summary**:    A bounty curator is proposed. 
 
 CuratorUnassigned(`u32`)
- **interface**: `bounties.CuratorUnassigned`
- **summary**:    A bounty curator is unassigned. 