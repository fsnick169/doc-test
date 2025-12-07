## staking
 
 AlreadyBonded
- **interface**: `staking.AlreadyBonded.is`
- **summary**:    Stash is already bonded. 
 
 AlreadyClaimed
- **interface**: `staking.AlreadyClaimed.is`
- **summary**:    Rewards for this era have already been claimed for this validator. 
 
 AlreadyMigrated
- **interface**: `staking.AlreadyMigrated.is`
- **summary**:    The stake of this account is already migrated to `Fungible` holds. 
 
 AlreadyPaired
- **interface**: `staking.AlreadyPaired.is`
- **summary**:    Controller is already paired. 
 
 BadState
- **interface**: `staking.BadState.is`
- **summary**:    Internal state has become somehow corrupted and the operation cannot continue. 
 
 BadTarget
- **interface**: `staking.BadTarget.is`
- **summary**:    A nomination target was supplied that was blocked or otherwise not a validator. 
 
 BoundNotMet
- **interface**: `staking.BoundNotMet.is`
- **summary**:    Some bound is not met. 
 
 CannotChillOther
- **interface**: `staking.CannotChillOther.is`
- **summary**:    The user has enough bond and thus cannot be chilled forcefully by an external person. 
 
 CannotReapStash
- **interface**: `staking.CannotReapStash.is`
- **summary**:    Stash could not be reaped as other pallet might depend on it. 
 
 CannotRestoreLedger
- **interface**: `staking.CannotRestoreLedger.is`
- **summary**:    Cannot reset a ledger. 
 
 CommissionTooLow
- **interface**: `staking.CommissionTooLow.is`
- **summary**:    Commission is too low. Must be at least `MinCommission`. 
 
 ControllerDeprecated
- **interface**: `staking.ControllerDeprecated.is`
- **summary**:    Used when attempting to use deprecated controller account logic. 
 
 DuplicateIndex
- **interface**: `staking.DuplicateIndex.is`
- **summary**:    Duplicate index. 
 
 EmptyTargets
- **interface**: `staking.EmptyTargets.is`
- **summary**:    Targets cannot be empty. 
 
 FundedTarget
- **interface**: `staking.FundedTarget.is`
- **summary**:    Attempting to target a stash that still has funds. 
 
 IncorrectHistoryDepth
- **interface**: `staking.IncorrectHistoryDepth.is`
- **summary**:    Incorrect previous history depth input provided. 
 
 IncorrectSlashingSpans
- **interface**: `staking.IncorrectSlashingSpans.is`
- **summary**:    Incorrect number of slashing spans provided. 
 
 InsufficientBond
- **interface**: `staking.InsufficientBond.is`
- **summary**:    Cannot have a validator or nominator role, with value less than the minimum defined by  governance (see `MinValidatorBond` and `MinNominatorBond`). If unbonding is the  intention, `chill` first to remove one's role as validator/nominator. 
 
 InvalidEraToReward
- **interface**: `staking.InvalidEraToReward.is`
- **summary**:    Invalid era to reward. 
 
 InvalidNumberOfNominations
- **interface**: `staking.InvalidNumberOfNominations.is`
- **summary**:    Invalid number of nominations. 
 
 InvalidPage
- **interface**: `staking.InvalidPage.is`
- **summary**:    No nominators exist on this page. 
 
 InvalidSlashIndex
- **interface**: `staking.InvalidSlashIndex.is`
- **summary**:    Slash record index out of bounds. 
 
 NoMoreChunks
- **interface**: `staking.NoMoreChunks.is`
- **summary**:    Can not schedule more unlock chunks. 
 
 NotController
- **interface**: `staking.NotController.is`
- **summary**:    Not a controller account. 
 
 NotEnoughFunds
- **interface**: `staking.NotEnoughFunds.is`
- **summary**:    Not enough funds available to withdraw. 
 
 NotSortedAndUnique
- **interface**: `staking.NotSortedAndUnique.is`
- **summary**:    Items are not sorted and unique. 
 
 NotStash
- **interface**: `staking.NotStash.is`
- **summary**:    Not a stash account. 
 
 NoUnlockChunk
- **interface**: `staking.NoUnlockChunk.is`
- **summary**:    Can not rebond without unlocking chunks. 
 
 Restricted
- **interface**: `staking.Restricted.is`
- **summary**:    Account is restricted from participation in staking. This may happen if the account is  staking in another way already, such as via pool. 
 
 RewardDestinationRestricted
- **interface**: `staking.RewardDestinationRestricted.is`
- **summary**:    Provided reward destination is not allowed. 
 
 TooManyNominators
- **interface**: `staking.TooManyNominators.is`
- **summary**:    There are too many nominators in the system. Governance needs to adjust the staking  settings to keep things safe for the runtime. 
 
 TooManyTargets
- **interface**: `staking.TooManyTargets.is`
- **summary**:    Too many nomination targets supplied. 
 
 TooManyValidators
- **interface**: `staking.TooManyValidators.is`
- **summary**:    There are too many validator candidates in the system. Governance needs to adjust the  staking settings to keep things safe for the runtime. 
 
 VirtualStakerNotAllowed
- **interface**: `staking.VirtualStakerNotAllowed.is`
- **summary**:    Operation not allowed for virtual stakers. 