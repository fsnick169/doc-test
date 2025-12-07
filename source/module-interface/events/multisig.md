## multisig
 
 DepositPoked(`AccountId32`, `[u8;32]`, `u128`, `u128`)
- **interface**: `multisig.DepositPoked`
- **summary**:    The deposit for a multisig operation has been updated/poked. 
 
 MultisigApproval(`AccountId32`, `PalletMultisigTimepoint`, `AccountId32`, `[u8;32]`)
- **interface**: `multisig.MultisigApproval`
- **summary**:    A multisig operation has been approved by someone. 
 
 MultisigCancelled(`AccountId32`, `PalletMultisigTimepoint`, `AccountId32`, `[u8;32]`)
- **interface**: `multisig.MultisigCancelled`
- **summary**:    A multisig operation has been cancelled. 
 
 MultisigExecuted(`AccountId32`, `PalletMultisigTimepoint`, `AccountId32`, `[u8;32]`, `Result<Null, SpRuntimeDispatchError>`)
- **interface**: `multisig.MultisigExecuted`
- **summary**:    A multisig operation has been executed. 
 
 NewMultisig(`AccountId32`, `AccountId32`, `[u8;32]`)
- **interface**: `multisig.NewMultisig`
- **summary**:    A new multisig operation has begun. 