## state
 
 call(method: `Text`, data: `Bytes`, at?: `BlockHash`): `Bytes`
- **interface**: `state.call`
- **jsonrpc**: `state_call`
- **summary**: Perform a call to a builtin on the chain
 
 getChildKeys(childStorageKey: `StorageKey`, childDefinition: `StorageKey`, childType: `u32`, key: `StorageKey`, at?: `BlockHash`): `Vec<StorageKey>`
- **interface**: `state.getChildKeys`
- **jsonrpc**: `state_getChildKeys`
- **summary**: Retrieves the keys with prefix of a specific child storage
 
 getChildReadProof(childStorageKey: `PrefixedStorageKey`, keys: `Vec<StorageKey>`, at?: `BlockHash`): `ReadProof`
- **interface**: `state.getChildReadProof`
- **jsonrpc**: `state_getChildReadProof`
- **summary**: Returns proof of storage for child key entries at a specific block state.
 
 getChildStorage(childStorageKey: `StorageKey`, childDefinition: `StorageKey`, childType: `u32`, key: `StorageKey`, at?: `BlockHash`): `StorageData`
- **interface**: `state.getChildStorage`
- **jsonrpc**: `state_getChildStorage`
- **summary**: Retrieves the child storage for a key
 
 getChildStorageHash(childStorageKey: `StorageKey`, childDefinition: `StorageKey`, childType: `u32`, key: `StorageKey`, at?: `BlockHash`): `Hash`
- **interface**: `state.getChildStorageHash`
- **jsonrpc**: `state_getChildStorageHash`
- **summary**: Retrieves the child storage hash
 
 getChildStorageSize(childStorageKey: `StorageKey`, childDefinition: `StorageKey`, childType: `u32`, key: `StorageKey`, at?: `BlockHash`): `u64`
- **interface**: `state.getChildStorageSize`
- **jsonrpc**: `state_getChildStorageSize`
- **summary**: Retrieves the child storage size
 
 getKeys(key: `StorageKey`, at?: `BlockHash`): `Vec<StorageKey>`
- **interface**: `state.getKeys`
- **jsonrpc**: `state_getKeys`
- **summary**: Retrieves the keys with a certain prefix
- **deprecated**: Use `state.getKeysPaged` to retrieve keys
 
 getKeysPaged(key: `StorageKey`, count: `u32`, startKey?: `StorageKey`, at?: `BlockHash`): `Vec<StorageKey>`
- **interface**: `state.getKeysPaged`
- **jsonrpc**: `state_getKeysPaged`
- **summary**: Returns the keys with prefix with pagination support.
 
 getMetadata(at?: `BlockHash`): `Metadata`
- **interface**: `state.getMetadata`
- **jsonrpc**: `state_getMetadata`
- **summary**: Returns the runtime metadata
 
 getPairs(prefix: `StorageKey`, at?: `BlockHash`): `Vec<KeyValue>`
- **interface**: `state.getPairs`
- **jsonrpc**: `state_getPairs`
- **summary**: Returns the keys with prefix, leave empty to get all the keys (deprecated: Use getKeysPaged)
- **deprecated**: Use `state.getKeysPaged` to retrieve keys
- **unsafe**: This method is only active with appropriate flags
 
 getReadProof(keys: `Vec<StorageKey>`, at?: `BlockHash`): `ReadProof`
- **interface**: `state.getReadProof`
- **jsonrpc**: `state_getReadProof`
- **summary**: Returns proof of storage entries at a specific block state
 
 getRuntimeVersion(at?: `BlockHash`): `RuntimeVersion`
- **interface**: `state.getRuntimeVersion`
- **jsonrpc**: `state_getRuntimeVersion`
- **summary**: Get the runtime version
 
 getStorage(key: `StorageKey`, at?: `BlockHash`): `StorageData`
- **interface**: `state.getStorage`
- **jsonrpc**: `state_getStorage`
- **summary**: Retrieves the storage for a key
 
 getStorageHash(key: `StorageKey`, at?: `BlockHash`): `Hash`
- **interface**: `state.getStorageHash`
- **jsonrpc**: `state_getStorageHash`
- **summary**: Retrieves the storage hash
 
 getStorageSize(key: `StorageKey`, at?: `BlockHash`): `u64`
- **interface**: `state.getStorageSize`
- **jsonrpc**: `state_getStorageSize`
- **summary**: Retrieves the storage size
 
 queryStorage(keys: `Vec<StorageKey>`, fromBlock: `Hash`, toBlock?: `BlockHash`): `Vec<StorageChangeSet>`
- **interface**: `state.queryStorage`
- **jsonrpc**: `state_queryStorage`
- **summary**: Query historical storage entries (by key) starting from a start block
- **unsafe**: This method is only active with appropriate flags
 
 queryStorageAt(keys: `Vec<StorageKey>`, at?: `BlockHash`): `Vec<StorageChangeSet>`
- **interface**: `state.queryStorageAt`
- **jsonrpc**: `state_queryStorageAt`
- **summary**: Query storage entries (by key) starting at block hash given as the second parameter
 
 subscribeRuntimeVersion(): `RuntimeVersion`
- **interface**: `state.subscribeRuntimeVersion`
- **jsonrpc**: `state_subscribeRuntimeVersion`
- **summary**: Retrieves the runtime version via subscription
 
 subscribeStorage(keys?: `Vec<StorageKey>`): `StorageChangeSet`
- **interface**: `state.subscribeStorage`
- **jsonrpc**: `state_subscribeStorage`
- **summary**: Subscribes to storage changes for the provided keys
 
 traceBlock(block: `Hash`, targets: `Option<Text>`, storageKeys: `Option<Text>`, methods: `Option<Text>`): `TraceBlockResponse`
- **interface**: `state.traceBlock`
- **jsonrpc**: `state_traceBlock`
- **summary**: Provides a way to trace the re-execution of a single block
- **unsafe**: This method is only active with appropriate flags
 
 trieMigrationStatus(at?: `BlockHash`): `MigrationStatusResult`
- **interface**: `state.trieMigrationStatus`
- **jsonrpc**: `state_trieMigrationStatus`
- **summary**: Check current migration state
- **unsafe**: This method is only active with appropriate flags