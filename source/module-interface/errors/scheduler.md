## scheduler
 
 FailedToSchedule
- **interface**: `scheduler.FailedToSchedule.is`
- **summary**:    Failed to schedule a call 
 
 Named
- **interface**: `scheduler.Named.is`
- **summary**:    Attempt to use a non-named function on a named task. 
 
 NotFound
- **interface**: `scheduler.NotFound.is`
- **summary**:    Cannot find the scheduled call. 
 
 RescheduleNoChange
- **interface**: `scheduler.RescheduleNoChange.is`
- **summary**:    Reschedule failed because it does not change scheduled time. 
 
 TargetBlockNumberInPast
- **interface**: `scheduler.TargetBlockNumberInPast.is`
- **summary**:    Given target block number is in the past. 