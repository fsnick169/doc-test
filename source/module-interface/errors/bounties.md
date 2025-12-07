## bounties
 
 HasActiveChildBounty
- **interface**: `bounties.HasActiveChildBounty.is`
- **summary**:    The bounty cannot be closed because it has active child bounties. 
 
 InsufficientProposersBalance
- **interface**: `bounties.InsufficientProposersBalance.is`
- **summary**:    Proposer's balance is too low. 
 
 InvalidFee
- **interface**: `bounties.InvalidFee.is`
- **summary**:    Invalid bounty fee. 
 
 InvalidIndex
- **interface**: `bounties.InvalidIndex.is`
- **summary**:    No proposal or bounty at that index. 
 
 InvalidValue
- **interface**: `bounties.InvalidValue.is`
- **summary**:    Invalid bounty value. 
 
 PendingPayout
- **interface**: `bounties.PendingPayout.is`
- **summary**:    A bounty payout is pending.  To cancel the bounty, you must unassign and slash the curator. 
 
 Premature
- **interface**: `bounties.Premature.is`
- **summary**:    The bounties cannot be claimed/closed because it's still in the countdown period. 
 
 ReasonTooBig
- **interface**: `bounties.ReasonTooBig.is`
- **summary**:    The reason given is just too big. 
 
 RequireCurator
- **interface**: `bounties.RequireCurator.is`
- **summary**:    Require bounty curator. 
 
 TooManyQueued
- **interface**: `bounties.TooManyQueued.is`
- **summary**:    Too many approvals are already queued. 
 
 UnexpectedStatus
- **interface**: `bounties.UnexpectedStatus.is`
- **summary**:    The bounty status is unexpected. 