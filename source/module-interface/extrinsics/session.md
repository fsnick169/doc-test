## session
 
 purgeKeys()
- **interface**: `session.purgeKeys`
- **summary**:    Removes any session key(s) of the function caller. 

   This doesn't take effect until the next session. 

   The dispatch origin of this function must be Signed and the account must be either be  convertible to a validator ID using the chain's typical addressing system (this usually  means being a controller account) or directly convertible into a validator ID (which  usually means being a stash account). 

- Complexity: `O(1)` in number of key types. Actual cost depends on the number of length of `T::Keys::key_ids()` which is fixed. 
 
 setKeys(keys: `KitchensinkRuntimeSessionKeys`, proof: `Bytes`)
- **interface**: `session.setKeys`
- **summary**:    Sets the session key(s) of the function caller to `keys`.  Allows an account to set its session key prior to becoming a validator.  This doesn't take effect until the next session. 

   The dispatch origin of this function must be signed. 

- Complexity : `O(1)`. Actual cost depends on the number of length of `T::Keys::key_ids()` which is fixed. 