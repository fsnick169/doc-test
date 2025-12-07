## identity
 
 basicDeposit: `u128`
- **interface**: `identity.basicDeposit`
- **summary**:    The amount held on deposit for a registered identity. 
 
 byteDeposit: `u128`
- **interface**: `identity.byteDeposit`
- **summary**:    The amount held on deposit per encoded byte for a registered identity. 
 
 maxRegistrars: `u32`
- **interface**: `identity.maxRegistrars`
- **summary**:    Maximum number of registrars allowed in the system. Needed to bound the complexity  of, e.g., updating judgements. 
 
 maxSubAccounts: `u32`
- **interface**: `identity.maxSubAccounts`
- **summary**:    The maximum number of sub-accounts allowed per identified account. 
 
 maxSuffixLength: `u32`
- **interface**: `identity.maxSuffixLength`
- **summary**:    The maximum length of a suffix. 
 
 maxUsernameLength: `u32`
- **interface**: `identity.maxUsernameLength`
- **summary**:    The maximum length of a username, including its suffix and any system-added delimiters. 
 
 pendingUsernameExpiration: `u32`
- **interface**: `identity.pendingUsernameExpiration`
- **summary**:    The number of blocks within which a username grant must be accepted. 
 
 subAccountDeposit: `u128`
- **interface**: `identity.subAccountDeposit`
- **summary**:    The amount held on deposit for a registered subaccount. This should account for the fact  that one storage item's value will increase by the size of an account ID, and there will  be another trie item whose value is the size of an account ID plus 32 bytes. 
 
 usernameDeposit: `u128`
- **interface**: `identity.usernameDeposit`
- **summary**:    The amount held on deposit per registered username. This value should change only in  runtime upgrades with proper migration of existing deposits. 
 
 usernameGracePeriod: `u32`
- **interface**: `identity.usernameGracePeriod`
- **summary**:    The number of blocks that must pass to enable the permanent deletion of a username by  its respective authority. 