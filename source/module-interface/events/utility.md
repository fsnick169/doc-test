## utility
 
 BatchCompleted()
- **interface**: `utility.BatchCompleted`
- **summary**:    Batch of dispatches completed fully with no error. 
 
 BatchCompletedWithErrors()
- **interface**: `utility.BatchCompletedWithErrors`
- **summary**:    Batch of dispatches completed but has errors. 
 
 BatchInterrupted(`u32`, `SpRuntimeDispatchError`)
- **interface**: `utility.BatchInterrupted`
- **summary**:    Batch of dispatches did not complete fully. Index of first failing dispatch given, as  well as the error. 
 
 DispatchedAs(`Result<Null, SpRuntimeDispatchError>`)
- **interface**: `utility.DispatchedAs`
- **summary**:    A call was dispatched. 
 
 IfElseFallbackCalled(`SpRuntimeDispatchError`)
- **interface**: `utility.IfElseFallbackCalled`
- **summary**:    The fallback call was dispatched. 
 
 IfElseMainSuccess()
- **interface**: `utility.IfElseMainSuccess`
- **summary**:    Main call was dispatched. 
 
 ItemCompleted()
- **interface**: `utility.ItemCompleted`
- **summary**:    A single item within a Batch of dispatches has completed with no error. 
 
 ItemFailed(`SpRuntimeDispatchError`)
- **interface**: `utility.ItemFailed`
- **summary**:    A single item within a Batch of dispatches has completed with error. 