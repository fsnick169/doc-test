## indices
 
 claim(index: `u32`)
- **interface**: `indices.claim`
- **summary**:    Assign an previously unassigned index. 

   Payment: `Deposit` is reserved from the sender account. 

   The dispatch origin for this call must be _Signed_. 

   - `index`: the index to be claimed. This must not be in use. 

   Emits `IndexAssigned` if successful. 

   Complexity:    O(1).
 
 forceTransfer(new: `MultiAddress`, index: `u32`, freeze: `bool`)
- **interface**: `indices.forceTransfer`
- **summary**:    Force an index to an account. This doesn't require a deposit. If the index is already  held, then any deposit is reimbursed to its current owner. 

   The dispatch origin for this call must be _Root_. 

   - `index`: the index to be (re-)assigned. 

  - `new`: the new owner of the index. This function is a no-op if it is equal to sender.

  - `freeze`: if set to `true`, will freeze the index so it cannot be transferred.

   Emits `IndexAssigned` if successful. 

   Complexity:    O(1).
 
 free(index: `u32`)
- **interface**: `indices.free`
- **summary**:    Free up an index owned by the sender. 

   Payment: Any previous deposit placed for the index is unreserved in the sender account. 

   The dispatch origin for this call must be _Signed_ and the sender must own the index. 

   - `index`: the index to be freed. This must be owned by the sender. 

   Emits `IndexFreed` if successful. 

   Complexity:    O(1).
 
 freeze(index: `u32`)
- **interface**: `indices.freeze`
- **summary**:    Freeze an index so it will always point to the sender account. This consumes the  deposit. 

   The dispatch origin for this call must be _Signed_ and the signing account must have a  non-frozen account `index`. 

   - `index`: the index to be frozen in place. 

   Emits `IndexFrozen` if successful. 

   Complexity:    O(1).
 
 pokeDeposit(index: `u32`)
- **interface**: `indices.pokeDeposit`
- **summary**:    Poke the deposit reserved for an index. 

   The dispatch origin for this call must be _Signed_ and the signing account must have a  non-frozen account `index`. 

   The transaction fees is waived if the deposit is changed after poking/reconsideration. 

   - `index`: the index whose deposit is to be poked/reconsidered. 

   Emits `DepositPoked` if successful. 
 
 transfer(new: `MultiAddress`, index: `u32`)
- **interface**: `indices.transfer`
- **summary**:    Assign an index already owned by the sender to another account. The balance reservation  is effectively transferred to the new account. 

   The dispatch origin for this call must be _Signed_. 

   - `index`: the index to be re-assigned. This must be owned by the sender. 

  - `new`: the new owner of the index. This function is a no-op if it is equal to sender.

   Emits `IndexAssigned` if successful. 

   Complexity:    O(1).