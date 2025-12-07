## babe
 
 authorities(): `Vec<(SpConsensusBabeAppPublic,u64)>`
- **interface**: `babe.authorities`
- **summary**:    Current epoch authorities. 
 
 authorVrfRandomness(): `Option<[u8;32]>`
- **interface**: `babe.authorVrfRandomness`
- **summary**:    This field should always be populated during block processing unless  secondary plain slots are enabled (which don't contain a VRF output). 

   It is set in `on_finalize`, before it will contain the value from the last block. 
 
 currentSlot(): `u64`
- **interface**: `babe.currentSlot`
- **summary**:    Current slot number. 
 
 epochConfig(): `Option<SpConsensusBabeBabeEpochConfiguration>`
- **interface**: `babe.epochConfig`
- **summary**:    The configuration for the current epoch. Should never be `None` as it is initialized in  genesis. 
 
 epochIndex(): `u64`
- **interface**: `babe.epochIndex`
- **summary**:    Current epoch index. 
 
 epochStart(): `(u32,u32)`
- **interface**: `babe.epochStart`
- **summary**:    The block numbers when the last and current epoch have started, respectively `N-1` and  `N`.  NOTE: We track this is in order to annotate the block number when a given pool of  entropy was fixed (i.e. it was known to chain observers). Since epochs are defined in  slots, which may be skipped, the block numbers may not line up with the slot numbers. 
 
 genesisSlot(): `u64`
- **interface**: `babe.genesisSlot`
- **summary**:    The slot at which the first epoch actually started. This is 0  until the first block of the chain. 
 
 initialized(): `Option<Option<SpConsensusBabeDigestsPreDigest>>`
- **interface**: `babe.initialized`
- **summary**:    Temporary value (cleared at block finalization) which is `Some`  if per-block initialization has already been called for current block. 
 
 lateness(): `u32`
- **interface**: `babe.lateness`
- **summary**:    How late the current block is compared to its parent. 

   This entry is populated as part of block execution and is cleaned up  on block finalization. Querying this storage entry outside of block  execution context should always yield zero. 
 
 nextAuthorities(): `Vec<(SpConsensusBabeAppPublic,u64)>`
- **interface**: `babe.nextAuthorities`
- **summary**:    Next epoch authorities. 
 
 nextEpochConfig(): `Option<SpConsensusBabeBabeEpochConfiguration>`
- **interface**: `babe.nextEpochConfig`
- **summary**:    The configuration for the next epoch, `None` if the config will not change  (you can fallback to `EpochConfig` instead in that case). 
 
 nextRandomness(): `[u8;32]`
- **interface**: `babe.nextRandomness`
- **summary**:    Next epoch randomness. 
 
 pendingEpochConfigChange(): `Option<SpConsensusBabeDigestsNextConfigDescriptor>`
- **interface**: `babe.pendingEpochConfigChange`
- **summary**:    Pending epoch configuration change that will be applied when the next epoch is enacted. 
 
 randomness(): `[u8;32]`
- **interface**: `babe.randomness`
- **summary**:    The epoch randomness for the *current* epoch. 

- Security:    This MUST NOT be used for gambling, as it can be influenced by a  malicious validator in the short term. It MAY be used in many  cryptographic protocols, however, so long as one remembers that this  (like everything else on-chain) it is public. For example, it can be  used where a number is needed that cannot have been chosen by an  adversary, for purposes such as public-coin zero-knowledge proofs. 
 
 segmentIndex(): `u32`
- **interface**: `babe.segmentIndex`
- **summary**:    Randomness under construction. 
 
 skippedEpochs(): `Vec<(u64,u32)>`
- **interface**: `babe.skippedEpochs`
- **summary**:    A list of the last 100 skipped epochs and the corresponding session index  when the epoch was skipped. 

   This is only used for validating equivocation proofs. An equivocation proof  must contains a key-ownership proof for a given session, therefore we need a  way to tie together sessions and epoch indices, i.e. we need to validate that  a validator was the owner of a given key on a given session, and what the  active epoch index was during that session. 
 
 underConstruction(`u32`): `Vec<[u8;32]>`
- **interface**: `babe.underConstruction`
- **summary**:    TWOX-NOTE: `SegmentIndex` is an increasing integer, so this is okay. 