## mmr
 
 generateProof(blockNumbers: `Vec<u64>`, bestKnownBlockNumber?: `u64`, at?: `BlockHash`): `MmrLeafBatchProof`
- **interface**: `mmr.generateProof`
- **jsonrpc**: `mmr_generateProof`
- **summary**: Generate MMR proof for the given block numbers.
 
 root(at?: `BlockHash`): `MmrHash`
- **interface**: `mmr.root`
- **jsonrpc**: `mmr_root`
- **summary**: Get the MMR root hash for the current best block.
 
 verifyProof(proof: `MmrLeafBatchProof`): `bool`
- **interface**: `mmr.verifyProof`
- **jsonrpc**: `mmr_verifyProof`
- **summary**: Verify an MMR proof
 
 verifyProofStateless(root: `MmrHash`, proof: `MmrLeafBatchProof`): `bool`
- **interface**: `mmr.verifyProofStateless`
- **jsonrpc**: `mmr_verifyProofStateless`
- **summary**: Verify an MMR proof statelessly given an mmr_root