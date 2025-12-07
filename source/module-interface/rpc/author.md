## author
 
 hasKey(publicKey: `Bytes`, keyType: `Text`): `bool`
- **interface**: `author.hasKey`
- **jsonrpc**: `author_hasKey`
- **summary**: Returns true if the keystore has private keys for the given public key and key type.
- **unsafe**: This method is only active with appropriate flags
 
 hasSessionKeys(sessionKeys: `Bytes`): `bool`
- **interface**: `author.hasSessionKeys`
- **jsonrpc**: `author_hasSessionKeys`
- **summary**: Returns true if the keystore has private keys for the given session public keys.
- **unsafe**: This method is only active with appropriate flags
 
 insertKey(keyType: `Text`, suri: `Text`, publicKey: `Bytes`): `Bytes`
- **interface**: `author.insertKey`
- **jsonrpc**: `author_insertKey`
- **summary**: Insert a key into the keystore.
- **unsafe**: This method is only active with appropriate flags
 
 pendingExtrinsics(): `Vec<Extrinsic>`
- **interface**: `author.pendingExtrinsics`
- **jsonrpc**: `author_pendingExtrinsics`
- **summary**: Returns all pending extrinsics, potentially grouped by sender
 
 removeExtrinsic(bytesOrHash: `Vec<ExtrinsicOrHash>`): `Vec<Hash>`
- **interface**: `author.removeExtrinsic`
- **jsonrpc**: `author_removeExtrinsic`
- **summary**: Remove given extrinsic from the pool and temporarily ban it to prevent reimporting
- **unsafe**: This method is only active with appropriate flags
 
 rotateKeys(): `Bytes`
- **interface**: `author.rotateKeys`
- **jsonrpc**: `author_rotateKeys`
- **summary**: Generate new session keys and returns the corresponding public keys
- **unsafe**: This method is only active with appropriate flags
 
 submitAndWatchExtrinsic(extrinsic: `Extrinsic`): `ExtrinsicStatus`
- **interface**: `author.submitAndWatchExtrinsic`
- **jsonrpc**: `author_submitAndWatchExtrinsic`
- **summary**: Submit and subscribe to watch an extrinsic until unsubscribed
 
 submitExtrinsic(extrinsic: `Extrinsic`): `Hash`
- **interface**: `author.submitExtrinsic`
- **jsonrpc**: `author_submitExtrinsic`
- **summary**: Submit a fully formatted extrinsic for block inclusion