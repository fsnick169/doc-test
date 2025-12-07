## lottery
 
 callIndices(): `Vec<(u8,u8)>`
- **interface**: `lottery.callIndices`
- **summary**:    The calls stored in this pallet to be used in an active lottery if configured  by `Config::ValidateCall`. 
 
 lottery(): `Option<PalletLotteryLotteryConfig>`
- **interface**: `lottery.lottery`
- **summary**:    The configuration for the current lottery. 
 
 lotteryIndex(): `u32`
- **interface**: `lottery.lotteryIndex`
 
 participants(`AccountId32`): `(u32,Vec<(u8,u8)>)`
- **interface**: `lottery.participants`
- **summary**:    Users who have purchased a ticket. (Lottery Index, Tickets Purchased) 
 
 tickets(`u32`): `Option<AccountId32>`
- **interface**: `lottery.tickets`
- **summary**:    Each ticket's owner. 

   May have residual storage from previous lotteries. Use `TicketsCount` to see which ones  are actually valid ticket mappings. 
 
 ticketsCount(): `u32`
- **interface**: `lottery.ticketsCount`
- **summary**:    Total number of tickets sold. 