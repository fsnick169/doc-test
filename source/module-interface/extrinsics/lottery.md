## lottery
 
 buyTicket(call: `Call`)
- **interface**: `lottery.buyTicket`
- **summary**:    Buy a ticket to enter the lottery. 

   This extrinsic acts as a passthrough function for `call`. In all  situations where `call` alone would succeed, this extrinsic should  succeed. 

   If `call` is successful, then we will attempt to purchase a ticket,  which may fail silently. To detect success of a ticket purchase, you  should listen for the `TicketBought` event. 

   This extrinsic must be called by a signed origin. 
 
 setCalls(calls: `Vec<Call>`)
- **interface**: `lottery.setCalls`
- **summary**:    Set calls in storage which can be used to purchase a lottery ticket. 

   This function only matters if you use the `ValidateCall` implementation  provided by this pallet, which uses storage to determine the valid calls. 

   This extrinsic must be called by the Manager origin. 
 
 startLottery(price: `u128`, length: `u32`, delay: `u32`, repeat: `bool`)
- **interface**: `lottery.startLottery`
- **summary**:    Start a lottery using the provided configuration. 

   This extrinsic must be called by the `ManagerOrigin`. 

   Parameters: 

   * `price`: The cost of a single ticket. 

  * `length`: How long the lottery should run for starting at the current block.

  * `delay`: How long after the lottery end we should wait before picking a winner.

  * `repeat`: If the lottery should repeat when completed.
 
 stopRepeat()
- **interface**: `lottery.stopRepeat`
- **summary**:    If a lottery is repeating, you can use this to stop the repeat.  The lottery will continue to run to completion. 

   This extrinsic must be called by the `ManagerOrigin`. 