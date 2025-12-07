## contracts
 
 apiVersion: `u16`
- **interface**: `contracts.apiVersion`
- **summary**:    The version of the HostFn APIs that are available in the runtime. 

   Only valid value is `()`. 
 
 codeHashLockupDepositPercent: `Perbill`
- **interface**: `contracts.codeHashLockupDepositPercent`
- **summary**:    The percentage of the storage deposit that should be held for using a code hash.  Instantiating a contract, or calling [`chain_extension::Ext::lock_delegate_dependency`]  protects the code from being removed. In order to prevent abuse these actions are  protected with a percentage of the code deposit. 
 
 defaultDepositLimit: `u128`
- **interface**: `contracts.defaultDepositLimit`
- **summary**:    Fallback value to limit the storage deposit if it's not being set by the caller. 
 
 depositPerByte: `u128`
- **interface**: `contracts.depositPerByte`
- **summary**:    The amount of balance a caller has to pay for each byte of storage. 

   # Note 

   Changing this value for an existing chain might need a storage migration. 
 
 depositPerItem: `u128`
- **interface**: `contracts.depositPerItem`
- **summary**:    The amount of balance a caller has to pay for each storage item. 

   # Note 

   Changing this value for an existing chain might need a storage migration. 
 
 environment: `PalletContractsEnvironment`
- **interface**: `contracts.environment`
- **summary**:    Type that bundles together all the runtime configurable interface types. 

   This is not a real config. We just mention the type here as constant so that  its type appears in the metadata. Only valid value is `()`. 
 
 maxCodeLen: `u32`
- **interface**: `contracts.maxCodeLen`
- **summary**:    The maximum length of a contract code in bytes. 

   The value should be chosen carefully taking into the account the overall memory limit  your runtime has. 
 
 maxDebugBufferLen: `u32`
- **interface**: `contracts.maxDebugBufferLen`
- **summary**:    The maximum length of the debug buffer in bytes. 
 
 maxDelegateDependencies: `u32`
- **interface**: `contracts.maxDelegateDependencies`
- **summary**:    The maximum number of delegate_dependencies that a contract can lock with  [`chain_extension::Ext::lock_delegate_dependency`]. 
 
 maxStorageKeyLen: `u32`
- **interface**: `contracts.maxStorageKeyLen`
- **summary**:    The maximum allowable length in bytes for storage keys. 
 
 maxTransientStorageSize: `u32`
- **interface**: `contracts.maxTransientStorageSize`
- **summary**:    The maximum size of the transient storage in bytes.  This includes keys, values, and previous entries used for storage rollback. 
 
 schedule: `PalletContractsSchedule`
- **interface**: `contracts.schedule`
- **summary**:    Cost schedule and limits. 
 
 unsafeUnstableInterface: `bool`
- **interface**: `contracts.unsafeUnstableInterface`
- **summary**:    Make contract callable functions marked as `#[unstable]` available. 

   Contracts that use `#[unstable]` functions won't be able to be uploaded unless  this is set to `true`. This is only meant for testnets and dev nodes in order to  experiment with new features. 

   # Warning 

   Do **not** set to `true` on productions chains. 