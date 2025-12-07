## system
 
 accountNextIndex(accountId: `AccountId`): `Index`
- **interface**: `system.accountNextIndex`
- **jsonrpc**: `system_accountNextIndex`
- **summary**: Retrieves the next accountIndex as available on the node
 
 addLogFilter(directives: `Text`): `Null`
- **interface**: `system.addLogFilter`
- **jsonrpc**: `system_addLogFilter`
- **summary**: Adds the supplied directives to the current log filter
- **unsafe**: This method is only active with appropriate flags
 
 addReservedPeer(peer: `Text`): `Text`
- **interface**: `system.addReservedPeer`
- **jsonrpc**: `system_addReservedPeer`
- **summary**: Adds a reserved peer
- **unsafe**: This method is only active with appropriate flags
 
 chain(): `Text`
- **interface**: `system.chain`
- **jsonrpc**: `system_chain`
- **summary**: Retrieves the chain
 
 chainType(): `ChainType`
- **interface**: `system.chainType`
- **jsonrpc**: `system_chainType`
- **summary**: Retrieves the chain type
 
 dryRun(extrinsic: `Bytes`, at?: `BlockHash`): `ApplyExtrinsicResult`
- **interface**: `system.dryRun`
- **jsonrpc**: `system_dryRun`
- **summary**: Dry run an extrinsic at a given block
- **unsafe**: This method is only active with appropriate flags
 
 health(): `Health`
- **interface**: `system.health`
- **jsonrpc**: `system_health`
- **summary**: Return health status of the node
 
 localListenAddresses(): `Vec<Text>`
- **interface**: `system.localListenAddresses`
- **jsonrpc**: `system_localListenAddresses`
- **summary**: The addresses include a trailing /p2p/ with the local PeerId, and are thus suitable to be passed to addReservedPeer or as a bootnode address for example
 
 localPeerId(): `Text`
- **interface**: `system.localPeerId`
- **jsonrpc**: `system_localPeerId`
- **summary**: Returns the base58-encoded PeerId of the node
 
 name(): `Text`
- **interface**: `system.name`
- **jsonrpc**: `system_name`
- **summary**: Retrieves the node name
 
 networkState(): `NetworkState`
- **interface**: `system.networkState`
- **jsonrpc**: `system_networkState`
- **summary**: Returns current state of the network
- **unsafe**: This method is only active with appropriate flags
 
 nodeRoles(): `Vec<NodeRole>`
- **interface**: `system.nodeRoles`
- **jsonrpc**: `system_nodeRoles`
- **summary**: Returns the roles the node is running as
 
 peers(): `Vec<PeerInfo>`
- **interface**: `system.peers`
- **jsonrpc**: `system_peers`
- **summary**: Returns the currently connected peers
- **unsafe**: This method is only active with appropriate flags
 
 properties(): `ChainProperties`
- **interface**: `system.properties`
- **jsonrpc**: `system_properties`
- **summary**: Get a custom set of properties as a JSON object, defined in the chain spec
 
 removeReservedPeer(peerId: `Text`): `Text`
- **interface**: `system.removeReservedPeer`
- **jsonrpc**: `system_removeReservedPeer`
- **summary**: Remove a reserved peer
- **unsafe**: This method is only active with appropriate flags
 
 reservedPeers(): `Vec<Text>`
- **interface**: `system.reservedPeers`
- **jsonrpc**: `system_reservedPeers`
- **summary**: Returns the list of reserved peers
 
 resetLogFilter(): `Null`
- **interface**: `system.resetLogFilter`
- **jsonrpc**: `system_resetLogFilter`
- **summary**: Resets the log filter to Substrate defaults
- **unsafe**: This method is only active with appropriate flags
 
 syncState(): `SyncState`
- **interface**: `system.syncState`
- **jsonrpc**: `system_syncState`
- **summary**: Returns the state of the syncing of the node
 
 version(): `Text`
- **interface**: `system.version`
- **jsonrpc**: `system_version`
- **summary**: Retrieves the version of the node
