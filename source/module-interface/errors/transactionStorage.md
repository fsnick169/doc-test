## transactionStorage
 
 BadContext
- **interface**: `transactionStorage.BadContext.is`
- **summary**:    Attempted to call `store` outside of block execution. 
 
 DoubleCheck
- **interface**: `transactionStorage.DoubleCheck.is`
- **summary**:    Double proof check in the block. 
 
 EmptyTransaction
- **interface**: `transactionStorage.EmptyTransaction.is`
- **summary**:    Attempting to store empty transaction 
 
 InvalidProof
- **interface**: `transactionStorage.InvalidProof.is`
- **summary**:    Proof failed verification. 
 
 MissingProof
- **interface**: `transactionStorage.MissingProof.is`
- **summary**:    Missing storage proof. 
 
 MissingStateData
- **interface**: `transactionStorage.MissingStateData.is`
- **summary**:    Unable to verify proof because state data is missing. 
 
 NotConfigured
- **interface**: `transactionStorage.NotConfigured.is`
- **summary**:    Invalid configuration. 
 
 ProofNotChecked
- **interface**: `transactionStorage.ProofNotChecked.is`
- **summary**:    Storage proof was not checked in the block. 
 
 RenewedNotFound
- **interface**: `transactionStorage.RenewedNotFound.is`
- **summary**:    Renewed extrinsic is not found. 
 
 TooManyTransactions
- **interface**: `transactionStorage.TooManyTransactions.is`
- **summary**:    Too many transactions in the block. 
 
 TransactionTooLarge
- **interface**: `transactionStorage.TransactionTooLarge.is`
- **summary**:    Transaction is too large. 
 
 UnexpectedProof
- **interface**: `transactionStorage.UnexpectedProof.is`
- **summary**:    Proof was not expected in this block. 