## multisig
 
 depositBase: `u128`
- **interface**: `multisig.depositBase`
- **summary**:    The base amount of currency needed to reserve for creating a multisig execution or to  store a dispatch call for later. 

   This is held for an additional storage item whose value size is  `4 + sizeof((BlockNumber, Balance, AccountId))` bytes and whose key size is  `32 + sizeof(AccountId)` bytes. 
 
 depositFactor: `u128`
- **interface**: `multisig.depositFactor`
- **summary**:    The amount of currency needed per unit threshold when creating a multisig execution. 

   This is held for adding 32 bytes more into a pre-existing storage value. 
 
 maxSignatories: `u32`
- **interface**: `multisig.maxSignatories`
- **summary**:    The maximum amount of signatories allowed in the multisig. 