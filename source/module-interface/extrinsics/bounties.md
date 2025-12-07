## bounties
 
 acceptCurator(bounty_id: `Compact<u32>`)
- **interface**: `bounties.acceptCurator`
- **summary**:    Accept the curator role for a bounty.  A deposit will be reserved from curator and refund upon successful payout. 

   May only be called from the curator. 

   Complexity:    O(1).
 
 approveBounty(bounty_id: `Compact<u32>`)
- **interface**: `bounties.approveBounty`
- **summary**:    Approve a bounty proposal. At a later time, the bounty will be funded and become active  and the original deposit will be returned. 

   May only be called from `T::SpendOrigin`. 

   Complexity:    O(1).
 
 approveBountyWithCurator(bounty_id: `Compact<u32>`, curator: `MultiAddress`, fee: `Compact<u128>`)
- **interface**: `bounties.approveBountyWithCurator`
- **summary**:    Approve bountry and propose a curator simultaneously.  This call is a shortcut to calling `approve_bounty` and `propose_curator` separately. 

   May only be called from `T::SpendOrigin`. 

   - `bounty_id`: Bounty ID to approve. 

  - `curator`: The curator account whom will manage this bounty.

  - `fee`: The curator fee.

   Complexity:    O(1).
 
 awardBounty(bounty_id: `Compact<u32>`, beneficiary: `MultiAddress`)
- **interface**: `bounties.awardBounty`
- **summary**:    Award bounty to a beneficiary account. The beneficiary will be able to claim the funds  after a delay. 

   The dispatch origin for this call must be the curator of this bounty. 

   - `bounty_id`: Bounty ID to award. 

  - `beneficiary`: The beneficiary account whom will receive the payout.

   Complexity:    O(1).
 
 claimBounty(bounty_id: `Compact<u32>`)
- **interface**: `bounties.claimBounty`
- **summary**:    Claim the payout from an awarded bounty after payout delay. 

   The dispatch origin for this call must be the beneficiary of this bounty. 

   - `bounty_id`: Bounty ID to claim. 

   Complexity:    O(1).
 
 closeBounty(bounty_id: `Compact<u32>`)
- **interface**: `bounties.closeBounty`
- **summary**:    Cancel a proposed or active bounty. All the funds will be sent to treasury and  the curator deposit will be unreserved if possible. 

   Only `T::RejectOrigin` is able to cancel a bounty. 

   - `bounty_id`: Bounty ID to cancel. 

   Complexity:    O(1).
 
 extendBountyExpiry(bounty_id: `Compact<u32>`, remark: `Bytes`)
- **interface**: `bounties.extendBountyExpiry`
- **summary**:    Extend the expiry time of an active bounty. 

   The dispatch origin for this call must be the curator of this bounty. 

   - `bounty_id`: Bounty ID to extend. 

  - `remark`: additional information.

   Complexity:    O(1).
 
 proposeBounty(value: `Compact<u128>`, description: `Bytes`)
- **interface**: `bounties.proposeBounty`
- **summary**:    Propose a new bounty. 

   The dispatch origin for this call must be _Signed_. 

   Payment: `TipReportDepositBase` will be reserved from the origin account, as well as  `DataDepositPerByte` for each byte in `reason`. It will be unreserved upon approval,  or slashed when rejected. 

   - `curator`: The curator account whom will manage this bounty. 

  - `fee`: The curator fee.

  - `value`: The total payment amount of this bounty, curator fee included.

  - `description`: The description of this bounty.
 
 proposeCurator(bounty_id: `Compact<u32>`, curator: `MultiAddress`, fee: `Compact<u128>`)
- **interface**: `bounties.proposeCurator`
- **summary**:    Propose a curator to a funded bounty. 

   May only be called from `T::SpendOrigin`. 

   Complexity:    O(1).
 
 unassignCurator(bounty_id: `Compact<u32>`)
- **interface**: `bounties.unassignCurator`
- **summary**:    Unassign curator from a bounty. 

   This function can only be called by the `RejectOrigin` a signed origin. 

   If this function is called by the `RejectOrigin`, we assume that the curator is  malicious or inactive. As a result, we will slash the curator when possible. 

   If the origin is the curator, we take this as a sign they are unable to do their job and  they willingly give up. We could slash them, but for now we allow them to recover their  deposit and exit without issue. (We may want to change this if it is abused.) 

   Finally, the origin can be anyone if and only if the curator is "inactive". This allows  anyone in the community to call out that a curator is not doing their due diligence, and  we should pick a new curator. In this case the curator should also be slashed. 

   Complexity:    O(1).