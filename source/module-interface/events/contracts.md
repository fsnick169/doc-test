## contracts
 
 Called(`PalletContractsOrigin`, `AccountId32`)
- **interface**: `contracts.Called`
- **summary**:    A contract was called either by a plain account or another contract. 
 
 CodeRemoved(`H256`, `u128`, `AccountId32`)
- **interface**: `contracts.CodeRemoved`
- **summary**:    A code with the specified hash was removed. 
 
 CodeStored(`H256`, `u128`, `AccountId32`)
- **interface**: `contracts.CodeStored`
- **summary**:    Code with the specified hash has been stored. 
 
 ContractCodeUpdated(`AccountId32`, `H256`, `H256`)
- **interface**: `contracts.ContractCodeUpdated`
- **summary**:    A contract's code was updated. 
 
 ContractEmitted(`AccountId32`, `Bytes`)
- **interface**: `contracts.ContractEmitted`
- **summary**:    A custom event emitted by the contract. 
 
 DelegateCalled(`AccountId32`, `H256`)
- **interface**: `contracts.DelegateCalled`
- **summary**:    A contract delegate called a code hash. 
 
 Instantiated(`AccountId32`, `AccountId32`)
- **interface**: `contracts.Instantiated`
- **summary**:    Contract deployed by address at the specified address. 
 
 StorageDepositTransferredAndHeld(`AccountId32`, `AccountId32`, `u128`)
- **interface**: `contracts.StorageDepositTransferredAndHeld`
- **summary**:    Some funds have been transferred and held as storage deposit. 
 
 StorageDepositTransferredAndReleased(`AccountId32`, `AccountId32`, `u128`)
- **interface**: `contracts.StorageDepositTransferredAndReleased`
- **summary**:    Some storage deposit funds have been transferred and released. 
 
 Terminated(`AccountId32`, `AccountId32`)
- **interface**: `contracts.Terminated`
- **summary**:    Contract has been removed. 