## contracts
 
 call(callRequest: `ContractCallRequest`, at?: `BlockHash`): `ContractExecResult`
- **interface**: `contracts.call`
- **jsonrpc**: `contracts_call`
- **summary**: Executes a call to a contract
- **deprecated**: Use the runtime interface `api.call.contractsApi.call` instead
 
 getStorage(address: `AccountId`, key: `H256`, at?: `BlockHash`): `Option<Bytes>`
- **interface**: `contracts.getStorage`
- **jsonrpc**: `contracts_getStorage`
- **summary**: Returns the value under a specified storage key in a contract
- **deprecated**: Use the runtime interface `api.call.contractsApi.getStorage` instead
 
 instantiate(request: `InstantiateRequestV1`, at?: `BlockHash`): `ContractInstantiateResult`
- **interface**: `contracts.instantiate`
- **jsonrpc**: `contracts_instantiate`
- **summary**: Instantiate a new contract
- **deprecated**: Use the runtime interface `api.call.contractsApi.instantiate` instead
 
 rentProjection(address: `AccountId`, at?: `BlockHash`): `Option<BlockNumber>`
- **interface**: `contracts.rentProjection`
- **jsonrpc**: `contracts_rentProjection`
- **summary**: Returns the projected time a given contract will be able to sustain paying its rent
- **deprecated**: Not available in newer versions of the contracts interfaces
 
 uploadCode(uploadRequest: `CodeUploadRequest`, at?: `BlockHash`): `CodeUploadResult`
- **interface**: `contracts.uploadCode`
- **jsonrpc**: `contracts_upload_code`
- **summary**: Upload new code without instantiating a contract from it
- **deprecated**: Use the runtime interface `api.call.contractsApi.uploadCode` instead