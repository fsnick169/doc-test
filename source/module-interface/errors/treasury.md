## treasury
 
 AlreadyAttempted
- **interface**: `treasury.AlreadyAttempted.is`
- **summary**:    The payment has already been attempted. 
 
 EarlyPayout
- **interface**: `treasury.EarlyPayout.is`
- **summary**:    The spend is not yet eligible for payout. 
 
 FailedToConvertBalance
- **interface**: `treasury.FailedToConvertBalance.is`
- **summary**:    The balance of the asset kind is not convertible to the balance of the native asset. 
 
 Inconclusive
- **interface**: `treasury.Inconclusive.is`
- **summary**:    The payment has neither failed nor succeeded yet. 
 
 InsufficientPermission
- **interface**: `treasury.InsufficientPermission.is`
- **summary**:    The spend origin is valid but the amount it is allowed to spend is lower than the  amount to be spent. 
 
 InvalidIndex
- **interface**: `treasury.InvalidIndex.is`
- **summary**:    No proposal, bounty or spend at that index. 
 
 NotAttempted
- **interface**: `treasury.NotAttempted.is`
- **summary**:    The payout was not yet attempted/claimed. 
 
 PayoutError
- **interface**: `treasury.PayoutError.is`
- **summary**:    There was some issue with the mechanism of payment. 
 
 ProposalNotApproved
- **interface**: `treasury.ProposalNotApproved.is`
- **summary**:    Proposal has not been approved. 
 
 SpendExpired
- **interface**: `treasury.SpendExpired.is`
- **summary**:    The spend has expired and cannot be claimed. 
 
 TooManyApprovals
- **interface**: `treasury.TooManyApprovals.is`
- **summary**:    Too many approvals in the queue. 