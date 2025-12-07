## system
 
 account(`AccountId32`): `FrameSystemAccountInfo`
- **interface**: `system.account`
- **summary**:    The full account information for a particular account ID. 
 
 allExtrinsicsLen(): `Option<u32>`
- **interface**: `system.allExtrinsicsLen`
- **summary**:    Total length (in bytes) for all extrinsics put together, for the current block. 
 
 authorizedUpgrade(): `Option<FrameSystemCodeUpgradeAuthorization>`
- **interface**: `system.authorizedUpgrade`
- **summary**:    `Some` if a code upgrade has been authorized. 
 
 blockHash(`u32`): `H256`
- **interface**: `system.blockHash`
- **summary**:    Map of block numbers to block hashes. 
 
 blockWeight(): `FrameSupportDispatchPerDispatchClassWeight`
- **interface**: `system.blockWeight`
- **summary**:    The current weight for the block. 
 
 digest(): `SpRuntimeDigest`
- **interface**: `system.digest`
- **summary**:    Digest of the current block, also part of the block header. 
 
 eventCount(): `u32`
- **interface**: `system.eventCount`
- **summary**:    The number of events in the `Events<T>` list. 
 
 events(): `Vec<FrameSystemEventRecord>`
- **interface**: `system.events`
- **summary**:    Events deposited for the current block. 

   NOTE: The item is unbound and should therefore never be read on chain.  It could otherwise inflate the PoV size of a block. 

   Events have a large in-memory size. Box the events to not go out-of-memory  just in case someone still reads them from within the runtime. 
 
 eventTopics(`H256`): `Vec<(u32,u32)>`
- **interface**: `system.eventTopics`
- **summary**:    Mapping between a topic (represented by T::Hash) and a vector of indexes  of events in the `<Events<T>>` list. 

   All topic vectors have deterministic storage locations depending on the topic. This  allows light-clients to leverage the changes trie storage tracking mechanism and  in case of changes fetch the list of events of interest. 

   The value has the type `(BlockNumberFor<T>, EventIndex)` because if we used only just  the `EventIndex` then in case if the topic has the same contents on the next block  no notification will be triggered thus the event might be lost. 
 
 executionPhase(): `Option<FrameSystemPhase>`
- **interface**: `system.executionPhase`
- **summary**:    The execution phase of the block. 
 
 extrinsicCount(): `Option<u32>`
- **interface**: `system.extrinsicCount`
- **summary**:    Total extrinsics count for the current block. 
 
 extrinsicData(`u32`): `Bytes`
- **interface**: `system.extrinsicData`
- **summary**:    Extrinsics data for the current block (maps an extrinsic's index to its data). 
 
 extrinsicWeightReclaimed(): `SpWeightsWeightV2Weight`
- **interface**: `system.extrinsicWeightReclaimed`
- **summary**:    The weight reclaimed for the extrinsic. 

   This information is available until the end of the extrinsic execution.  More precisely this information is removed in `note_applied_extrinsic`. 

   Logic doing some post dispatch weight reduction must update this storage to avoid duplicate  reduction. 
 
 inherentsApplied(): `bool`
- **interface**: `system.inherentsApplied`
- **summary**:    Whether all inherents have been applied. 
 
 lastRuntimeUpgrade(): `Option<FrameSystemLastRuntimeUpgradeInfo>`
- **interface**: `system.lastRuntimeUpgrade`
- **summary**:    Stores the `spec_version` and `spec_name` of when the last runtime upgrade happened. 
 
 number(): `u32`
- **interface**: `system.number`
- **summary**:    The current block number being processed. Set by `execute_block`. 
 
 parentHash(): `H256`
- **interface**: `system.parentHash`
- **summary**:    Hash of the previous block. 
 
 upgradedToTripleRefCount(): `bool`
- **interface**: `system.upgradedToTripleRefCount`
- **summary**:    True if we have upgraded so that AccountInfo contains three types of `RefCount`. False  (default) if not. 
 
 upgradedToU32RefCount(): `bool`
- **interface**: `system.upgradedToU32RefCount`
- **summary**:    True if we have upgraded so that `type RefCount` is `u32`. False (default) if not. 