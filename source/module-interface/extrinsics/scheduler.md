## scheduler
 
 cancel(when: `u32`, index: `u32`)
- **interface**: `scheduler.cancel`
- **summary**:    Cancel an anonymously scheduled task. 
 
 cancelNamed(id: `[u8;32]`)
- **interface**: `scheduler.cancelNamed`
- **summary**:    Cancel a named scheduled task. 
 
 cancelRetry(task: `(u32,u32)`)
- **interface**: `scheduler.cancelRetry`
- **summary**:    Removes the retry configuration of a task. 
 
 cancelRetryNamed(id: `[u8;32]`)
- **interface**: `scheduler.cancelRetryNamed`
- **summary**:    Cancel the retry configuration of a named task. 
 
 schedule(when: `u32`, maybe_periodic: `Option<(u32,u32)>`, priority: `u8`, call: `Call`)
- **interface**: `scheduler.schedule`
- **summary**:    Anonymously schedule a task. 
 
 scheduleAfter(after: `u32`, maybe_periodic: `Option<(u32,u32)>`, priority: `u8`, call: `Call`)
- **interface**: `scheduler.scheduleAfter`
- **summary**:    Anonymously schedule a task after a delay. 
 
 scheduleNamed(id: `[u8;32]`, when: `u32`, maybe_periodic: `Option<(u32,u32)>`, priority: `u8`, call: `Call`)
- **interface**: `scheduler.scheduleNamed`
- **summary**:    Schedule a named task. 
 
 scheduleNamedAfter(id: `[u8;32]`, after: `u32`, maybe_periodic: `Option<(u32,u32)>`, priority: `u8`, call: `Call`)
- **interface**: `scheduler.scheduleNamedAfter`
- **summary**:    Schedule a named task after a delay. 
 
 setRetry(task: `(u32,u32)`, retries: `u8`, period: `u32`)
- **interface**: `scheduler.setRetry`
- **summary**:    Set a retry configuration for a task so that, in case its scheduled run fails, it will  be retried after `period` blocks, for a total amount of `retries` retries or until it  succeeds. 

   Tasks which need to be scheduled for a retry are still subject to weight metering and  agenda space, same as a regular task. If a periodic task fails, it will be scheduled  normally while the task is retrying. 

   Tasks scheduled as a result of a retry for a periodic task are unnamed, non-periodic  clones of the original task. Their retry configuration will be derived from the  original task's configuration, but will have a lower value for `remaining` than the  original `total_retries`. 
 
 setRetryNamed(id: `[u8;32]`, retries: `u8`, period: `u32`)
- **interface**: `scheduler.setRetryNamed`
- **summary**:    Set a retry configuration for a named task so that, in case its scheduled run fails, it  will be retried after `period` blocks, for a total amount of `retries` retries or until  it succeeds. 

   Tasks which need to be scheduled for a retry are still subject to weight metering and  agenda space, same as a regular task. If a periodic task fails, it will be scheduled  normally while the task is retrying. 

   Tasks scheduled as a result of a retry for a periodic task are unnamed, non-periodic  clones of the original task. Their retry configuration will be derived from the  original task's configuration, but will have a lower value for `remaining` than the  original `total_retries`. 