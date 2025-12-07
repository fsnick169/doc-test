## electionProviderMultiPhase
 
 betterSignedThreshold: `Perbill`
- **interface**: `electionProviderMultiPhase.betterSignedThreshold`
- **summary**:    The minimum amount of improvement to the solution score that defines a solution as  "better" in the Signed phase. 
 
 maxWinners: `u32`
- **interface**: `electionProviderMultiPhase.maxWinners`
- **summary**:    The maximum number of winners that can be elected by this `ElectionProvider`  implementation. 

   Note: This must always be greater or equal to `T::DataProvider::desired_targets()`. 
 
 minerMaxLength: `u32`
- **interface**: `electionProviderMultiPhase.minerMaxLength`
 
 minerMaxVotesPerVoter: `u32`
- **interface**: `electionProviderMultiPhase.minerMaxVotesPerVoter`
 
 minerMaxWeight: `SpWeightsWeightV2Weight`
- **interface**: `electionProviderMultiPhase.minerMaxWeight`
 
 minerMaxWinners: `u32`
- **interface**: `electionProviderMultiPhase.minerMaxWinners`
 
 minerTxPriority: `u64`
- **interface**: `electionProviderMultiPhase.minerTxPriority`
- **summary**:    The priority of the unsigned transaction submitted in the unsigned-phase 
 
 offchainRepeat: `u32`
- **interface**: `electionProviderMultiPhase.offchainRepeat`
- **summary**:    The repeat threshold of the offchain worker. 

   For example, if it is 5, that means that at least 5 blocks will elapse between attempts  to submit the worker's solution. 
 
 signedDepositByte: `u128`
- **interface**: `electionProviderMultiPhase.signedDepositByte`
- **summary**:    Per-byte deposit for a signed solution. 
 
 signedDepositWeight: `u128`
- **interface**: `electionProviderMultiPhase.signedDepositWeight`
- **summary**:    Per-weight deposit for a signed solution. 
 
 signedMaxRefunds: `u32`
- **interface**: `electionProviderMultiPhase.signedMaxRefunds`
- **summary**:    The maximum amount of unchecked solutions to refund the call fee for. 
 
 signedMaxSubmissions: `u32`
- **interface**: `electionProviderMultiPhase.signedMaxSubmissions`
- **summary**:    Maximum number of signed submissions that can be queued. 

   It is best to avoid adjusting this during an election, as it impacts downstream data  structures. In particular, `SignedSubmissionIndices<T>` is bounded on this value. If you  update this value during an election, you _must_ ensure that  `SignedSubmissionIndices.len()` is less than or equal to the new value. Otherwise,  attempts to submit new solutions may cause a runtime panic. 
 
 signedMaxWeight: `SpWeightsWeightV2Weight`
- **interface**: `electionProviderMultiPhase.signedMaxWeight`
- **summary**:    Maximum weight of a signed solution. 

   If [`Config::MinerConfig`] is being implemented to submit signed solutions (outside of  this pallet), then [`MinerConfig::solution_weight`] is used to compare against  this value. 
 
 signedRewardBase: `u128`
- **interface**: `electionProviderMultiPhase.signedRewardBase`
- **summary**:    Base reward for a signed solution 