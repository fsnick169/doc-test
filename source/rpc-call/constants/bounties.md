## bounties
 
 bountyDepositBase: `u128`
- **interface**: `bounties.bountyDepositBase`
- **summary**:    The amount held on deposit for placing a bounty proposal. 
 
 bountyDepositPayoutDelay: `u32`
- **interface**: `bounties.bountyDepositPayoutDelay`
- **summary**:    The delay period for which a bounty beneficiary need to wait before claim the payout. 
 
 bountyUpdatePeriod: `u32`
- **interface**: `bounties.bountyUpdatePeriod`
- **summary**:    The time limit for a curator to act before a bounty expires. 

   The period that starts when a curator is approved, during which they must execute or  update the bounty via `extend_bounty_expiry`. If missed, the bounty expires, and the  curator may be slashed. If `BlockNumberFor::MAX`, bounties stay active indefinitely,  removing the need for `extend_bounty_expiry`. 
 
 bountyValueMinimum: `u128`
- **interface**: `bounties.bountyValueMinimum`
- **summary**:    Minimum value for a bounty. 
 
 curatorDepositMax: `Option<u128>`
- **interface**: `bounties.curatorDepositMax`
- **summary**:    Maximum amount of funds that should be placed in a deposit for making a proposal. 
 
 curatorDepositMin: `Option<u128>`
- **interface**: `bounties.curatorDepositMin`
- **summary**:    Minimum amount of funds that should be placed in a deposit for making a proposal. 
 
 curatorDepositMultiplier: `Permill`
- **interface**: `bounties.curatorDepositMultiplier`
- **summary**:    The curator deposit is calculated as a percentage of the curator fee. 

   This deposit has optional upper and lower bounds with `CuratorDepositMax` and  `CuratorDepositMin`. 
 
 dataDepositPerByte: `u128`
- **interface**: `bounties.dataDepositPerByte`
- **summary**:    The amount held on deposit per byte within the tip report reason or bounty description. 
 
 maximumReasonLength: `u32`
- **interface**: `bounties.maximumReasonLength`
- **summary**:    Maximum acceptable reason length. 

   Benchmarks depend on this value, be sure to update weights file when changing this value 