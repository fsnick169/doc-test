## childstate
 
 getKeys(childKey: `PrefixedStorageKey`, prefix: `StorageKey`, at?: `Hash`): `Vec<StorageKey>`
- **interface**: `childstate.getKeys`
- **jsonrpc**: `childstate_getKeys`
- **summary**: Returns the keys with prefix from a child storage, leave empty to get all the keys
 
 getKeysPaged(childKey: `PrefixedStorageKey`, prefix: `StorageKey`, count: `u32`, startKey?: `StorageKey`, at?: `Hash`): `Vec<StorageKey>`
- **interface**: `childstate.getKeysPaged`
- **jsonrpc**: `childstate_getKeysPaged`
- **summary**: Returns the keys with prefix from a child storage with pagination support
 
 getStorage(childKey: `PrefixedStorageKey`, key: `StorageKey`, at?: `Hash`): `Option<StorageData>`
- **interface**: `childstate.getStorage`
- **jsonrpc**: `childstate_getStorage`
- **summary**: Returns a child storage entry at a specific block state
 
 getStorageEntries(childKey: `PrefixedStorageKey`, keys: `Vec<StorageKey>`, at?: `Hash`): `Vec<Option<StorageData>>`
- **interface**: `childstate.getStorageEntries`
- **jsonrpc**: `childstate_getStorageEntries`
- **summary**: Returns child storage entries for multiple keys at a specific block state
 
 getStorageHash(childKey: `PrefixedStorageKey`, key: `StorageKey`, at?: `Hash`): `Option<Hash>`
- **interface**: `childstate.getStorageHash`
- **jsonrpc**: `childstate_getStorageHash`
- **summary**: Returns the hash of a child storage entry at a block state
 
 getStorageSize(childKey: `PrefixedStorageKey`, key: `StorageKey`, at?: `Hash`): `Option<u64>`
- **interface**: `childstate.getStorageSize`
- **jsonrpc**: `childstate_getStorageSize`
- **summary**: Returns the size of a child storage entry at a block state