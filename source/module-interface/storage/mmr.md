## mmr
 
 nodes(`u64`): `Option<H256>`
- **interface**: `mmr.nodes`
- **summary**:    Hashes of the nodes in the MMR. 

   Note this collection only contains MMR peaks, the inner nodes (and leaves)  are pruned and only stored in the Offchain DB. 
 
 numberOfLeaves(): `u64`
- **interface**: `mmr.numberOfLeaves`
- **summary**:    Current size of the MMR (number of leaves). 
 
 rootHash(): `H256`
- **interface**: `mmr.rootHash`
- **summary**:    Latest MMR Root hash. 