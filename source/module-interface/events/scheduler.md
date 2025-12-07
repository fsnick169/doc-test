## scheduler
 
 AgendaIncomplete(`u32`)
- **interface**: `scheduler.AgendaIncomplete`
- **summary**:    Agenda is incomplete from `when`. 
 
 CallUnavailable(`(u32,u32)`, `Option<[u8;32]>`)
- **interface**: `scheduler.CallUnavailable`
- **summary**:    The call for the provided hash was not found so the task has been aborted. 
 
 Canceled(`u32`, `u32`)
- **interface**: `scheduler.Canceled`
- **summary**:    Canceled some task. 
 
 Dispatched(`(u32,u32)`, `Option<[u8;32]>`, `Result<Null, SpRuntimeDispatchError>`)
- **interface**: `scheduler.Dispatched`
- **summary**:    Dispatched some task. 
 
 PeriodicFailed(`(u32,u32)`, `Option<[u8;32]>`)
- **interface**: `scheduler.PeriodicFailed`
- **summary**:    The given task was unable to be renewed since the agenda is full at that block. 
 
 PermanentlyOverweight(`(u32,u32)`, `Option<[u8;32]>`)
- **interface**: `scheduler.PermanentlyOverweight`
- **summary**:    The given task can never be executed since it is overweight. 
 
 RetryCancelled(`(u32,u32)`, `Option<[u8;32]>`)
- **interface**: `scheduler.RetryCancelled`
- **summary**:    Cancel a retry configuration for some task. 
 
 RetryFailed(`(u32,u32)`, `Option<[u8;32]>`)
- **interface**: `scheduler.RetryFailed`
- **summary**:    The given task was unable to be retried since the agenda is full at that block or there  was not enough weight to reschedule it. 
 
 RetrySet(`(u32,u32)`, `Option<[u8;32]>`, `u32`, `u8`)
- **interface**: `scheduler.RetrySet`
- **summary**:    Set a retry configuration for some task. 
 
 Scheduled(`u32`, `u32`)
- **interface**: `scheduler.Scheduled`
- **summary**:    Scheduled some task. 