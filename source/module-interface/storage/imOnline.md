## imOnline
 
 authoredBlocks(`u32, AccountId32`): `u32`
- **interface**: `imOnline.authoredBlocks`
- **summary**:    For each session index, we keep a mapping of `ValidatorId<T>` to the  number of blocks authored by the given authority. 
 
 heartbeatAfter(): `u32`
- **interface**: `imOnline.heartbeatAfter`
- **summary**:    The block number after which it's ok to send heartbeats in the current  session. 

   At the beginning of each session we set this to a value that should fall  roughly in the middle of the session duration. The idea is to first wait for  the validators to produce a block in the current session, so that the  heartbeat later on will not be necessary. 

   This value will only be used as a fallback if we fail to get a proper session  progress estimate from `NextSessionRotation`, as those estimates should be  more accurate then the value we calculate for `HeartbeatAfter`. 
 
 keys(): `Vec<PalletImOnlineSr25519AppSr25519Public>`
- **interface**: `imOnline.keys`
- **summary**:    The current set of keys that may issue a heartbeat. 
 
 receivedHeartbeats(`u32, u32`): `Option<bool>`
- **interface**: `imOnline.receivedHeartbeats`
- **summary**:    For each session index, we keep a mapping of `SessionIndex` and `AuthIndex`. 