## system
 
 CodeUpdated()
- **interface**: `system.CodeUpdated`
- **summary**:    `:code` was updated. 
 
 ExtrinsicFailed(`SpRuntimeDispatchError`, `FrameSystemDispatchEventInfo`)
- **interface**: `system.ExtrinsicFailed`
- **summary**:    An extrinsic failed. 
 
 ExtrinsicSuccess(`FrameSystemDispatchEventInfo`)
- **interface**: `system.ExtrinsicSuccess`
- **summary**:    An extrinsic completed successfully. 
 
 KilledAccount(`AccountId32`)
- **interface**: `system.KilledAccount`
- **summary**:    An account was reaped. 
 
 NewAccount(`AccountId32`)
- **interface**: `system.NewAccount`
- **summary**:    A new account was created. 
 
 RejectedInvalidAuthorizedUpgrade(`H256`, `SpRuntimeDispatchError`)
- **interface**: `system.RejectedInvalidAuthorizedUpgrade`
- **summary**:    An invalid authorized upgrade was rejected while trying to apply it. 
 
 Remarked(`AccountId32`, `H256`)
- **interface**: `system.Remarked`
- **summary**:    On on-chain remark happened. 
 
 UpgradeAuthorized(`H256`, `bool`)
- **interface**: `system.UpgradeAuthorized`
- **summary**:    An upgrade was authorized. 