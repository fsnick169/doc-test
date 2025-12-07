## electionProviderMultiPhase
 
 currentPhase(): `PalletElectionProviderMultiPhasePhase`
- **interface**: `electionProviderMultiPhase.currentPhase`
- **summary**:    Current phase. 
 
 desiredTargets(): `Option<u32>`
- **interface**: `electionProviderMultiPhase.desiredTargets`
- **summary**:    Desired number of targets to elect for this round. 

   Only exists when [`Snapshot`] is present.  Note: This storage type must only be mutated through [`SnapshotWrapper`]. 
 
 minimumUntrustedScore(): `Option<SpNposElectionsElectionScore>`
- **interface**: `electionProviderMultiPhase.minimumUntrustedScore`
- **summary**:    The minimum score that each 'untrusted' solution must attain in order to be considered  feasible. 

   Can be set via `set_minimum_untrusted_score`. 
 
 queuedSolution(): `Option<PalletElectionProviderMultiPhaseReadySolution>`
- **interface**: `electionProviderMultiPhase.queuedSolution`
- **summary**:    Current best solution, signed or unsigned, queued to be returned upon `elect`. 

   Always sorted by score. 
 
 round(): `u32`
- **interface**: `electionProviderMultiPhase.round`
- **summary**:    Internal counter for the number of rounds. 

   This is useful for de-duplication of transactions submitted to the pool, and general  diagnostics of the pallet. 

   This is merely incremented once per every time that an upstream `elect` is called. 
 
 signedSubmissionIndices(): `Vec<(SpNposElectionsElectionScore,u32,u32)>`
- **interface**: `electionProviderMultiPhase.signedSubmissionIndices`
- **summary**:    A sorted, bounded vector of `(score, block_number, index)`, where each `index` points to a  value in `SignedSubmissions`. 

   We never need to process more than a single signed submission at a time. Signed submissions  can be quite large, so we're willing to pay the cost of multiple database accesses to access  them one at a time instead of reading and decoding all of them at once. 
 
 signedSubmissionNextIndex(): `u32`
- **interface**: `electionProviderMultiPhase.signedSubmissionNextIndex`
- **summary**:    The next index to be assigned to an incoming signed submission. 

   Every accepted submission is assigned a unique index; that index is bound to that particular  submission for the duration of the election. On election finalization, the next index is  reset to 0. 

   We can't just use `SignedSubmissionIndices.len()`, because that's a bounded set; past its  capacity, it will simply saturate. We can't just iterate over `SignedSubmissionsMap`,  because iteration is slow. Instead, we store the value here. 
 
 signedSubmissionsMap(`u32`): `Option<PalletElectionProviderMultiPhaseSignedSignedSubmission>`
- **interface**: `electionProviderMultiPhase.signedSubmissionsMap`
- **summary**:    Unchecked, signed solutions. 

   Together with `SubmissionIndices`, this stores a bounded set of `SignedSubmissions` while  allowing us to keep only a single one in memory at a time. 

   Twox note: the key of the map is an auto-incrementing index which users cannot inspect or  affect; we shouldn't need a cryptographically secure hasher. 
 
 snapshot(): `Option<PalletElectionProviderMultiPhaseRoundSnapshot>`
- **interface**: `electionProviderMultiPhase.snapshot`
- **summary**:    Snapshot data of the round. 

   This is created at the beginning of the signed phase and cleared upon calling `elect`.  Note: This storage type must only be mutated through [`SnapshotWrapper`]. 
 
 snapshotMetadata(): `Option<PalletElectionProviderMultiPhaseSolutionOrSnapshotSize>`
- **interface**: `electionProviderMultiPhase.snapshotMetadata`
- **summary**:    The metadata of the [`RoundSnapshot`] 

   Only exists when [`Snapshot`] is present.  Note: This storage type must only be mutated through [`SnapshotWrapper`]. 