## assets
 
 approveTransfer(id: `Compact<u32>`, delegate: `MultiAddress`, amount: `Compact<u128>`)
- **interface**: `assets.approveTransfer`
- **summary**:    Approve an amount of asset for transfer by a delegated third-party account. 

   Origin must be Signed. 

   Ensures that `ApprovalDeposit` worth of `Currency` is reserved from signing account  for the purpose of holding the approval. If some non-zero amount of assets is already  approved from signing account to `delegate`, then it is topped up or unreserved to  meet the right value. 

   NOTE: The signing account does not need to own `amount` of assets at the point of  making this call. 

   - `id`: The identifier of the asset. 

   - `delegate`: The account to delegate permission to transfer asset.

   - `amount`: The amount of asset that may be transferred by `delegate`. If there is already an approval in place, then this acts additively. 

   Emits `ApprovedTransfer` on success. 

   Weight: `O(1)` 
 
 block(id: `Compact<u32>`, who: `MultiAddress`)
- **interface**: `assets.block`
- **summary**:    Disallow further unprivileged transfers of an asset `id` to and from an account `who`. 

   Origin must be Signed and the sender should be the Freezer of the asset `id`. 

   - `id`: The identifier of the account's asset. 

  - `who`: The account to be unblocked.

   Emits `Blocked`. 

   Weight: `O(1)` 
 
 burn(id: `Compact<u32>`, who: `MultiAddress`, amount: `Compact<u128>`)
- **interface**: `assets.burn`
- **summary**:    Reduce the balance of `who` by as much as possible up to `amount` assets of `id`. 

   Origin must be Signed and the sender should be the Manager of the asset `id`. 

   Bails with `NoAccount` if the `who` is already dead. 

   - `id`: The identifier of the asset to have some amount burned. 

  - `who`: The account to be debited from.

  - `amount`: The maximum amount by which `who`'s balance should be reduced.

   Emits `Burned` with the actual amount burned. If this takes the balance to below the  minimum for the asset, then the amount burned is increased to take it to zero. 

   Weight: `O(1)`  Modes: Post-existence of `who`; Pre & post Zombie-status of `who`. 
 
 cancelApproval(id: `Compact<u32>`, delegate: `MultiAddress`)
- **interface**: `assets.cancelApproval`
- **summary**:    Cancel all of some asset approved for delegated transfer by a third-party account. 

   Origin must be Signed and there must be an approval in place between signer and  `delegate`. 

   Unreserves any deposit previously reserved by `approve_transfer` for the approval. 

   - `id`: The identifier of the asset. 

  - `delegate`: The account delegated permission to transfer asset.

   Emits `ApprovalCancelled` on success. 

   Weight: `O(1)` 
 
 clearMetadata(id: `Compact<u32>`)
- **interface**: `assets.clearMetadata`
- **summary**:    Clear the metadata for an asset. 

   Origin must be Signed and the sender should be the Owner of the asset `id`. 

   Any deposit is freed for the asset owner. 

   - `id`: The identifier of the asset to clear. 

   Emits `MetadataCleared`. 

   Weight: `O(1)` 
 
 create(id: `Compact<u32>`, admin: `MultiAddress`, min_balance: `u128`)
- **interface**: `assets.create`
- **summary**:    Issue a new class of fungible assets from a public origin. 

   This new asset class has no assets initially and its owner is the origin. 

   The origin must conform to the configured `CreateOrigin` and have sufficient funds free. 

   Funds of sender are reserved by `AssetDeposit`. 

   Parameters: 

  - `id`: The identifier of the new asset. This must not be currently in use to identify an existing asset. If [`NextAssetId`] is set, then this must be equal to it. 

  - `admin`: The admin of this class of assets. The admin is the initial address of each member of the asset class's admin team. 

  - `min_balance`: The minimum balance of this new asset that any single account must have. If an account's balance is reduced below this, then it collapses to zero. 

   Emits `Created` event when successful. 

   Weight: `O(1)` 
 
 destroyAccounts(id: `Compact<u32>`)
- **interface**: `assets.destroyAccounts`
- **summary**:    Destroy all accounts associated with a given asset. 

   `destroy_accounts` should only be called after `start_destroy` has been called, and the  asset is in a `Destroying` state. 

   Due to weight restrictions, this function may need to be called multiple times to fully  destroy all accounts. It will destroy `RemoveItemsLimit` accounts at a time. 

   - `id`: The identifier of the asset to be destroyed. This must identify an existing  asset. 

   Each call emits the `Event::DestroyedAccounts` event. 
 
 destroyApprovals(id: `Compact<u32>`)
- **interface**: `assets.destroyApprovals`
- **summary**:    Destroy all approvals associated with a given asset up to the max (T::RemoveItemsLimit). 

   `destroy_approvals` should only be called after `start_destroy` has been called, and the  asset is in a `Destroying` state. 

   Due to weight restrictions, this function may need to be called multiple times to fully  destroy all approvals. It will destroy `RemoveItemsLimit` approvals at a time. 

   - `id`: The identifier of the asset to be destroyed. This must identify an existing  asset. 

   Each call emits the `Event::DestroyedApprovals` event. 
 
 finishDestroy(id: `Compact<u32>`)
- **interface**: `assets.finishDestroy`
- **summary**:    Complete destroying asset and unreserve currency. 

   `finish_destroy` should only be called after `start_destroy` has been called, and the  asset is in a `Destroying` state. All accounts or approvals should be destroyed before  hand. 

   - `id`: The identifier of the asset to be destroyed. This must identify an existing  asset. 

   Each successful call emits the `Event::Destroyed` event. 
 
 forceAssetStatus(id: `Compact<u32>`, owner: `MultiAddress`, issuer: `MultiAddress`, admin: `MultiAddress`, freezer: `MultiAddress`, min_balance: `Compact<u128>`, is_sufficient: `bool`, is_frozen: `bool`)
- **interface**: `assets.forceAssetStatus`
- **summary**:    Alter the attributes of a given asset. 

   Origin must be `ForceOrigin`. 

   - `id`: The identifier of the asset. 

  - `owner`: The new Owner of this asset.

  - `issuer`: The new Issuer of this asset.

  - `admin`: The new Admin of this asset.

  - `freezer`: The new Freezer of this asset.

  - `min_balance`: The minimum balance of this new asset that any single account must have. If an account's balance is reduced below this, then it collapses to zero. 

  - `is_sufficient`: Whether a non-zero balance of this asset is deposit of sufficient value to account for the state bloat associated with its balance storage. If set to  `true`, then non-zero balances may be stored without a `consumer` reference (and thus  an ED in the Balances pallet or whatever else is used to control user-account state  growth). 

  - `is_frozen`: Whether this asset class is frozen except for permissioned/admin instructions. 

   Emits `AssetStatusChanged` with the identity of the asset. 

   Weight: `O(1)` 
 
 forceCancelApproval(id: `Compact<u32>`, owner: `MultiAddress`, delegate: `MultiAddress`)
- **interface**: `assets.forceCancelApproval`
- **summary**:    Cancel all of some asset approved for delegated transfer by a third-party account. 

   Origin must be either ForceOrigin or Signed origin with the signer being the Admin  account of the asset `id`. 

   Unreserves any deposit previously reserved by `approve_transfer` for the approval. 

   - `id`: The identifier of the asset. 

  - `delegate`: The account delegated permission to transfer asset.

   Emits `ApprovalCancelled` on success. 

   Weight: `O(1)` 
 
 forceClearMetadata(id: `Compact<u32>`)
- **interface**: `assets.forceClearMetadata`
- **summary**:    Clear the metadata for an asset. 

   Origin must be ForceOrigin. 

   Any deposit is returned. 

   - `id`: The identifier of the asset to clear. 

   Emits `MetadataCleared`. 

   Weight: `O(1)` 
 
 forceCreate(id: `Compact<u32>`, owner: `MultiAddress`, is_sufficient: `bool`, min_balance: `Compact<u128>`)
- **interface**: `assets.forceCreate`
- **summary**:    Issue a new class of fungible assets from a privileged origin. 

   This new asset class has no assets initially. 

   The origin must conform to `ForceOrigin`. 

   Unlike `create`, no funds are reserved. 

   - `id`: The identifier of the new asset. This must not be currently in use to identify  an existing asset. If [`NextAssetId`] is set, then this must be equal to it. 

  - `owner`: The owner of this class of assets. The owner has full superuser permissions over this asset, but may later change and configure the permissions using  `transfer_ownership` and `set_team`. 

  - `min_balance`: The minimum balance of this new asset that any single account must have. If an account's balance is reduced below this, then it collapses to zero. 

   Emits `ForceCreated` event when successful. 

   Weight: `O(1)` 
 
 forceSetMetadata(id: `Compact<u32>`, name: `Bytes`, symbol: `Bytes`, decimals: `u8`, is_frozen: `bool`)
- **interface**: `assets.forceSetMetadata`
- **summary**:    Force the metadata for an asset to some value. 

   Origin must be ForceOrigin. 

   Any deposit is left alone. 

   - `id`: The identifier of the asset to update. 

  - `name`: The user friendly name of this asset. Limited in length by `StringLimit`.

  - `symbol`: The exchange symbol for this asset. Limited in length by `StringLimit`.

  - `decimals`: The number of decimals this asset uses to represent one unit.

   Emits `MetadataSet`. 

   Weight: `O(N + S)` where N and S are the length of the name and symbol respectively. 
 
 forceTransfer(id: `Compact<u32>`, source: `MultiAddress`, dest: `MultiAddress`, amount: `Compact<u128>`)
- **interface**: `assets.forceTransfer`
- **summary**:    Move some assets from one account to another. 

   Origin must be Signed and the sender should be the Admin of the asset `id`. 

   - `id`: The identifier of the asset to have some amount transferred. 

  - `source`: The account to be debited.

  - `dest`: The account to be credited.

  - `amount`: The amount by which the `source`'s balance of assets should be reduced and `dest`'s balance increased. The amount actually transferred may be slightly greater in  the case that the transfer would otherwise take the `source` balance above zero but  below the minimum balance. Must be greater than zero. 

   Emits `Transferred` with the actual amount transferred. If this takes the source balance  to below the minimum for the asset, then the amount transferred is increased to take it  to zero. 

   Weight: `O(1)`  Modes: Pre-existence of `dest`; Post-existence of `source`; Account pre-existence of  `dest`. 
 
 freeze(id: `Compact<u32>`, who: `MultiAddress`)
- **interface**: `assets.freeze`
- **summary**:    Disallow further unprivileged transfers of an asset `id` from an account `who`. `who`  must already exist as an entry in `Account`s of the asset. If you want to freeze an  account that does not have an entry, use `touch_other` first. 

   Origin must be Signed and the sender should be the Freezer of the asset `id`. 

   - `id`: The identifier of the asset to be frozen. 

  - `who`: The account to be frozen.

   Emits `Frozen`. 

   Weight: `O(1)` 
 
 freezeAsset(id: `Compact<u32>`)
- **interface**: `assets.freezeAsset`
- **summary**:    Disallow further unprivileged transfers for the asset class. 

   Origin must be Signed and the sender should be the Freezer of the asset `id`. 

   - `id`: The identifier of the asset to be frozen. 

   Emits `Frozen`. 

   Weight: `O(1)` 
 
 mint(id: `Compact<u32>`, beneficiary: `MultiAddress`, amount: `Compact<u128>`)
- **interface**: `assets.mint`
- **summary**:    Mint assets of a particular class. 

   The origin must be Signed and the sender must be the Issuer of the asset `id`. 

   - `id`: The identifier of the asset to have some amount minted. 

  - `beneficiary`: The account to be credited with the minted assets.

  - `amount`: The amount of the asset to be minted.

   Emits `Issued` event when successful. 

   Weight: `O(1)`  Modes: Pre-existing balance of `beneficiary`; Account pre-existence of `beneficiary`. 
 
 refund(id: `Compact<u32>`, allow_burn: `bool`)
- **interface**: `assets.refund`
- **summary**:    Return the deposit (if any) of an asset account or a consumer reference (if any) of an  account. 

   The origin must be Signed. 

   - `id`: The identifier of the asset for which the caller would like the deposit  refunded. 

  - `allow_burn`: If `true` then assets may be destroyed in order to complete the refund.

   It will fail with either [`Error::ContainsHolds`] or [`Error::ContainsFreezes`] if  the asset account contains holds or freezes in place. 

   Emits `Refunded` event when successful. 
 
 refundOther(id: `Compact<u32>`, who: `MultiAddress`)
- **interface**: `assets.refundOther`
- **summary**:    Return the deposit (if any) of a target asset account. Useful if you are the depositor. 

   The origin must be Signed and either the account owner, depositor, or asset `Admin`. In  order to burn a non-zero balance of the asset, the caller must be the account and should  use `refund`. 

   - `id`: The identifier of the asset for the account holding a deposit. 

  - `who`: The account to refund.

   It will fail with either [`Error::ContainsHolds`] or [`Error::ContainsFreezes`] if  the asset account contains holds or freezes in place. 

   Emits `Refunded` event when successful. 
 
 setMetadata(id: `Compact<u32>`, name: `Bytes`, symbol: `Bytes`, decimals: `u8`)
- **interface**: `assets.setMetadata`
- **summary**:    Set the metadata for an asset. 

   Origin must be Signed and the sender should be the Owner of the asset `id`. 

   Funds of sender are reserved according to the formula:  `MetadataDepositBase + MetadataDepositPerByte * (name.len + symbol.len)` taking into  account any already reserved funds. 

   - `id`: The identifier of the asset to update. 

  - `name`: The user friendly name of this asset. Limited in length by `StringLimit`.

  - `symbol`: The exchange symbol for this asset. Limited in length by `StringLimit`.

  - `decimals`: The number of decimals this asset uses to represent one unit.

   Emits `MetadataSet`. 

   Weight: `O(1)` 
 
 setMinBalance(id: `Compact<u32>`, min_balance: `u128`)
- **interface**: `assets.setMinBalance`
- **summary**:    Sets the minimum balance of an asset. 

   Only works if there aren't any accounts that are holding the asset or if  the new value of `min_balance` is less than the old one. 

   Origin must be Signed and the sender has to be the Owner of the  asset `id`. 

   - `id`: The identifier of the asset. 

  - `min_balance`: The new value of `min_balance`.

   Emits `AssetMinBalanceChanged` event when successful. 
 
 setTeam(id: `Compact<u32>`, issuer: `MultiAddress`, admin: `MultiAddress`, freezer: `MultiAddress`)
- **interface**: `assets.setTeam`
- **summary**:    Change the Issuer, Admin and Freezer of an asset. 

   Origin must be Signed and the sender should be the Owner of the asset `id`. 

   - `id`: The identifier of the asset to be frozen. 

  - `issuer`: The new Issuer of this asset.

  - `admin`: The new Admin of this asset.

  - `freezer`: The new Freezer of this asset.

   Emits `TeamChanged`. 

   Weight: `O(1)` 
 
 startDestroy(id: `Compact<u32>`)
- **interface**: `assets.startDestroy`
- **summary**:    Start the process of destroying a fungible asset class. 

   `start_destroy` is the first in a series of extrinsics that should be called, to allow  destruction of an asset class. 

   The origin must conform to `ForceOrigin` or must be `Signed` by the asset's `owner`. 

   - `id`: The identifier of the asset to be destroyed. This must identify an existing  asset. 

   It will fail with either [`Error::ContainsHolds`] or [`Error::ContainsFreezes`] if  an account contains holds or freezes in place. 
 
 thaw(id: `Compact<u32>`, who: `MultiAddress`)
- **interface**: `assets.thaw`
- **summary**:    Allow unprivileged transfers to and from an account again. 

   Origin must be Signed and the sender should be the Admin of the asset `id`. 

   - `id`: The identifier of the asset to be frozen. 

  - `who`: The account to be unfrozen.

   Emits `Thawed`. 

   Weight: `O(1)` 
 
 thawAsset(id: `Compact<u32>`)
- **interface**: `assets.thawAsset`
- **summary**:    Allow unprivileged transfers for the asset again. 

   Origin must be Signed and the sender should be the Admin of the asset `id`. 

   - `id`: The identifier of the asset to be thawed. 

   Emits `Thawed`. 

   Weight: `O(1)` 
 
 touch(id: `Compact<u32>`)
- **interface**: `assets.touch`
- **summary**:    Create an asset account for non-provider assets. 

   A deposit will be taken from the signer account. 

   - `origin`: Must be Signed; the signer account must have sufficient funds for a deposit  to be taken. 

  - `id`: The identifier of the asset for the account to be created.

   Emits `Touched` event when successful. 
 
 touchOther(id: `Compact<u32>`, who: `MultiAddress`)
- **interface**: `assets.touchOther`
- **summary**:    Create an asset account for `who`. 

   A deposit will be taken from the signer account. 

   - `origin`: Must be Signed by `Freezer` or `Admin` of the asset `id`; the signer account  must have sufficient funds for a deposit to be taken. 

  - `id`: The identifier of the asset for the account to be created.

  - `who`: The account to be created.

   Emits `Touched` event when successful. 
 
 transfer(id: `Compact<u32>`, target: `MultiAddress`, amount: `Compact<u128>`)
- **interface**: `assets.transfer`
- **summary**:    Move some assets from the sender account to another. 

   Origin must be Signed. 

   - `id`: The identifier of the asset to have some amount transferred. 

  - `target`: The account to be credited.

  - `amount`: The amount by which the sender's balance of assets should be reduced and `target`'s balance increased. The amount actually transferred may be slightly greater in  the case that the transfer would otherwise take the sender balance above zero but below  the minimum balance. Must be greater than zero. 

   Emits `Transferred` with the actual amount transferred. If this takes the source balance  to below the minimum for the asset, then the amount transferred is increased to take it  to zero. 

   Weight: `O(1)`  Modes: Pre-existence of `target`; Post-existence of sender; Account pre-existence of  `target`. 
 
 transferAll(id: `Compact<u32>`, dest: `MultiAddress`, keep_alive: `bool`)
- **interface**: `assets.transferAll`
- **summary**:    Transfer the entire transferable balance from the caller asset account. 

   NOTE: This function only attempts to transfer _transferable_ balances. This means that  any held, frozen, or minimum balance (when `keep_alive` is `true`), will not be  transferred by this function. To ensure that this function results in a killed account,  you might need to prepare the account by removing any reference counters, storage  deposits, etc... 

   The dispatch origin of this call must be Signed. 

   - `id`: The identifier of the asset for the account holding a deposit. 

  - `dest`: The recipient of the transfer.

  - `keep_alive`: A boolean to determine if the `transfer_all` operation should send all of the funds the asset account has, causing the sender asset account to be killed  (false), or transfer everything except at least the minimum balance, which will  guarantee to keep the sender asset account alive (true). 
 
 transferApproved(id: `Compact<u32>`, owner: `MultiAddress`, destination: `MultiAddress`, amount: `Compact<u128>`)
- **interface**: `assets.transferApproved`
- **summary**:    Transfer some asset balance from a previously delegated account to some third-party  account. 

   Origin must be Signed and there must be an approval in place by the `owner` to the  signer. 

   If the entire amount approved for transfer is transferred, then any deposit previously  reserved by `approve_transfer` is unreserved. 

   - `id`: The identifier of the asset. 

  - `owner`: The account which previously approved for a transfer of at least `amount` and from which the asset balance will be withdrawn. 

  - `destination`: The account to which the asset balance of `amount` will be transferred.

  - `amount`: The amount of assets to transfer.

   Emits `TransferredApproved` on success. 

   Weight: `O(1)` 
 
 transferKeepAlive(id: `Compact<u32>`, target: `MultiAddress`, amount: `Compact<u128>`)
- **interface**: `assets.transferKeepAlive`
- **summary**:    Move some assets from the sender account to another, keeping the sender account alive. 

   Origin must be Signed. 

   - `id`: The identifier of the asset to have some amount transferred. 

  - `target`: The account to be credited.

  - `amount`: The amount by which the sender's balance of assets should be reduced and `target`'s balance increased. The amount actually transferred may be slightly greater in  the case that the transfer would otherwise take the sender balance above zero but below  the minimum balance. Must be greater than zero. 

   Emits `Transferred` with the actual amount transferred. If this takes the source balance  to below the minimum for the asset, then the amount transferred is increased to take it  to zero. 

   Weight: `O(1)`  Modes: Pre-existence of `target`; Post-existence of sender; Account pre-existence of  `target`. 
 
 transferOwnership(id: `Compact<u32>`, owner: `MultiAddress`)
- **interface**: `assets.transferOwnership`
- **summary**:    Change the Owner of an asset. 

   Origin must be Signed and the sender should be the Owner of the asset `id`. 

   - `id`: The identifier of the asset. 

  - `owner`: The new Owner of this asset.

   Emits `OwnerChanged`. 

   Weight: `O(1)` 