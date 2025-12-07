## identity
 
 AlreadyClaimed
- **interface**: `identity.AlreadyClaimed.is`
- **summary**:    Account ID is already named. 
 
 AlreadyUnbinding
- **interface**: `identity.AlreadyUnbinding.is`
- **summary**:    The username cannot be unbound because it is already unbinding. 
 
 EmptyIndex
- **interface**: `identity.EmptyIndex.is`
- **summary**:    Empty index. 
 
 FeeChanged
- **interface**: `identity.FeeChanged.is`
- **summary**:    Fee is changed. 
 
 InsufficientPrivileges
- **interface**: `identity.InsufficientPrivileges.is`
- **summary**:    The action cannot be performed because of insufficient privileges (e.g. authority  trying to unbind a username provided by the system). 
 
 InvalidIndex
- **interface**: `identity.InvalidIndex.is`
- **summary**:    The index is invalid. 
 
 InvalidJudgement
- **interface**: `identity.InvalidJudgement.is`
- **summary**:    Invalid judgement. 
 
 InvalidSignature
- **interface**: `identity.InvalidSignature.is`
- **summary**:    The signature on a username was not valid. 
 
 InvalidSuffix
- **interface**: `identity.InvalidSuffix.is`
- **summary**:    The provided suffix is too long. 
 
 InvalidTarget
- **interface**: `identity.InvalidTarget.is`
- **summary**:    The target is invalid. 
 
 InvalidUsername
- **interface**: `identity.InvalidUsername.is`
- **summary**:    The username does not meet the requirements. 
 
 JudgementForDifferentIdentity
- **interface**: `identity.JudgementForDifferentIdentity.is`
- **summary**:    The provided judgement was for a different identity. 
 
 JudgementGiven
- **interface**: `identity.JudgementGiven.is`
- **summary**:    Judgement given. 
 
 JudgementPaymentFailed
- **interface**: `identity.JudgementPaymentFailed.is`
- **summary**:    Error that occurs when there is an issue paying for judgement. 
 
 NoAllocation
- **interface**: `identity.NoAllocation.is`
- **summary**:    The authority cannot allocate any more usernames. 
 
 NoIdentity
- **interface**: `identity.NoIdentity.is`
- **summary**:    No identity found. 
 
 NotExpired
- **interface**: `identity.NotExpired.is`
- **summary**:    The username cannot be forcefully removed because it can still be accepted. 
 
 NotFound
- **interface**: `identity.NotFound.is`
- **summary**:    Account isn't found. 
 
 NotNamed
- **interface**: `identity.NotNamed.is`
- **summary**:    Account isn't named. 
 
 NotOwned
- **interface**: `identity.NotOwned.is`
- **summary**:    Sub-account isn't owned by sender. 
 
 NotSub
- **interface**: `identity.NotSub.is`
- **summary**:    Sender is not a sub-account. 
 
 NotUnbinding
- **interface**: `identity.NotUnbinding.is`
- **summary**:    The username cannot be removed because it is not unbinding. 
 
 NotUsernameAuthority
- **interface**: `identity.NotUsernameAuthority.is`
- **summary**:    The sender does not have permission to issue a username. 
 
 NoUsername
- **interface**: `identity.NoUsername.is`
- **summary**:    The requested username does not exist. 
 
 RequiresSignature
- **interface**: `identity.RequiresSignature.is`
- **summary**:    Setting this username requires a signature, but none was provided. 
 
 StickyJudgement
- **interface**: `identity.StickyJudgement.is`
- **summary**:    Sticky judgement. 
 
 TooEarly
- **interface**: `identity.TooEarly.is`
- **summary**:    The username cannot be removed because it's still in the grace period. 
 
 TooManyRegistrars
- **interface**: `identity.TooManyRegistrars.is`
- **summary**:    Maximum amount of registrars reached. Cannot add any more. 
 
 TooManySubAccounts
- **interface**: `identity.TooManySubAccounts.is`
- **summary**:    Too many subs-accounts. 
 
 UsernameTaken
- **interface**: `identity.UsernameTaken.is`
- **summary**:    The username is already taken. 