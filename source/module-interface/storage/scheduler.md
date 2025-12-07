## scheduler
 
 agenda(`u32`): `Vec<Option<PalletSchedulerScheduled>>`
- **interface**: `scheduler.agenda`
- **summary**:    Items to be executed, indexed by the block number that they should be executed on. 
 
 incompleteSince(): `Option<u32>`
- **interface**: `scheduler.incompleteSince`
- **summary**:    Block number at which the agenda began incomplete execution. 
 
 lookup(`[u8;32]`): `Option<(u32,u32)>`
- **interface**: `scheduler.lookup`
- **summary**:    Lookup from a name to the block number and index of the task. 

   For v3 -> v4 the previously unbounded identities are Blake2-256 hashed to form the v4  identities. 
 
 retries(`(u32,u32)`): `Option<PalletSchedulerRetryConfig>`
- **interface**: `scheduler.retries`
- **summary**:    Retry configurations for items to be executed, indexed by task address. 