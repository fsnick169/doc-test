## transactionStorage
 
 blockTransactions(): `Vec<PalletTransactionStorageTransactionInfo>`
- **interface**: `transactionStorage.blockTransactions`
 
 byteFee(): `Option<u128>`
- **interface**: `transactionStorage.byteFee`
- **summary**:    Storage fee per byte. 
 
 chunkCount(`u32`): `u32`
- **interface**: `transactionStorage.chunkCount`
- **summary**:    Count indexed chunks for each block. 
 
 entryFee(): `Option<u128>`
- **interface**: `transactionStorage.entryFee`
- **summary**:    Storage fee per transaction. 
 
 proofChecked(): `bool`
- **interface**: `transactionStorage.proofChecked`
- **summary**:    Was the proof checked in this block? 
 
 storagePeriod(): `u32`
- **interface**: `transactionStorage.storagePeriod`
- **summary**:    Storage period for data in blocks. Should match `sp_storage_proof::DEFAULT_STORAGE_PERIOD`  for block authoring. 
 
 transactions(`u32`): `Option<Vec<PalletTransactionStorageTransactionInfo>>`
- **interface**: `transactionStorage.transactions`
- **summary**:    Collection of transaction metadata by block number. 