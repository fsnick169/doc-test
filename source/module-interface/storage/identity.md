## identity
 
 authorityOf(`Bytes`): `Option<PalletIdentityAuthorityProperties>`
- **interface**: `identity.authorityOf`
- **summary**:    A map of the accounts who are authorized to grant usernames. 
 
 identityOf(`AccountId32`): `Option<PalletIdentityRegistration>`
- **interface**: `identity.identityOf`
- **summary**:    Information that is pertinent to identify the entity behind an account. First item is the  registration, second is the account's primary username. 

   TWOX-NOTE: OK ― `AccountId` is a secure hash. 
 
 pendingUsernames(`Bytes`): `Option<(AccountId32,u32,PalletIdentityProvider)>`
- **interface**: `identity.pendingUsernames`
- **summary**:    Usernames that an authority has granted, but that the account controller has not confirmed  that they want it. Used primarily in cases where the `AccountId` cannot provide a signature  because they are a pure proxy, multisig, etc. In order to confirm it, they should call  [accept_username]. 

   First tuple item is the account and second is the acceptance deadline. 
 
 registrars(): `Vec<Option<PalletIdentityRegistrarInfo>>`
- **interface**: `identity.registrars`
- **summary**:    The set of registrars. Not expected to get very big as can only be added through a  special origin (likely a council motion). 

   The index into this can be cast to `RegistrarIndex` to get a valid value. 
 
 subsOf(`AccountId32`): `(u128,Vec<AccountId32>)`
- **interface**: `identity.subsOf`
- **summary**:    Alternative "sub" identities of this account. 

   The first item is the deposit, the second is a vector of the accounts. 

   TWOX-NOTE: OK ― `AccountId` is a secure hash. 
 
 superOf(`AccountId32`): `Option<(AccountId32,Data)>`
- **interface**: `identity.superOf`
- **summary**:    The super-identity of an alternative "sub" identity together with its name, within that  context. If the account is not some other account's sub-identity, then just `None`. 
 
 unbindingUsernames(`Bytes`): `Option<u32>`
- **interface**: `identity.unbindingUsernames`
- **summary**:    Usernames for which the authority that granted them has started the removal process by  unbinding them. Each unbinding username maps to its grace period expiry, which is the first  block in which the username could be deleted through a  [remove_username]  call. 
 
 usernameInfoOf(`Bytes`): `Option<PalletIdentityUsernameInformation>`
- **interface**: `identity.usernameInfoOf`
- **summary**:    Reverse lookup from `username` to the `AccountId` that has registered it and the provider of  the username. The `owner` value should be a key in the `UsernameOf` map, but it may not if  the user has cleared their username or it has been removed. 

   Multiple usernames may map to the same `AccountId`, but `UsernameOf` will only map to one  primary username. 
 
 usernameOf(`AccountId32`): `Option<Bytes>`
- **interface**: `identity.usernameOf`
- **summary**:    Identifies the primary username of an account. 