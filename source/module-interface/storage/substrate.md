## substrate
 
 changesTrieConfig(): `u32`
- **interface**: `substrate.changesTrieConfig`
- **summary**:    Changes trie configuration is stored under this key. 
 
 childStorageKeyPrefix(): `u32`
- **interface**: `substrate.childStorageKeyPrefix`
- **summary**:    Prefix of child storage keys. 
 
 code(): `Bytes`
- **interface**: `substrate.code`
- **summary**:    Wasm code of the runtime. 
 
 defaultChildStorageKeyPrefix(): `u32`
- **interface**: `substrate.defaultChildStorageKeyPrefix`
- **summary**:    Prefix of the default child storage keys in the top trie. 
 
 extrinsicIndex(): `u32`
- **interface**: `substrate.extrinsicIndex`
- **summary**:    Current extrinsic index (u32) is stored under this key. 
 
 heapPages(): `u64`
- **interface**: `substrate.heapPages`
- **summary**:    Number of wasm linear memory pages required for execution of the runtime. 
 
 intrablockEntropy(): `[u8;32]`
- **interface**: `substrate.intrablockEntropy`
- **summary**:    Current intra-block entropy (a universally unique `[u8; 32]` value) is stored here. 
 
 storageVersionStorageKeyPostfix(): `u16`
- **interface**: `substrate.storageVersionStorageKeyPostfix`
- **summary**:    The storage key postfix that is used to store the [`StorageVersion`] per pallet. 
 
 transactionLevelKey(): `u32`
- **interface**: `substrate.transactionLevelKey`
- **summary**:    The key that holds the current number of active layers. 