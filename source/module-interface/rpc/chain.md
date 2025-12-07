## chain
 
 getBlock(hash?: `BlockHash`): `SignedBlock`
- **interface**: `chain.getBlock`
- **jsonrpc**: `chain_getBlock`
- **summary**: Get header and body of a relay chain block
 
 getBlockHash(blockNumber?: `BlockNumber`): `BlockHash`
- **interface**: `chain.getBlockHash`
- **jsonrpc**: `chain_getBlockHash`
- **summary**: Get the block hash for a specific block
 
 getFinalizedHead(): `BlockHash`
- **interface**: `chain.getFinalizedHead`
- **jsonrpc**: `chain_getFinalizedHead`
- **summary**: Get hash of the last finalized block in the canon chain
 
 getHeader(hash?: `BlockHash`): `Header`
- **interface**: `chain.getHeader`
- **jsonrpc**: `chain_getHeader`
- **summary**: Retrieves the header for a specific block
 
 subscribeAllHeads(): `Header`
- **interface**: `chain.subscribeAllHeads`
- **jsonrpc**: `chain_subscribeAllHeads`
- **summary**: Retrieves the newest header via subscription
 
 subscribeFinalizedHeads(): `Header`
- **interface**: `chain.subscribeFinalizedHeads`
- **jsonrpc**: `chain_subscribeFinalizedHeads`
- **summary**: Retrieves the best finalized header via subscription
 
 subscribeNewHeads(): `Header`
- **interface**: `chain.subscribeNewHeads`
- **jsonrpc**: `chain_subscribeNewHeads`
- **summary**: Retrieves the best header via subscription