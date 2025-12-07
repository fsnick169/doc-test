## grandpa
 
 authorities(): `Vec<(SpConsensusGrandpaAppPublic,u64)>`
- **interface**: `grandpa.authorities`
- **summary**:    The current list of authorities. 
 
 currentSetId(): `u64`
- **interface**: `grandpa.currentSetId`
- **summary**:    The number of changes (both in terms of keys and underlying economic responsibilities)  in the "set" of Grandpa validators from genesis. 
 
 nextForced(): `Option<u32>`
- **interface**: `grandpa.nextForced`
- **summary**:    next block number where we can force a change. 
 
 pendingChange(): `Option<PalletGrandpaStoredPendingChange>`
- **interface**: `grandpa.pendingChange`
- **summary**:    Pending change: (signaled at, scheduled change). 
 
 setIdSession(`u64`): `Option<u32>`
- **interface**: `grandpa.setIdSession`
- **summary**:    A mapping from grandpa set ID to the index of the *most recent* session for which its  members were responsible. 

   This is only used for validating equivocation proofs. An equivocation proof must  contains a key-ownership proof for a given session, therefore we need a way to tie  together sessions and GRANDPA set ids, i.e. we need to validate that a validator  was the owner of a given key on a given session, and what the active set ID was  during that session. 

   TWOX-NOTE: `SetId` is not under user control. 
 
 stalled(): `Option<(u32,u32)>`
- **interface**: `grandpa.stalled`
- **summary**:    `true` if we are currently stalled. 
 
 state(): `PalletGrandpaStoredState`
- **interface**: `grandpa.state`
- **summary**:    State of the current authority set. 