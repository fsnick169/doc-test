## contracts
 
 call(dest: `MultiAddress`, value: `Compact<u128>`, gas_limit: `SpWeightsWeightV2Weight`, storage_deposit_limit: `Option<Compact<u128>>`, data: `Bytes`)
- **interface**: `contracts.call`
- **summary**:    Makes a call to an account, optionally transferring some balance. 
- **Parameters**: 

   * `dest`: Address of the contract to call. 

  * `value`: The balance to transfer from the `origin` to `dest`.

  * `gas_limit`: The gas limit enforced when executing the constructor.

  * `storage_deposit_limit`: The maximum amount of balance that can be charged from the caller to pay for the storage consumed. 

  * `data`: The input data to pass to the contract.

   * If the account is a smart-contract account, the associated code will be  executed and any value will be transferred. 

  * If the account is a regular account, any value will be transferred.

  * If no account exists and the call value is not less than `existential_deposit`, a regular account will be created and any value will be transferred. 
 
 callOldWeight(dest: `MultiAddress`, value: `Compact<u128>`, gas_limit: `Compact<u64>`, storage_deposit_limit: `Option<Compact<u128>>`, data: `Bytes`)
- **interface**: `contracts.callOldWeight`
- **summary**:    Deprecated version if [`Self::call`] for use in an in-storage `Call`. 
 
 instantiate(value: `Compact<u128>`, gas_limit: `SpWeightsWeightV2Weight`, storage_deposit_limit: `Option<Compact<u128>>`, code_hash: `H256`, data: `Bytes`, salt: `Bytes`)
- **interface**: `contracts.instantiate`
- **summary**:    Instantiates a contract from a previously deployed wasm binary. 

   This function is identical to [`Self::instantiate_with_code`] but without the  code deployment step. Instead, the `code_hash` of an on-chain deployed wasm binary  must be supplied. 
 
 instantiateOldWeight(value: `Compact<u128>`, gas_limit: `Compact<u64>`, storage_deposit_limit: `Option<Compact<u128>>`, code_hash: `H256`, data: `Bytes`, salt: `Bytes`)
- **interface**: `contracts.instantiateOldWeight`
- **summary**:    Deprecated version if [`Self::instantiate`] for use in an in-storage `Call`. 
 
 instantiateWithCode(value: `Compact<u128>`, gas_limit: `SpWeightsWeightV2Weight`, storage_deposit_limit: `Option<Compact<u128>>`, code: `Bytes`, data: `Bytes`, salt: `Bytes`)
- **interface**: `contracts.instantiateWithCode`
- **summary**:    Instantiates a new contract from the supplied `code` optionally transferring  some balance. 

   This dispatchable has the same effect as calling [`Self::upload_code`] +  [`Self::instantiate`]. Bundling them together provides efficiency gains. Please  also check the documentation of [`Self::upload_code`]. 

- **Parameters**: 

   * `value`: The balance to transfer from the `origin` to the newly created contract. 

  * `gas_limit`: The gas limit enforced when executing the constructor.

  * `storage_deposit_limit`: The maximum amount of balance that can be charged/reserved from the caller to pay for the storage consumed. 

  * `code`: The contract code to deploy in raw bytes.

  * `data`: The input data to pass to the contract constructor.

  * `salt`: Used for the address derivation. See [`Pallet::contract_address`].

   Instantiation is executed as follows: 

   - The supplied `code` is deployed, and a `code_hash` is created for that code. 

  - If the `code_hash` already exists on the chain the underlying `code` will be shared.

  - The destination address is computed based on the sender, code_hash and the salt.

  - The smart-contract account is created at the computed address.

  - The `value` is transferred to the new account.

  - The `deploy` function is executed in the context of the newly-created account.
 
 instantiateWithCodeOldWeight(value: `Compact<u128>`, gas_limit: `Compact<u64>`, storage_deposit_limit: `Option<Compact<u128>>`, code: `Bytes`, data: `Bytes`, salt: `Bytes`)
- **interface**: `contracts.instantiateWithCodeOldWeight`
- **summary**:    Deprecated version if [`Self::instantiate_with_code`] for use in an in-storage `Call`. 
 
 migrate(weight_limit: `SpWeightsWeightV2Weight`)
- **interface**: `contracts.migrate`
- **summary**:    When a migration is in progress, this dispatchable can be used to run migration steps.  Calls that contribute to advancing the migration have their fees waived, as it's helpful  for the chain. Note that while the migration is in progress, the pallet will also  leverage the `on_idle` hooks to run migration steps. 
 
 removeCode(code_hash: `H256`)
- **interface**: `contracts.removeCode`
- **summary**:    Remove the code stored under `code_hash` and refund the deposit to its owner. 

   A code can only be removed by its original uploader (its owner) and only if it is  not used by any contract. 
 
 setCode(dest: `MultiAddress`, code_hash: `H256`)
- **interface**: `contracts.setCode`
- **summary**:    Privileged function that changes the code of an existing contract. 

   This takes care of updating refcounts and all other necessary operations. Returns  an error if either the `code_hash` or `dest` do not exist. 

   This does **not** change the address of the contract in question. This means  that the contract address is no longer derived from its code hash after calling  this dispatchable. 
 
 uploadCode(code: `Bytes`, storage_deposit_limit: `Option<Compact<u128>>`, determinism: `PalletContractsWasmDeterminism`)
- **interface**: `contracts.uploadCode`
- **summary**:    Upload new `code` without instantiating a contract from it. 

   If the code does not already exist a deposit is reserved from the caller  and unreserved only when [`Self::remove_code`] is called. The size of the reserve  depends on the size of the supplied `code`. 

   If the code already exists in storage it will still return `Ok` and upgrades  the in storage version to the current  [`InstructionWeights::version`]. 

   - `determinism`: If this is set to any other value but [`Determinism::Enforced`] then  the only way to use this code is to delegate call into it from an offchain execution.  Set to [`Determinism::Enforced`] if in doubt. 

   Anyone can instantiate a contract from any uploaded code and thus prevent its removal.  To avoid this situation a constructor could employ access control so that it can  only be instantiated by permissioned entities. The same is true when uploading  through [`Self::instantiate_with_code`]. 

   Use [`Determinism::Relaxed`] exclusively for non-deterministic code. If the uploaded  code is deterministic, specifying [`Determinism::Relaxed`] will be disregarded and  result in higher gas costs. 