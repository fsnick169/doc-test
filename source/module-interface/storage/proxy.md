## proxy
 
 announcements(`AccountId32`): `(Vec<PalletProxyAnnouncement>,u128)`
- **interface**: `proxy.announcements`
- **summary**:    The announcements made by the proxy (key). 
 
 proxies(`AccountId32`): `(Vec<PalletProxyProxyDefinition>,u128)`
- **interface**: `proxy.proxies`
- **summary**:    The set of account proxies. Maps the account which has delegated to the accounts  which are being delegated to, together with the amount held on deposit. 