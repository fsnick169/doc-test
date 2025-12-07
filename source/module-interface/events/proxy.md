## proxy
 
 Announced(`AccountId32`, `AccountId32`, `H256`)
- **interface**: `proxy.Announced`
- **summary**:    An announcement was placed to make a call in the future. 
 
 DepositPoked(`AccountId32`, `PalletProxyDepositKind`, `u128`, `u128`)
- **interface**: `proxy.DepositPoked`
- **summary**:    A deposit stored for proxies or announcements was poked / updated. 
 
 ProxyAdded(`AccountId32`, `AccountId32`, `KitchensinkRuntimeProxyType`, `u32`)
- **interface**: `proxy.ProxyAdded`
- **summary**:    A proxy was added. 
 
 ProxyExecuted(`Result<Null, SpRuntimeDispatchError>`)
- **interface**: `proxy.ProxyExecuted`
- **summary**:    A proxy was executed correctly, with the given. 
 
 ProxyRemoved(`AccountId32`, `AccountId32`, `KitchensinkRuntimeProxyType`, `u32`)
- **interface**: `proxy.ProxyRemoved`
- **summary**:    A proxy was removed. 
 
 PureCreated(`AccountId32`, `AccountId32`, `KitchensinkRuntimeProxyType`, `u16`)
- **interface**: `proxy.PureCreated`
- **summary**:    A pure account has been created by new proxy with given  disambiguation index and proxy type. 