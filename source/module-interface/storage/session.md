## session
 
 currentIndex(): `u32`
- **interface**: `session.currentIndex`
- **summary**:    Current index of the session. 
 
 disabledValidators(): `Vec<(u32,Perbill)>`
- **interface**: `session.disabledValidators`
- **summary**:    Indices of disabled validators. 

   The vec is always kept sorted so that we can find whether a given validator is  disabled using binary search. It gets cleared when `on_session_ending` returns  a new set of identities. 
 
 keyOwner(`(SpCoreCryptoKeyTypeId,Bytes)`): `Option<AccountId32>`
- **interface**: `session.keyOwner`
- **summary**:    The owner of a key. The key is the `KeyTypeId` + the encoded key. 
 
 nextKeys(`AccountId32`): `Option<KitchensinkRuntimeSessionKeys>`
- **interface**: `session.nextKeys`
- **summary**:    The next session keys for a validator. 
 
 queuedChanged(): `bool`
- **interface**: `session.queuedChanged`
- **summary**:    True if the underlying economic identities or weighting behind the validators  has changed in the queued validator set. 
 
 queuedKeys(): `Vec<(AccountId32,KitchensinkRuntimeSessionKeys)>`
- **interface**: `session.queuedKeys`
- **summary**:    The queued keys for the next session. When the next session begins, these keys  will be used to determine the validator's session keys. 
 
 validators(): `Vec<AccountId32>`
- **interface**: `session.validators`
- **summary**:    The current set of validators. 