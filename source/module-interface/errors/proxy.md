## proxy
 
 Duplicate
- **interface**: `proxy.Duplicate.is`
- **summary**:    Account is already a proxy. 
 
 NoPermission
- **interface**: `proxy.NoPermission.is`
- **summary**:    Call may not be made by proxy because it may escalate its privileges. 
 
 NoSelfProxy
- **interface**: `proxy.NoSelfProxy.is`
- **summary**:    Cannot add self as proxy. 
 
 NotFound
- **interface**: `proxy.NotFound.is`
- **summary**:    Proxy registration not found. 
 
 NotProxy
- **interface**: `proxy.NotProxy.is`
- **summary**:    Sender is not a proxy of the account to be proxied. 
 
 TooMany
- **interface**: `proxy.TooMany.is`
- **summary**:    There are too many proxies registered or too many announcements pending. 
 
 Unannounced
- **interface**: `proxy.Unannounced.is`
- **summary**:    Announcement, if made at all, was made too recently. 
 
 Unproxyable
- **interface**: `proxy.Unproxyable.is`
- **summary**:    A call which is incompatible with the proxy type's filter was attempted. 