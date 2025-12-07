## grandpa
 
 proveFinality(blockNumber: `BlockNumber`): `Option<EncodedFinalityProofs>`
- **interface**: `grandpa.proveFinality`
- **jsonrpc**: `grandpa_proveFinality`
- **summary**: Prove finality for the given block number, returning the Justification for the last block in the set.
 
 roundState(): `ReportedRoundStates`
- **interface**: `grandpa.roundState`
- **jsonrpc**: `grandpa_roundState`
- **summary**: Returns the state of the current best round state as well as the ongoing background rounds
 
 subscribeJustifications(): `JustificationNotification`
- **interface**: `grandpa.subscribeJustifications`
- **jsonrpc**: `grandpa_subscribeJustifications`
- **summary**: Subscribes to grandpa justifications