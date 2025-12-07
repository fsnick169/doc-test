## indices
 
 DepositPoked(`AccountId32`, `u32`, `u128`, `u128`)
- **interface**: `indices.DepositPoked`
- **summary**:    A deposit to reserve an index has been poked/reconsidered. 
 
 IndexAssigned(`AccountId32`, `u32`)
- **interface**: `indices.IndexAssigned`
- **summary**:    A account index was assigned. 
 
 IndexFreed(`u32`)
- **interface**: `indices.IndexFreed`
- **summary**:    A account index has been freed up (unassigned). 
 
 IndexFrozen(`u32`, `AccountId32`)
- **interface**: `indices.IndexFrozen`
- **summary**:    A account index has been frozen to its current account ID. 