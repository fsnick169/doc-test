## vesting
 
 storageVersion(): `PalletVestingReleases`
- **interface**: `vesting.storageVersion`
- **summary**:    Storage version of the pallet. 

   New networks start with latest version, as determined by the genesis build. 
 
 vesting(`AccountId32`): `Option<Vec<PalletVestingVestingInfo>>`
- **interface**: `vesting.vesting`
- **summary**:    Information regarding the vesting of a given account. 