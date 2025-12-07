## bounties
 
 bounties(`u32`): `Option<PalletBountiesBounty>`
- **interface**: `bounties.bounties`
- **summary**:    Bounties that have been made. 
 
 bountyApprovals(): `Vec<u32>`
- **interface**: `bounties.bountyApprovals`
- **summary**:    Bounty indices that have been approved but not yet funded. 
 
 bountyCount(): `u32`
- **interface**: `bounties.bountyCount`
- **summary**:    Number of bounty proposals that have been made. 
 
 bountyDescriptions(`u32`): `Option<Bytes>`
- **interface**: `bounties.bountyDescriptions`
- **summary**:    The description of each bounty. 