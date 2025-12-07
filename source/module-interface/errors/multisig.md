## multisig
 
 AlreadyApproved
- **interface**: `multisig.AlreadyApproved.is`
- **summary**:    Call is already approved by this signatory. 
 
 AlreadyStored
- **interface**: `multisig.AlreadyStored.is`
- **summary**:    The data to be stored is already stored. 
 
 MaxWeightTooLow
- **interface**: `multisig.MaxWeightTooLow.is`
- **summary**:    The maximum weight information provided was too low. 
 
 MinimumThreshold
- **interface**: `multisig.MinimumThreshold.is`
- **summary**:    Threshold must be 2 or greater. 
 
 NoApprovalsNeeded
- **interface**: `multisig.NoApprovalsNeeded.is`
- **summary**:    Call doesn't need any (more) approvals. 
 
 NotFound
- **interface**: `multisig.NotFound.is`
- **summary**:    Multisig operation not found in storage. 
 
 NoTimepoint
- **interface**: `multisig.NoTimepoint.is`
- **summary**:    No timepoint was given, yet the multisig operation is already underway. 
 
 NotOwner
- **interface**: `multisig.NotOwner.is`
- **summary**:    Only the account that originally created the multisig is able to cancel it or update  its deposits. 
 
 SenderInSignatories
- **interface**: `multisig.SenderInSignatories.is`
- **summary**:    The sender was contained in the other signatories; it shouldn't be. 
 
 SignatoriesOutOfOrder
- **interface**: `multisig.SignatoriesOutOfOrder.is`
- **summary**:    The signatories were provided out of order; they should be ordered. 
 
 TooFewSignatories
- **interface**: `multisig.TooFewSignatories.is`
- **summary**:    There are too few signatories in the list. 
 
 TooManySignatories
- **interface**: `multisig.TooManySignatories.is`
- **summary**:    There are too many signatories in the list. 
 
 UnexpectedTimepoint
- **interface**: `multisig.UnexpectedTimepoint.is`
- **summary**:    A timepoint was given, yet no multisig operation is underway. 
 
 WrongTimepoint
- **interface**: `multisig.WrongTimepoint.is`
- **summary**:    A different timepoint was given to the multisig operation that is underway. 