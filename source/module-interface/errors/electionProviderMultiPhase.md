## electionProviderMultiPhase
 
 BoundNotMet
- **interface**: `electionProviderMultiPhase.BoundNotMet.is`
- **summary**:    Some bound not met 
 
 CallNotAllowed
- **interface**: `electionProviderMultiPhase.CallNotAllowed.is`
- **summary**:    The call is not allowed at this point. 
 
 FallbackFailed
- **interface**: `electionProviderMultiPhase.FallbackFailed.is`
- **summary**:    The fallback failed 
 
 InvalidSubmissionIndex
- **interface**: `electionProviderMultiPhase.InvalidSubmissionIndex.is`
- **summary**:    `Self::insert_submission` returned an invalid index. 
 
 MissingSnapshotMetadata
- **interface**: `electionProviderMultiPhase.MissingSnapshotMetadata.is`
- **summary**:    Snapshot metadata should exist but didn't. 
 
 OcwCallWrongEra
- **interface**: `electionProviderMultiPhase.OcwCallWrongEra.is`
- **summary**:    OCW submitted solution for wrong round 
 
 PreDispatchDifferentRound
- **interface**: `electionProviderMultiPhase.PreDispatchDifferentRound.is`
- **summary**:    Submission was prepared for a different round. 
 
 PreDispatchEarlySubmission
- **interface**: `electionProviderMultiPhase.PreDispatchEarlySubmission.is`
- **summary**:    Submission was too early. 
 
 PreDispatchWeakSubmission
- **interface**: `electionProviderMultiPhase.PreDispatchWeakSubmission.is`
- **summary**:    Submission was too weak, score-wise. 
 
 PreDispatchWrongWinnerCount
- **interface**: `electionProviderMultiPhase.PreDispatchWrongWinnerCount.is`
- **summary**:    Wrong number of winners presented. 
 
 SignedCannotPayDeposit
- **interface**: `electionProviderMultiPhase.SignedCannotPayDeposit.is`
- **summary**:    The origin failed to pay the deposit. 
 
 SignedInvalidWitness
- **interface**: `electionProviderMultiPhase.SignedInvalidWitness.is`
- **summary**:    Witness data to dispatchable is invalid. 
 
 SignedQueueFull
- **interface**: `electionProviderMultiPhase.SignedQueueFull.is`
- **summary**:    The queue was full, and the solution was not better than any of the existing ones. 
 
 SignedTooMuchWeight
- **interface**: `electionProviderMultiPhase.SignedTooMuchWeight.is`
- **summary**:    The signed submission consumes too much weight 
 
 TooManyWinners
- **interface**: `electionProviderMultiPhase.TooManyWinners.is`
- **summary**:    Submitted solution has too many winners 