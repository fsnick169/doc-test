## system
 
 applyAuthorizedUpgrade(code: `Bytes`)
- **interface**: `system.applyAuthorizedUpgrade`
- **summary**:    Provide the preimage (runtime binary) `code` for an upgrade that has been authorized. 

   If the authorization required a version check, this call will ensure the spec name  remains unchanged and that the spec version has increased. 

   Depending on the runtime's `OnSetCode` configuration, this function may directly apply  the new `code` in the same block or attempt to schedule the upgrade. 

   All origins are allowed. 
 
 authorizeUpgrade(code_hash: `H256`)
- **interface**: `system.authorizeUpgrade`
- **summary**:    Authorize an upgrade to a given `code_hash` for the runtime. The runtime can be supplied  later. 

   This call requires Root origin. 
 
 authorizeUpgradeWithoutChecks(code_hash: `H256`)
- **interface**: `system.authorizeUpgradeWithoutChecks`
- **summary**:    Authorize an upgrade to a given `code_hash` for the runtime. The runtime can be supplied  later. 

   WARNING: This authorizes an upgrade that will take place without any safety checks, for  example that the spec name remains the same and that the version number increases. Not  recommended for normal use. Use `authorize_upgrade` instead. 

   This call requires Root origin. 
 
 killPrefix(prefix: `Bytes`, subkeys: `u32`)
- **interface**: `system.killPrefix`
- **summary**:    Kill all storage items with a key that starts with the given prefix. 

   **NOTE:** We rely on the Root origin to provide us the number of subkeys under  the prefix we are removing to accurately calculate the weight of this function. 
 
 killStorage(keys: `Vec<Bytes>`)
- **interface**: `system.killStorage`
- **summary**:    Kill some items from storage. 
 
 remark(remark: `Bytes`)
- **interface**: `system.remark`
- **summary**:    Make some on-chain remark. 

   Can be executed by every `origin`. 
 
 remarkWithEvent(remark: `Bytes`)
- **interface**: `system.remarkWithEvent`
- **summary**:    Make some on-chain remark and emit event. 
 
 setCode(code: `Bytes`)
- **interface**: `system.setCode`
- **summary**:    Set the new runtime code. 
 
 setCodeWithoutChecks(code: `Bytes`)
- **interface**: `system.setCodeWithoutChecks`
- **summary**:    Set the new runtime code without doing any checks of the given `code`. 

   Note that runtime upgrades will not run if this is called with a not-increasing spec  version! 
 
 setHeapPages(pages: `u64`)
- **interface**: `system.setHeapPages`
- **summary**:    Set the number of pages in the WebAssembly environment's heap. 
 
 setStorage(items: `Vec<(Bytes,Bytes)>`)
- **interface**: `system.setStorage`
- **summary**:    Set some items of storage. 