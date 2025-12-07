## grandpa
 
 ChangePending
- **interface**: `grandpa.ChangePending.is`
- **summary**:    Attempt to signal GRANDPA change with one already pending. 
 
 DuplicateOffenceReport
- **interface**: `grandpa.DuplicateOffenceReport.is`
- **summary**:    A given equivocation report is valid but already previously reported. 
 
 InvalidEquivocationProof
- **interface**: `grandpa.InvalidEquivocationProof.is`
- **summary**:    An equivocation proof provided as part of an equivocation report is invalid. 
 
 InvalidKeyOwnershipProof
- **interface**: `grandpa.InvalidKeyOwnershipProof.is`
- **summary**:    A key ownership proof provided as part of an equivocation report is invalid. 
 
 PauseFailed
- **interface**: `grandpa.PauseFailed.is`
- **summary**:    Attempt to signal GRANDPA pause when the authority set isn't live  (either paused or already pending pause). 
 
 ResumeFailed
- **interface**: `grandpa.ResumeFailed.is`
- **summary**:    Attempt to signal GRANDPA resume when the authority set isn't paused  (either live or already pending resume). 
 
 TooSoon
- **interface**: `grandpa.TooSoon.is`
- **summary**:    Cannot signal forced change so soon after last. 