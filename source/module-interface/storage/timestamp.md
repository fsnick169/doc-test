## timestamp
 
 didUpdate(): `bool`
- **interface**: `timestamp.didUpdate`
- **summary**:    Whether the timestamp has been updated in this block. 

   This value is updated to `true` upon successful submission of a timestamp by a node.  It is then checked at the end of each block execution in the `on_finalize` hook. 
 
 now(): `u64`
- **interface**: `timestamp.now`
- **summary**:    The current time for the current block. 