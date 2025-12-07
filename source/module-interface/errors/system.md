## system
 
 CallFiltered
- **interface**: `system.CallFiltered.is`
- **summary**:    The origin filter prevent the call to be dispatched. 
 
 FailedToExtractRuntimeVersion
- **interface**: `system.FailedToExtractRuntimeVersion.is`
- **summary**:    Failed to extract the runtime version from the new runtime. 

   Either calling `Core_version` or decoding `RuntimeVersion` failed. 
 
 InvalidSpecName
- **interface**: `system.InvalidSpecName.is`
- **summary**:    The name of specification does not match between the current runtime  and the new runtime. 
 
 MultiBlockMigrationsOngoing
- **interface**: `system.MultiBlockMigrationsOngoing.is`
- **summary**:    A multi-block migration is ongoing and prevents the current code from being replaced. 
 
 NonDefaultComposite
- **interface**: `system.NonDefaultComposite.is`
- **summary**:    Suicide called when the account has non-default composite data. 
 
 NonZeroRefCount
- **interface**: `system.NonZeroRefCount.is`
- **summary**:    There is a non-zero reference count preventing the account from being purged. 
 
 NothingAuthorized
- **interface**: `system.NothingAuthorized.is`
- **summary**:    No upgrade authorized. 
 
 SpecVersionNeedsToIncrease
- **interface**: `system.SpecVersionNeedsToIncrease.is`
- **summary**:    The specification version is not allowed to decrease between the current runtime  and the new runtime. 
 
 Unauthorized
- **interface**: `system.Unauthorized.is`
- **summary**:    The submitted code is not authorized. 