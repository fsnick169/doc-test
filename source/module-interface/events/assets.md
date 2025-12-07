## assets
 
 AccountsDestroyed(`u32`, `u32`, `u32`)
- **interface**: `assets.AccountsDestroyed`
- **summary**:    Accounts were destroyed for given asset. 
 
 ApprovalCancelled(`u32`, `AccountId32`, `AccountId32`)
- **interface**: `assets.ApprovalCancelled`
- **summary**:    An approval for account `delegate` was cancelled by `owner`. 
 
 ApprovalsDestroyed(`u32`, `u32`, `u32`)
- **interface**: `assets.ApprovalsDestroyed`
- **summary**:    Approvals were destroyed for given asset. 
 
 ApprovedTransfer(`u32`, `AccountId32`, `AccountId32`, `u128`)
- **interface**: `assets.ApprovedTransfer`
- **summary**:    (Additional) funds have been approved for transfer to a destination account. 
 
 AssetFrozen(`u32`)
- **interface**: `assets.AssetFrozen`
- **summary**:    Some asset `asset_id` was frozen. 
 
 AssetMinBalanceChanged(`u32`, `u128`)
- **interface**: `assets.AssetMinBalanceChanged`
- **summary**:    The min_balance of an asset has been updated by the asset owner. 
 
 AssetStatusChanged(`u32`)
- **interface**: `assets.AssetStatusChanged`
- **summary**:    An asset has had its attributes changed by the `Force` origin. 
 
 AssetThawed(`u32`)
- **interface**: `assets.AssetThawed`
- **summary**:    Some asset `asset_id` was thawed. 
 
 Blocked(`u32`, `AccountId32`)
- **interface**: `assets.Blocked`
- **summary**:    Some account `who` was blocked. 
 
 Burned(`u32`, `AccountId32`, `u128`)
- **interface**: `assets.Burned`
- **summary**:    Some assets were destroyed. 
 
 Created(`u32`, `AccountId32`, `AccountId32`)
- **interface**: `assets.Created`
- **summary**:    Some asset class was created. 
 
 Deposited(`u32`, `AccountId32`, `u128`)
- **interface**: `assets.Deposited`
- **summary**:    Some assets were deposited (e.g. for transaction fees). 
 
 Destroyed(`u32`)
- **interface**: `assets.Destroyed`
- **summary**:    An asset class was destroyed. 
 
 DestructionStarted(`u32`)
- **interface**: `assets.DestructionStarted`
- **summary**:    An asset class is in the process of being destroyed. 
 
 ForceCreated(`u32`, `AccountId32`)
- **interface**: `assets.ForceCreated`
- **summary**:    Some asset class was force-created. 
 
 Frozen(`u32`, `AccountId32`)
- **interface**: `assets.Frozen`
- **summary**:    Some account `who` was frozen. 
 
 Issued(`u32`, `AccountId32`, `u128`)
- **interface**: `assets.Issued`
- **summary**:    Some assets were issued. 
 
 MetadataCleared(`u32`)
- **interface**: `assets.MetadataCleared`
- **summary**:    Metadata has been cleared for an asset. 
 
 MetadataSet(`u32`, `Bytes`, `Bytes`, `u8`, `bool`)
- **interface**: `assets.MetadataSet`
- **summary**:    New metadata has been set for an asset. 
 
 OwnerChanged(`u32`, `AccountId32`)
- **interface**: `assets.OwnerChanged`
- **summary**:    The owner changed. 
 
 TeamChanged(`u32`, `AccountId32`, `AccountId32`, `AccountId32`)
- **interface**: `assets.TeamChanged`
- **summary**:    The management team changed. 
 
 Thawed(`u32`, `AccountId32`)
- **interface**: `assets.Thawed`
- **summary**:    Some account `who` was thawed. 
 
 Touched(`u32`, `AccountId32`, `AccountId32`)
- **interface**: `assets.Touched`
- **summary**:    Some account `who` was created with a deposit from `depositor`. 
 
 Transferred(`u32`, `AccountId32`, `AccountId32`, `u128`)
- **interface**: `assets.Transferred`
- **summary**:    Some assets were transferred. 
 
 TransferredApproved(`u32`, `AccountId32`, `AccountId32`, `AccountId32`, `u128`)
- **interface**: `assets.TransferredApproved`
- **summary**:    An `amount` was transferred in its entirety from `owner` to `destination` by  the approved `delegate`. 
 
 Withdrawn(`u32`, `AccountId32`, `u128`)
- **interface**: `assets.Withdrawn`
- **summary**:    Some assets were withdrawn from the account (e.g. for transaction fees). 