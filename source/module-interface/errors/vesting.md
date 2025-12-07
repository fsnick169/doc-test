## vesting
 
 AmountLow
- **interface**: `vesting.AmountLow.is`
- **summary**:    Amount being transferred is too low to create a vesting schedule. 
 
 AtMaxVestingSchedules
- **interface**: `vesting.AtMaxVestingSchedules.is`
- **summary**:    The account already has `MaxVestingSchedules` count of schedules and thus  cannot add another one. Consider merging existing schedules in order to add another. 
 
 InvalidScheduleParams
- **interface**: `vesting.InvalidScheduleParams.is`
- **summary**:    Failed to create a new schedule because some parameter was invalid. 
 
 NotVesting
- **interface**: `vesting.NotVesting.is`
- **summary**:    The account given is not vesting. 
 
 ScheduleIndexOutOfBounds
- **interface**: `vesting.ScheduleIndexOutOfBounds.is`
- **summary**:    An index was out of bounds of the vesting schedules. 