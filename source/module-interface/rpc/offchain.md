## offchain
 
 localStorageClear(kind: `StorageKind`, key: `Bytes`): `Null`
- **interface**: `offchain.localStorageClear`
- **jsonrpc**: `offchain_localStorageClear`
- **summary**: Clear offchain local storage under given key and prefix
- **unsafe**: This method is only active with appropriate flags
 
 localStorageGet(kind: `StorageKind`, key: `Bytes`): `Option<Bytes>`
- **interface**: `offchain.localStorageGet`
- **jsonrpc**: `offchain_localStorageGet`
- **summary**: Get offchain local storage under given key and prefix
- **unsafe**: This method is only active with appropriate flags
 
 localStorageSet(kind: `StorageKind`, key: `Bytes`, value: `Bytes`): `Null`
- **interface**: `offchain.localStorageSet`
- **jsonrpc**: `offchain_localStorageSet`
- **summary**: Set offchain local storage under given key and prefix
- **unsafe**: This method is only active with appropriate flags