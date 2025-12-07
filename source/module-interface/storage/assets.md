## assets
 
 account(`u32, AccountId32`): `Option<PalletAssetsAssetAccount>`
- **interface**: `assets.account`
- **summary**:    The holdings of a specific account for a specific asset. 
 
 approvals(`u32, AccountId32, AccountId32`): `Option<PalletAssetsApproval>`
- **interface**: `assets.approvals`
- **summary**:    Approved balance transfers. First balance is the amount approved for transfer. Second  is the amount of `T::Currency` reserved for storing this.  First key is the asset ID, second key is the owner and third key is the delegate. 
 
 asset(`u32`): `Option<PalletAssetsAssetDetails>`
- **interface**: `assets.asset`
- **summary**:    Details of an asset. 
 
 metadata(`u32`): `PalletAssetsAssetMetadata`
- **interface**: `assets.metadata`
- **summary**:    Metadata of an asset. 
 
 nextAssetId(): `Option<u32>`
- **interface**: `assets.nextAssetId`
- **summary**:    The asset ID enforced for the next asset creation, if any present. Otherwise, this storage  item has no effect. 

   This can be useful for setting up constraints for IDs of the new assets. For example, by  providing an initial [`NextAssetId`] and using the [`crate::AutoIncAssetId`] callback, an  auto-increment model can be applied to all new asset IDs. 

   The initial next asset ID can be set using the [`GenesisConfig`] or the  [SetNextAssetId] migration. 
