## balances
 
 Transfer(source: `MultiAddress`, dest: `MultiAddress`, value: `Compact<u128>`)
- **interface**: `balances.Transfer`
- **summary**:    Transfer some liquid free balance to another account.
 
 transferAll(dest: `MultiAddress`, keep_alive: `bool`)
- **interface**: `balances.transferAll`
- **summary**:    Transfer the entire transferable balance from the caller account. 

   NOTE: This function only attempts to transfer _transferable_ balances. This means that  any locked, reserved, or existential deposits (when `keep_alive` is `true`), will not be  transferred by this function. To ensure that this function results in a killed account,  you might need to prepare the account by removing any reference counters, storage  deposits, etc... 

   The dispatch origin of this call must be Signed. 

   - `dest`: The recipient of the transfer. 

   - `keep_alive`: A boolean to determine if the `transfer_all` operation should send all of the funds the account has, causing the sender account to be killed (false), or  transfer everything except at least the existential deposit, which will guarantee to  keep the sender account alive (true). 
 
 transferKeepAlive(dest: `MultiAddress`, value: `Compact<u128>`)
- **interface**: `balances.transferKeepAlive`
- **summary**:    Same as the [`Transfer`] call, but with a check that the transfer will not  kill the origin account. 