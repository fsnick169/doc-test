## electionProviderMultiPhase
 
 ElectionFailed()
- **interface**: `electionProviderMultiPhase.ElectionFailed`
- **summary**:    An election failed. 
 
 ElectionFinalized(`PalletElectionProviderMultiPhaseElectionCompute`, `SpNposElectionsElectionScore`)
- **interface**: `electionProviderMultiPhase.ElectionFinalized`
- **summary**:    The election has been finalized, with the given computation and score. 
 
 PhaseTransitioned(`PalletElectionProviderMultiPhasePhase`, `PalletElectionProviderMultiPhasePhase`, `u32`)
- **interface**: `electionProviderMultiPhase.PhaseTransitioned`
- **summary**:    There was a phase transition in a given round. 
 
 Rewarded(`AccountId32`, `u128`)
- **interface**: `electionProviderMultiPhase.Rewarded`
- **summary**:    An account has been rewarded for their signed submission being finalized. 
 
 Slashed(`AccountId32`, `u128`)
- **interface**: `electionProviderMultiPhase.Slashed`
- **summary**:    An account has been slashed for submitting an invalid signed submission. 
 
 SolutionStored(`PalletElectionProviderMultiPhaseElectionCompute`, `Option<AccountId32>`, `bool`)
- **interface**: `electionProviderMultiPhase.SolutionStored`
- **summary**:    A solution was stored with the given compute. The `origin` indicates the origin of the solution. If `origin` is `Some(AccountId)`,  the stored solution was submitted in the signed phase by a miner with the `AccountId`.  Otherwise, the solution was stored either during the unsigned phase or by  `T::ForceOrigin`. The `bool` is `true` when a previous solution was ejected to make  room for this one. 