## staking
 
 activeEra(): `Option<PalletStakingActiveEraInfo>`
- **interface**: `staking.activeEra`
- **summary**:    The active era information, it holds index and start. 

   The active era is the era being currently rewarded. Validator set of this era must be  equal to [`SessionInterface::validators`]. 
 
 bonded(`AccountId32`): `Option<AccountId32>`
- **interface**: `staking.bonded`
- **summary**:    Map from all locked "stash" accounts to the controller account. 

   TWOX-NOTE: SAFE since `AccountId` is a secure hash. 
 
 bondedEras(): `Vec<(u32,u32)>`
- **interface**: `staking.bondedEras`
- **summary**:    A mapping from still-bonded eras to the first session index of that era. 

   Must contains information for eras for the range:  `[active_era - bounding_duration; active_era]` 
 
 canceledSlashPayout(): `u128`
- **interface**: `staking.canceledSlashPayout`
- **summary**:    The amount of currency given to reporters of a slash event which was  canceled by extraordinary circumstances (e.g. governance). 
 
 chillThreshold(): `Option<Percent>`
- **interface**: `staking.chillThreshold`
- **summary**:    The threshold for when users can start calling `chill_other` for other validators /  nominators. The threshold is compared to the actual number of validators / nominators  (`CountFor*`) in the system compared to the configured max (`Max*Count`). 
 
 claimedRewards(`u32, AccountId32`): `Vec<u32>`
- **interface**: `staking.claimedRewards`
- **summary**:    History of claimed paged rewards by era and validator. 

   This is keyed by era and validator stash which maps to the set of page indexes which have  been claimed. 

   It is removed after [`Config::HistoryDepth`] eras. 
 
 counterForNominators(): `u32`
- **interface**: `staking.counterForNominators`
- **summary**:    Counter for the related counted storage map 
 
 counterForValidators(): `u32`
- **interface**: `staking.counterForValidators`
- **summary**:    Counter for the related counted storage map 
 
 counterForVirtualStakers(): `u32`
- **interface**: `staking.counterForVirtualStakers`
- **summary**:    Counter for the related counted storage map 
 
 currentEra(): `Option<u32>`
- **interface**: `staking.currentEra`
- **summary**:    The current era index. 

   This is the latest planned era, depending on how the Session pallet queues the validator  set, it might be active or not. 
 
 currentPlannedSession(): `u32`
- **interface**: `staking.currentPlannedSession`
- **summary**:    The last planned session scheduled by the session pallet. 

   This is basically in sync with the call to [`pallet_session::SessionManager::new_session`]. 
 
 erasRewardPoints(`u32`): `PalletStakingEraRewardPoints`
- **interface**: `staking.erasRewardPoints`
- **summary**:    Rewards for the last [`Config::HistoryDepth`] eras.  If reward hasn't been set or has been removed then 0 reward is returned. 
 
 erasStakers(`u32, AccountId32`): `SpStakingExposure`
- **interface**: `staking.erasStakers`
- **summary**:    Exposure of validator at era. 

   This is keyed first by the era index to allow bulk deletion and then the stash account. 

   Is it removed after [`Config::HistoryDepth`] eras.  If stakers hasn't been set or has been removed then empty exposure is returned. 

   Note: Deprecated since v14. Use `EraInfo` instead to work with exposures. 
 
 erasStakersClipped(`u32, AccountId32`): `SpStakingExposure`
- **interface**: `staking.erasStakersClipped`
- **summary**:    Clipped Exposure of validator at era. 

   Note: This is deprecated, should be used as read-only and will be removed in the future.  New `Exposure`s are stored in a paged manner in `ErasStakersPaged` instead. 

   This is similar to [`ErasStakers`] but number of nominators exposed is reduced to the  `T::MaxExposurePageSize` biggest stakers.  (Note: the field `total` and `own` of the exposure remains unchanged).  This is used to limit the i/o cost for the nominator payout. 

   This is keyed fist by the era index to allow bulk deletion and then the stash account. 

   It is removed after [`Config::HistoryDepth`] eras.  If stakers hasn't been set or has been removed then empty exposure is returned. 

   Note: Deprecated since v14. Use `EraInfo` instead to work with exposures. 
 
 erasStakersOverview(`u32, AccountId32`): `Option<SpStakingPagedExposureMetadata>`
- **interface**: `staking.erasStakersOverview`
- **summary**:    Summary of validator exposure at a given era. 

   This contains the total stake in support of the validator and their own stake. In addition,  it can also be used to get the number of nominators backing this validator and the number of  exposure pages they are divided into. The page count is useful to determine the number of  pages of rewards that needs to be claimed. 

   This is keyed first by the era index to allow bulk deletion and then the stash account.  Should only be accessed through `EraInfo`. 

   Is it removed after [`Config::HistoryDepth`] eras.  If stakers hasn't been set or has been removed then empty overview is returned. 
 
 erasStakersPaged(`u32, AccountId32, u32`): `Option<SpStakingExposurePage>`
- **interface**: `staking.erasStakersPaged`
- **summary**:    Paginated exposure of a validator at given era. 

   This is keyed first by the era index to allow bulk deletion, then stash account and finally  the page. Should only be accessed through `EraInfo`. 

   This is cleared after [`Config::HistoryDepth`] eras. 
 
 erasStartSessionIndex(`u32`): `Option<u32>`
- **interface**: `staking.erasStartSessionIndex`
- **summary**:    The session index at which the era start for the last [`Config::HistoryDepth`] eras. 

   Note: This tracks the starting session (i.e. session index when era start being active)  for the eras in `[CurrentEra - HISTORY_DEPTH, CurrentEra]`. 
 
 erasTotalStake(`u32`): `u128`
- **interface**: `staking.erasTotalStake`
- **summary**:    The total amount staked for the last [`Config::HistoryDepth`] eras.  If total hasn't been set or has been removed then 0 stake is returned. 
 
 erasValidatorPrefs(`u32, AccountId32`): `PalletStakingValidatorPrefs`
- **interface**: `staking.erasValidatorPrefs`
- **summary**:    Similar to `ErasStakers`, this holds the preferences of validators. 

   This is keyed first by the era index to allow bulk deletion and then the stash account. 

   Is it removed after [`Config::HistoryDepth`] eras. 
 
 erasValidatorReward(`u32`): `Option<u128>`
- **interface**: `staking.erasValidatorReward`
- **summary**:    The total validator era payout for the last [`Config::HistoryDepth`] eras. 

   Eras that haven't finished yet or has been removed doesn't have reward. 
 
 forceEra(): `PalletStakingForcing`
- **interface**: `staking.forceEra`
- **summary**:    Mode of era forcing. 
 
 invulnerables(): `Vec<AccountId32>`
- **interface**: `staking.invulnerables`
- **summary**:    Any validators that may never be slashed or forcibly kicked. It's a Vec since they're  easy to initialize and the performance hit is minimal (we expect no more than four  invulnerables) and restricted to testnets. 
 
 ledger(`AccountId32`): `Option<PalletStakingStakingLedger>`
- **interface**: `staking.ledger`
- **summary**:    Map from all (unlocked) "controller" accounts to the info regarding the staking. 

   Note: All the reads and mutations to this storage *MUST* be done through the methods exposed  by [`StakingLedger`] to ensure data and lock consistency. 
 
 maxNominatorsCount(): `Option<u32>`
- **interface**: `staking.maxNominatorsCount`
- **summary**:    The maximum nominator count before we stop allowing new validators to join. 

   When this value is not set, no limits are enforced. 
 
 maxStakedRewards(): `Option<Percent>`
- **interface**: `staking.maxStakedRewards`
- **summary**:    Maximum staked rewards, i.e. the percentage of the era inflation that  is used for stake rewards. 
 
 maxValidatorsCount(): `Option<u32>`
- **interface**: `staking.maxValidatorsCount`
- **summary**:    The maximum validator count before we stop allowing new validators to join. 

   When this value is not set, no limits are enforced. 
 
 minCommission(): `Perbill`
- **interface**: `staking.minCommission`
- **summary**:    The minimum amount of commission that validators can set. 

   If set to `0`, no limit exists. 
 
 minimumActiveStake(): `u128`
- **interface**: `staking.minimumActiveStake`
- **summary**:    The minimum active nominator stake of the last successful election. 
 
 minimumValidatorCount(): `u32`
- **interface**: `staking.minimumValidatorCount`
- **summary**:    Minimum number of staking participants before emergency conditions are imposed. 
 
 minNominatorBond(): `u128`
- **interface**: `staking.minNominatorBond`
- **summary**:    The minimum active bond to become and maintain the role of a nominator. 
 
 minValidatorBond(): `u128`
- **interface**: `staking.minValidatorBond`
- **summary**:    The minimum active bond to become and maintain the role of a validator. 
 
 nominators(`AccountId32`): `Option<PalletStakingNominations>`
- **interface**: `staking.nominators`
- **summary**:    The map from nominator stash key to their nomination preferences, namely the validators that  they wish to support. 

   Note that the keys of this storage map might become non-decodable in case the  account's [`NominationsQuota::MaxNominations`] configuration is decreased.  In this rare case, these nominators  are still existent in storage, their key is correct and retrievable (i.e. `contains_key`  indicates that they exist), but their value cannot be decoded. Therefore, the non-decodable  nominators will effectively not-exist, until they re-submit their preferences such that it  is within the bounds of the newly set `Config::MaxNominations`. 

   This implies that `::iter_keys().count()` and `::iter().count()` might return different  values for this map. Moreover, the main `::count()` is aligned with the former, namely the  number of keys that exist. 

   Lastly, if any of the nominators become non-decodable, they can be chilled immediately via  [`Call::chill_other`] dispatchable by anyone. 

   TWOX-NOTE: SAFE since `AccountId` is a secure hash. 
 
 nominatorSlashInEra(`u32, AccountId32`): `Option<u128>`
- **interface**: `staking.nominatorSlashInEra`
- **summary**:    All slashing events on nominators, mapped by era to the highest slash value of the era. 
 
 payee(`AccountId32`): `Option<PalletStakingRewardDestination>`
- **interface**: `staking.payee`
- **summary**:    Where the reward payment should be made. Keyed by stash. 

   TWOX-NOTE: SAFE since `AccountId` is a secure hash. 
 
 slashingSpans(`AccountId32`): `Option<PalletStakingSlashingSlashingSpans>`
- **interface**: `staking.slashingSpans`
- **summary**:    Slashing spans for stash accounts. 
 
 slashRewardFraction(): `Perbill`
- **interface**: `staking.slashRewardFraction`
- **summary**:    The percentage of the slash that is distributed to reporters. 

   The rest of the slashed value is handled by the `Slash`. 
 
 spanSlash(`(AccountId32,u32)`): `PalletStakingSlashingSpanRecord`
- **interface**: `staking.spanSlash`
- **summary**:    Records information about the maximum slash of a stash within a slashing span,  as well as how much reward has been paid out. 
 
 unappliedSlashes(`u32`): `Vec<PalletStakingUnappliedSlash>`
- **interface**: `staking.unappliedSlashes`
- **summary**:    All unapplied slashes that are queued for later. 
 
 validatorCount(): `u32`
- **interface**: `staking.validatorCount`
- **summary**:    The ideal number of active validators. 
 
 validators(`AccountId32`): `PalletStakingValidatorPrefs`
- **interface**: `staking.validators`
- **summary**:    The map from (wannabe) validator stash key to the preferences of that validator. 

   TWOX-NOTE: SAFE since `AccountId` is a secure hash. 
 
 validatorSlashInEra(`u32, AccountId32`): `Option<(Perbill,u128)>`
- **interface**: `staking.validatorSlashInEra`
- **summary**:    All slashing events on validators, mapped by era to the highest slash proportion  and slash value of the era. 