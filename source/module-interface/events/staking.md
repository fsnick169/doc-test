## staking
 
 Bonded(`AccountId32`, `u128`)
- **interface**: `staking.Bonded`
- **summary**:    An account has bonded this amount. \[stash, amount\] 

   NOTE: This event is only emitted when funds are bonded via a dispatchable. Notably,  it will not be emitted for staking rewards when they are added to stake. 
 
 Chilled(`AccountId32`)
- **interface**: `staking.Chilled`
- **summary**:    An account has stopped participating as either a validator or nominator. 
 
 ControllerBatchDeprecated(`u32`)
- **interface**: `staking.ControllerBatchDeprecated`
- **summary**:    Report of a controller batch deprecation. 
 
 CurrencyMigrated(`AccountId32`, `u128`)
- **interface**: `staking.CurrencyMigrated`
- **summary**:    Staking balance migrated from locks to holds, with any balance that could not be held  is force withdrawn. 
 
 EraPaid(`u32`, `u128`, `u128`)
- **interface**: `staking.EraPaid`
- **summary**:    The era payout has been set; the first balance is the validator-payout; the second is  the remainder from the maximum amount of reward. 
 
 ForceEra(`PalletStakingForcing`)
- **interface**: `staking.ForceEra`
- **summary**:    A new force era mode was set. 
 
 Kicked(`AccountId32`, `AccountId32`)
- **interface**: `staking.Kicked`
- **summary**:    A nominator has been kicked from a validator. 
 
 OldSlashingReportDiscarded(`u32`)
- **interface**: `staking.OldSlashingReportDiscarded`
- **summary**:    An old slashing report from a prior era was discarded because it could  not be processed. 
 
 PayoutStarted(`u32`, `AccountId32`, `u32`, `Option<u32>`)
- **interface**: `staking.PayoutStarted`
- **summary**:    A Page of stakers rewards are getting paid. `next` is `None` if all pages are claimed. 
 
 Rewarded(`AccountId32`, `PalletStakingRewardDestination`, `u128`)
- **interface**: `staking.Rewarded`
- **summary**:    The nominator has been rewarded by this amount to this destination. 
 
 Slashed(`AccountId32`, `u128`)
- **interface**: `staking.Slashed`
- **summary**:    A staker (validator or nominator) has been slashed by the given amount. 
 
 SlashReported(`AccountId32`, `Perbill`, `u32`)
- **interface**: `staking.SlashReported`
- **summary**:    A slash for the given validator, for the given percentage of their stake, at the given  era as been reported. 
 
 SnapshotTargetsSizeExceeded(`u32`)
- **interface**: `staking.SnapshotTargetsSizeExceeded`
- **summary**:    Targets size limit reached. 
 
 SnapshotVotersSizeExceeded(`u32`)
- **interface**: `staking.SnapshotVotersSizeExceeded`
- **summary**:    Voters size limit reached. 
 
 StakersElected()
- **interface**: `staking.StakersElected`
- **summary**:    A new set of stakers was elected. 
 
 StakingElectionFailed()
- **interface**: `staking.StakingElectionFailed`
- **summary**:    The election failed. No new era is planned. 
 
 Unbonded(`AccountId32`, `u128`)
- **interface**: `staking.Unbonded`
- **summary**:    An account has unbonded this amount. 
 
 ValidatorPrefsSet(`AccountId32`, `PalletStakingValidatorPrefs`)
- **interface**: `staking.ValidatorPrefsSet`
- **summary**:    A validator has set their preferences. 
 
 Withdrawn(`AccountId32`, `u128`)
- **interface**: `staking.Withdrawn`
- **summary**:    An account has called `withdraw_unbonded` and removed unbonding chunks worth `Balance`  from the unlocking queue. 