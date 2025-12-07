## identity
 
 AuthorityAdded(`AccountId32`)
- **interface**: `identity.AuthorityAdded`
- **summary**:    A username authority was added. 
 
 AuthorityRemoved(`AccountId32`)
- **interface**: `identity.AuthorityRemoved`
- **summary**:    A username authority was removed. 
 
 DanglingUsernameRemoved(`AccountId32`, `Bytes`)
- **interface**: `identity.DanglingUsernameRemoved`
- **summary**:    A dangling username (as in, a username corresponding to an account that has removed its  identity) has been removed. 
 
 IdentityCleared(`AccountId32`, `u128`)
- **interface**: `identity.IdentityCleared`
- **summary**:    A name was cleared, and the given balance returned. 
 
 IdentityKilled(`AccountId32`, `u128`)
- **interface**: `identity.IdentityKilled`
- **summary**:    A name was removed and the given balance slashed. 
 
 IdentitySet(`AccountId32`)
- **interface**: `identity.IdentitySet`
- **summary**:    A name was set or reset (which will remove all judgements). 
 
 JudgementGiven(`AccountId32`, `u32`)
- **interface**: `identity.JudgementGiven`
- **summary**:    A judgement was given by a registrar. 
 
 JudgementRequested(`AccountId32`, `u32`)
- **interface**: `identity.JudgementRequested`
- **summary**:    A judgement was asked from a registrar. 
 
 JudgementUnrequested(`AccountId32`, `u32`)
- **interface**: `identity.JudgementUnrequested`
- **summary**:    A judgement request was retracted. 
 
 PreapprovalExpired(`AccountId32`)
- **interface**: `identity.PreapprovalExpired`
- **summary**:    A queued username passed its expiration without being claimed and was removed. 
 
 PrimaryUsernameSet(`AccountId32`, `Bytes`)
- **interface**: `identity.PrimaryUsernameSet`
- **summary**:    A username was set as a primary and can be looked up from `who`. 
 
 RegistrarAdded(`u32`)
- **interface**: `identity.RegistrarAdded`
- **summary**:    A registrar was added. 
 
 SubIdentitiesSet(`AccountId32`, `u32`, `u128`)
- **interface**: `identity.SubIdentitiesSet`
- **summary**:    An account's sub-identities were set (in bulk). 
 
 SubIdentityAdded(`AccountId32`, `AccountId32`, `u128`)
- **interface**: `identity.SubIdentityAdded`
- **summary**:    A sub-identity was added to an identity and the deposit paid. 
 
 SubIdentityRemoved(`AccountId32`, `AccountId32`, `u128`)
- **interface**: `identity.SubIdentityRemoved`
- **summary**:    A sub-identity was removed from an identity and the deposit freed. 
 
 SubIdentityRenamed(`AccountId32`, `AccountId32`)
- **interface**: `identity.SubIdentityRenamed`
- **summary**:    A given sub-account's associated name was changed by its super-identity. 
 
 SubIdentityRevoked(`AccountId32`, `AccountId32`, `u128`)
- **interface**: `identity.SubIdentityRevoked`
- **summary**:    A sub-identity was cleared, and the given deposit repatriated from the  main identity account to the sub-identity account. 
 
 UsernameKilled(`Bytes`)
- **interface**: `identity.UsernameKilled`
- **summary**:    A username has been killed. 
 
 UsernameQueued(`AccountId32`, `Bytes`, `u32`)
- **interface**: `identity.UsernameQueued`
- **summary**:    A username was queued, but `who` must accept it prior to `expiration`. 
 
 UsernameRemoved(`Bytes`)
- **interface**: `identity.UsernameRemoved`
- **summary**:    A username has been removed. 
 
 UsernameSet(`AccountId32`, `Bytes`)
- **interface**: `identity.UsernameSet`
- **summary**:    A username was set for `who`. 
 
 UsernameUnbound(`Bytes`)
- **interface**: `identity.UsernameUnbound`
- **summary**:    A username has been unbound. 