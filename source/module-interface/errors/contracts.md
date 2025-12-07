## contracts
 
 CannotAddSelfAsDelegateDependency
- **interface**: `contracts.CannotAddSelfAsDelegateDependency.is`
- **summary**:    Can not add a delegate dependency to the code hash of the contract itself. 
 
 CodeInfoNotFound
- **interface**: `contracts.CodeInfoNotFound.is`
- **summary**:    No code info could be found at the supplied code hash. 
 
 CodeInUse
- **interface**: `contracts.CodeInUse.is`
- **summary**:    Code removal was denied because the code is still in use by at least one contract. 
 
 CodeNotFound
- **interface**: `contracts.CodeNotFound.is`
- **summary**:    No code could be found at the supplied code hash. 
 
 CodeRejected
- **interface**: `contracts.CodeRejected.is`
- **summary**:    The contract's code was found to be invalid during validation. 

   The most likely cause of this is that an API was used which is not supported by the  node. This happens if an older node is used with a new version of ink!. Try updating  your node to the newest available version. 

   A more detailed error can be found on the node console if debug messages are enabled  by supplying `-lruntime::contracts=debug`. 
 
 CodeTooLarge
- **interface**: `contracts.CodeTooLarge.is`
- **summary**:    The code supplied to `instantiate_with_code` exceeds the limit specified in the  current schedule. 
 
 ContractNotFound
- **interface**: `contracts.ContractNotFound.is`
- **summary**:    No contract was found at the specified address. 
 
 ContractReverted
- **interface**: `contracts.ContractReverted.is`
- **summary**:    The contract ran to completion but decided to revert its storage changes.  Please note that this error is only returned from extrinsics. When called directly  or via RPC an `Ok` will be returned. In this case the caller needs to inspect the flags  to determine whether a reversion has taken place. 
 
 ContractTrapped
- **interface**: `contracts.ContractTrapped.is`
- **summary**:    Contract trapped during execution. 
 
 DecodingFailed
- **interface**: `contracts.DecodingFailed.is`
- **summary**:    Input passed to a contract API function failed to decode as expected type. 
 
 DelegateDependencyAlreadyExists
- **interface**: `contracts.DelegateDependencyAlreadyExists.is`
- **summary**:    The contract already depends on the given delegate dependency. 
 
 DelegateDependencyNotFound
- **interface**: `contracts.DelegateDependencyNotFound.is`
- **summary**:    The dependency was not found in the contract's delegate dependencies. 
 
 DuplicateContract
- **interface**: `contracts.DuplicateContract.is`
- **summary**:    A contract with the same AccountId already exists. 
 
 Indeterministic
- **interface**: `contracts.Indeterministic.is`
- **summary**:    An indeterministic code was used in a context where this is not permitted. 
 
 InputForwarded
- **interface**: `contracts.InputForwarded.is`
- **summary**:    `seal_call` forwarded this contracts input. It therefore is no longer available. 
 
 InvalidCallFlags
- **interface**: `contracts.InvalidCallFlags.is`
- **summary**:    Invalid combination of flags supplied to `seal_call` or `seal_delegate_call`. 
 
 InvalidSchedule
- **interface**: `contracts.InvalidSchedule.is`
- **summary**:    Invalid schedule supplied, e.g. with zero weight of a basic operation. 
 
 MaxCallDepthReached
- **interface**: `contracts.MaxCallDepthReached.is`
- **summary**:    Performing a call was denied because the calling depth reached the limit  of what is specified in the schedule. 
 
 MaxDelegateDependenciesReached
- **interface**: `contracts.MaxDelegateDependenciesReached.is`
- **summary**:    The contract has reached its maximum number of delegate dependencies. 
 
 MigrationInProgress
- **interface**: `contracts.MigrationInProgress.is`
- **summary**:    A pending migration needs to complete before the extrinsic can be called. 
 
 NoChainExtension
- **interface**: `contracts.NoChainExtension.is`
- **summary**:    The chain does not provide a chain extension. Calling the chain extension results  in this error. Note that this usually  shouldn't happen as deploying such contracts  is rejected. 
 
 NoMigrationPerformed
- **interface**: `contracts.NoMigrationPerformed.is`
- **summary**:    Migrate dispatch call was attempted but no migration was performed. 
 
 OutOfBounds
- **interface**: `contracts.OutOfBounds.is`
- **summary**:    A buffer outside of sandbox memory was passed to a contract API function. 
 
 OutOfGas
- **interface**: `contracts.OutOfGas.is`
- **summary**:    The executed contract exhausted its gas limit. 
 
 OutOfTransientStorage
- **interface**: `contracts.OutOfTransientStorage.is`
- **summary**:    Can not add more data to transient storage. 
 
 OutputBufferTooSmall
- **interface**: `contracts.OutputBufferTooSmall.is`
- **summary**:    The output buffer supplied to a contract API call was too small. 
 
 RandomSubjectTooLong
- **interface**: `contracts.RandomSubjectTooLong.is`
- **summary**:    The subject passed to `seal_random` exceeds the limit. 
 
 ReentranceDenied
- **interface**: `contracts.ReentranceDenied.is`
- **summary**:    A call tried to invoke a contract that is flagged as non-reentrant.  The only other cause is that a call from a contract into the runtime tried to call back  into `pallet-contracts`. This would make the whole pallet reentrant with regard to  contract code execution which is not supported. 
 
 StateChangeDenied
- **interface**: `contracts.StateChangeDenied.is`
- **summary**:    A contract attempted to invoke a state modifying API while being in read-only mode. 
 
 StorageDepositLimitExhausted
- **interface**: `contracts.StorageDepositLimitExhausted.is`
- **summary**:    More storage was created than allowed by the storage deposit limit. 
 
 StorageDepositNotEnoughFunds
- **interface**: `contracts.StorageDepositNotEnoughFunds.is`
- **summary**:    Origin doesn't have enough balance to pay the required storage deposits. 
 
 TerminatedInConstructor
- **interface**: `contracts.TerminatedInConstructor.is`
- **summary**:    A contract self destructed in its constructor. 
 
 TerminatedWhileReentrant
- **interface**: `contracts.TerminatedWhileReentrant.is`
- **summary**:    Termination of a contract is not allowed while the contract is already  on the call stack. Can be triggered by `seal_terminate`. 
 
 TooManyTopics
- **interface**: `contracts.TooManyTopics.is`
- **summary**:    The amount of topics passed to `seal_deposit_events` exceeds the limit. 
 
 TransferFailed
- **interface**: `contracts.TransferFailed.is`
- **summary**:    Performing the requested transfer failed. Probably because there isn't enough  free balance in the sender's account. 
 
 ValueTooLarge
- **interface**: `contracts.ValueTooLarge.is`
- **summary**:    The size defined in `T::MaxValueSize` was exceeded. 