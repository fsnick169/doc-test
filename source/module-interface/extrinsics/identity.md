## identity
 
 acceptUsername(username: `Bytes`)
- **interface**: `identity.acceptUsername`
- **summary**:    Accept a given username that an `authority` granted. The call must include the full  username, as in `username.suffix`. 
 
 addRegistrar(account: `MultiAddress`)
- **interface**: `identity.addRegistrar`
- **summary**:    Add a registrar to the system. 

   The dispatch origin for this call must be `T::RegistrarOrigin`. 

   - `account`: the account of the registrar. 

   Emits `RegistrarAdded` if successful. 
 
 addSub(sub: `MultiAddress`, data: `Data`)
- **interface**: `identity.addSub`
- **summary**:    Add the given account to the sender's subs. 

   Payment: Balance reserved by a previous `set_subs` call for one sub will be repatriated  to the sender. 

   The dispatch origin for this call must be _Signed_ and the sender must have a registered  sub identity of `sub`. 
 
 addUsernameAuthority(authority: `MultiAddress`, suffix: `Bytes`, allocation: `u32`)
- **interface**: `identity.addUsernameAuthority`
- **summary**:    Add an `AccountId` with permission to grant usernames with a given `suffix` appended. 

   The authority can grant up to `allocation` usernames. To top up the allocation or  change the account used to grant usernames, this call can be used with the updated  parameters to overwrite the existing configuration. 
 
 cancelRequest(reg_index: `u32`)
- **interface**: `identity.cancelRequest`
- **summary**:    Cancel a previous request. 

   Payment: A previously reserved deposit is returned on success. 

   The dispatch origin for this call must be _Signed_ and the sender must have a  registered identity. 

   - `reg_index`: The index of the registrar whose judgement is no longer requested. 

   Emits `JudgementUnrequested` if successful. 
 
 clearIdentity()
- **interface**: `identity.clearIdentity`
- **summary**:    Clear an account's identity info and all sub-accounts and return all deposits. 

   Payment: All reserved balances on the account are returned. 

   The dispatch origin for this call must be _Signed_ and the sender must have a registered  identity. 

   Emits `IdentityCleared` if successful. 
 
 killIdentity(target: `MultiAddress`)
- **interface**: `identity.killIdentity`
- **summary**:    Remove an account's identity and sub-account information and slash the deposits. 

   Payment: Reserved balances from `set_subs` and `set_identity` are slashed and handled by  `Slash`. Verification request deposits are not returned; they should be cancelled  manually using `cancel_request`. 

   The dispatch origin for this call must match `T::ForceOrigin`. 

   - `target`: the account whose identity the judgement is upon. This must be an account  with a registered identity. 

   Emits `IdentityKilled` if successful. 
 
 killUsername(username: `Bytes`)
- **interface**: `identity.killUsername`
- **summary**:    Call with [ForceOrigin](crate::Config::ForceOrigin) privileges which deletes a username  and slashes any deposit associated with it. 
 
 provideJudgement(reg_index: `Compact<u32>`, target: `MultiAddress`, judgement: `PalletIdentityJudgement`, identity: `H256`)
- **interface**: `identity.provideJudgement`
- **summary**:    Provide a judgement for an account's identity. 

   The dispatch origin for this call must be _Signed_ and the sender must be the account  of the registrar whose index is `reg_index`. 

   - `reg_index`: the index of the registrar whose judgement is being made. 

  - `target`: the account whose identity the judgement is upon. This must be an account with a registered identity. 

  - `judgement`: the judgement of the registrar of index `reg_index` about `target`.

  - `identity`: The hash of the [`IdentityInformationProvider`] for that the judgement is provided. 

   Note: Judgements do not apply to a username. 

   Emits `JudgementGiven` if successful. 
 
 quitSub()
- **interface**: `identity.quitSub`
- **summary**:    Remove the sender as a sub-account. 

   Payment: Balance reserved by a previous `set_subs` call for one sub will be repatriated  to the sender (*not* the original depositor). 

   The dispatch origin for this call must be _Signed_ and the sender must have a registered  super-identity. 

   NOTE: This should not normally be used, but is provided in the case that the non-  controller of an account is maliciously registered as a sub-account. 
 
 removeExpiredApproval(username: `Bytes`)
- **interface**: `identity.removeExpiredApproval`
- **summary**:    Remove an expired username approval. The username was approved by an authority but never  accepted by the user and must now be beyond its expiration. The call must include the  full username, as in `username.suffix`. 
 
 removeSub(sub: `MultiAddress`)
- **interface**: `identity.removeSub`
- **summary**:    Remove the given account from the sender's subs. 

   Payment: Balance reserved by a previous `set_subs` call for one sub will be repatriated  to the sender. 

   The dispatch origin for this call must be _Signed_ and the sender must have a registered  sub identity of `sub`. 
 
 removeUsername(username: `Bytes`)
- **interface**: `identity.removeUsername`
- **summary**:    Permanently delete a username which has been unbinding for longer than the grace period.  Caller is refunded the fee if the username expired and the removal was successful. 
 
 removeUsernameAuthority(suffix: `Bytes`, authority: `MultiAddress`)
- **interface**: `identity.removeUsernameAuthority`
- **summary**:    Remove `authority` from the username authorities. 
 
 renameSub(sub: `MultiAddress`, data: `Data`)
- **interface**: `identity.renameSub`
- **summary**:    Alter the associated name of the given sub-account. 

   The dispatch origin for this call must be _Signed_ and the sender must have a registered  sub identity of `sub`. 
 
 requestJudgement(reg_index: `Compact<u32>`, max_fee: `Compact<u128>`)
- **interface**: `identity.requestJudgement`
- **summary**:    Request a judgement from a registrar. 

   Payment: At most `max_fee` will be reserved for payment to the registrar if judgement  given. 

   The dispatch origin for this call must be _Signed_ and the sender must have a  registered identity. 

   - `reg_index`: The index of the registrar whose judgement is requested. 

  - `max_fee`: The maximum fee that may be paid. This should just be auto-populated as:

   ```nocompile  Registrars::<T>::get().get(reg_index).unwrap().fee  ``` 

   Emits `JudgementRequested` if successful. 
 
 setAccountId(index: `Compact<u32>`, new: `MultiAddress`)
- **interface**: `identity.setAccountId`
- **summary**:    Change the account associated with a registrar. 

   The dispatch origin for this call must be _Signed_ and the sender must be the account  of the registrar whose index is `index`. 

   - `index`: the index of the registrar whose fee is to be set. 

  - `new`: the new account ID.
 
 setFee(index: `Compact<u32>`, fee: `Compact<u128>`)
- **interface**: `identity.setFee`
- **summary**:    Set the fee required for a judgement to be requested from a registrar. 

   The dispatch origin for this call must be _Signed_ and the sender must be the account  of the registrar whose index is `index`. 

   - `index`: the index of the registrar whose fee is to be set. 

  - `fee`: the new fee.
 
 setFields(index: `Compact<u32>`, fields: `u64`)
- **interface**: `identity.setFields`
- **summary**:    Set the field information for a registrar. 

   The dispatch origin for this call must be _Signed_ and the sender must be the account  of the registrar whose index is `index`. 

   - `index`: the index of the registrar whose fee is to be set. 

  - `fields`: the fields that the registrar concerns themselves with.
 
 setIdentity(info: `PalletIdentityLegacyIdentityInfo`)
- **interface**: `identity.setIdentity`
- **summary**:    Set an account's identity information and reserve the appropriate deposit. 

   If the account already has identity information, the deposit is taken as part payment  for the new deposit. 

   The dispatch origin for this call must be _Signed_. 

   - `info`: The identity information. 

   Emits `IdentitySet` if successful. 
 
 setPrimaryUsername(username: `Bytes`)
- **interface**: `identity.setPrimaryUsername`
- **summary**:    Set a given username as the primary. The username should include the suffix. 
 
 setSubs(subs: `Vec<(AccountId32,Data)>`)
- **interface**: `identity.setSubs`
- **summary**:    Set the sub-accounts of the sender. 

   Payment: Any aggregate balance reserved by previous `set_subs` calls will be returned  and an amount `SubAccountDeposit` will be reserved for each item in `subs`. 

   The dispatch origin for this call must be _Signed_ and the sender must have a registered  identity. 

   - `subs`: The identity's (new) sub-accounts. 
 
 setUsernameFor(who: `MultiAddress`, username: `Bytes`, signature: `Option<SpRuntimeMultiSignature>`, use_allocation: `bool`)
- **interface**: `identity.setUsernameFor`
- **summary**:    Set the username for `who`. Must be called by a username authority. 

   If `use_allocation` is set, the authority must have a username allocation available to  spend. Otherwise, the authority will need to put up a deposit for registering the  username. 

   Users can either pre-sign their usernames or  accept them later. 

   Usernames must: 

  - Only contain lowercase ASCII characters or digits.

  - When combined with the suffix of the issuing authority be _less than_ the `MaxUsernameLength`. 
 
 unbindUsername(username: `Bytes`)
- **interface**: `identity.unbindUsername`
- **summary**:    Start the process of removing a username by placing it in the unbinding usernames map.  Once the grace period has passed, the username can be deleted by calling  [remove_username](crate::Call::remove_username).