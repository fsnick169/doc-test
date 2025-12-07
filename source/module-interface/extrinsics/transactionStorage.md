## transactionStorage
 
 checkProof(proof: `SpTransactionStorageProofTransactionStorageProof`)
- **interface**: `transactionStorage.checkProof`
- **summary**:    Check storage proof for block number `block_number() - StoragePeriod`.  If such block does not exist the proof is expected to be `None`.  # Complexity 

  - Linear w.r.t the number of indexed transactions in the proved block for random probing.  There's a DB read for each transaction. 
 
 renew(block: `u32`, index: `u32`)
- **interface**: `transactionStorage.renew`
- **summary**:    Renew previously stored data. Parameters are the block number that contains  previous `store` or `renew` call and transaction index within that block.  Transaction index is emitted in the `Stored` or `Renewed` event.  Applies same fees as `store`.  # Complexity 

  - O(1).
 
 store(data: `Bytes`)
- **interface**: `transactionStorage.store`
- **summary**:    Index and store data off chain. Minimum data size is 1 bytes, maximum is  `MaxTransactionSize`. Data will be removed after `STORAGE_PERIOD` blocks, unless `renew`  is called.  # Complexity 

  - O(n*log(n)) of data size, as all data is pushed to an in-memory trie.