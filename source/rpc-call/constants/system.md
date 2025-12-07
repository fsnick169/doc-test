## system
 
 blockHashCount: `u32`
- **interface**: `system.blockHashCount`
- **summary**:    Maximum number of block number to block hash mappings to keep (oldest pruned first). 
 
 blockLength: `FrameSystemLimitsBlockLength`
- **interface**: `system.blockLength`
- **summary**:    The maximum length of a block (in bytes). 
 
 blockWeights: `FrameSystemLimitsBlockWeights`
- **interface**: `system.blockWeights`
- **summary**:    Block & extrinsics weights: base values and limits. 
 
 dbWeight: `SpWeightsRuntimeDbWeight`
- **interface**: `system.dbWeight`
- **summary**:    The weight of runtime database operations the runtime can invoke. 
 
 ss58Prefix: `u16`
- **interface**: `system.ss58Prefix`
- **summary**:    The designated SS58 prefix of this chain. 

   This replaces the "ss58Format" property declared in the chain spec. Reason is  that the runtime should know about the prefix in order to make use of it as  an identifier of the chain. 
 
 version: `SpVersionRuntimeVersion`
- **interface**: `system.version`
- **summary**:    Get the chain's in-code version. 