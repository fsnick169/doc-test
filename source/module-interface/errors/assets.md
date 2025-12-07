## assets
 
 AlreadyExists
- **interface**: `assets.AlreadyExists.is`
- **summary**:    The asset-account already exists. 
 
 AssetNotLive
- **interface**: `assets.AssetNotLive.is`
- **summary**:    The asset is not live, and likely being destroyed. 
 
 BadAssetId
- **interface**: `assets.BadAssetId.is`
- **summary**:    The asset ID must be equal to the [`NextAssetId`]. 
 
 BadMetadata
- **interface**: `assets.BadMetadata.is`
- **summary**:    Invalid metadata given. 
 
 BadWitness
- **interface**: `assets.BadWitness.is`
- **summary**:    Invalid witness data given. 
 
 BalanceLow
- **interface**: `assets.BalanceLow.is`
- **summary**:    Account balance must be greater than or equal to the transfer amount. 
 
 CallbackFailed
- **interface**: `assets.CallbackFailed.is`
- **summary**:    Callback action resulted in error 
 
 ContainsFreezes
- **interface**: `assets.ContainsFreezes.is`
- **summary**:    The asset cannot be destroyed because some accounts for this asset contain freezes. 
 
 ContainsHolds
- **interface**: `assets.ContainsHolds.is`
- **summary**:    The asset cannot be destroyed because some accounts for this asset contain holds. 
 
 Frozen
- **interface**: `assets.Frozen.is`
- **summary**:    The origin account is frozen. 
 
 IncorrectStatus
- **interface**: `assets.IncorrectStatus.is`
- **summary**:    The asset status is not the expected status. 
 
 InUse
- **interface**: `assets.InUse.is`
- **summary**:    The asset ID is already taken. 
 
 LiveAsset
- **interface**: `assets.LiveAsset.is`
- **summary**:    The asset is a live asset and is actively being used. Usually emit for operations such  as `start_destroy` which require the asset to be in a destroying state. 
 
 MinBalanceZero
- **interface**: `assets.MinBalanceZero.is`
- **summary**:    Minimum balance should be non-zero. 
 
 NoAccount
- **interface**: `assets.NoAccount.is`
- **summary**:    The account to alter does not exist. 
 
 NoDeposit
- **interface**: `assets.NoDeposit.is`
- **summary**:    The asset-account doesn't have an associated deposit. 
 
 NoPermission
- **interface**: `assets.NoPermission.is`
- **summary**:    The signing account has no permission to do the operation. 
 
 NotFrozen
- **interface**: `assets.NotFrozen.is`
- **summary**:    The asset should be frozen before the given operation. 
 
 Unapproved
- **interface**: `assets.Unapproved.is`
- **summary**:    No approval exists that would allow the transfer. 
 
 UnavailableConsumer
- **interface**: `assets.UnavailableConsumer.is`
- **summary**:    Unable to increment the consumer reference counters on the account. Either no provider  reference exists to allow a non-zero balance of a non-self-sufficient asset, or one  fewer then the maximum number of consumers has been reached. 
 
 Unknown
- **interface**: `assets.Unknown.is`
- **summary**:    The given asset ID is unknown. 
 
 WouldBurn
- **interface**: `assets.WouldBurn.is`
- **summary**:    The operation would result in funds being burned. 
 
 WouldDie
- **interface**: `assets.WouldDie.is`
- **summary**:    The source account would not survive the transfer and it needs to stay alive. 