## contracts
 
 codeInfoOf(`H256`): `Option<PalletContractsWasmCodeInfo>`
- **interface**: `contracts.codeInfoOf`
- **summary**:    A mapping from a contract's code hash to its code info. 
 
 contractInfoOf(`AccountId32`): `Option<PalletContractsStorageContractInfo>`
- **interface**: `contracts.contractInfoOf`
- **summary**:    The code associated with a given account. 

   TWOX-NOTE: SAFE since `AccountId` is a secure hash. 
 
 deletionQueue(`u32`): `Option<Bytes>`
- **interface**: `contracts.deletionQueue`
- **summary**:    Evicted contracts that await child trie deletion. 

   Child trie deletion is a heavy operation depending on the amount of storage items  stored in said trie. Therefore this operation is performed lazily in `on_idle`. 
 
 deletionQueueCounter(): `PalletContractsStorageDeletionQueueManager`
- **interface**: `contracts.deletionQueueCounter`
- **summary**:    A pair of monotonic counters used to track the latest contract marked for deletion  and the latest deleted contract in queue. 
 
 migrationInProgress(): `Option<Bytes>`
- **interface**: `contracts.migrationInProgress`
- **summary**:    A migration can span across multiple blocks. This storage defines a cursor to track the  progress of the migration, enabling us to resume from the last completed position. 
 
 nonce(): `u64`
- **interface**: `contracts.nonce`
- **summary**:    This is a **monotonic** counter incremented on contract instantiation. 

   This is used in order to generate unique trie ids for contracts.  The trie id of a new contract is calculated from hash(account_id, nonce).  The nonce is required because otherwise the following sequence would lead to  a possible collision of storage: 

   1. Create a new contract.  2. Terminate the contract.  3. Immediately recreate the contract with the same account_id. 

   This is bad because the contents of a trie are deleted lazily and there might be  storage of the old instantiation still in it when the new contract is created. Please  note that we can't replace the counter by the block number because the sequence above  can happen in the same block. We also can't keep the account counter in memory only  because storage is the only way to communicate across different extrinsics in the  same block. 

   Do not use it to determine the number of contracts. It won't be decremented if  a contract is destroyed. 
 
 pristineCode(`H256`): `Option<Bytes>`
- **interface**: `contracts.pristineCode`
- **summary**:    A mapping from a contract's code hash to its code. 