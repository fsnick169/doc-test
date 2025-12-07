## utility
 
 asDerivative(index: `u16`, call: `Call`)
- **interface**: `- utility.asDerivative`
- **summary**:    Send a call through an indexed pseudonym of the sender. 

   Filter from origin are passed along. The call will be dispatched with an origin which  use the same filter as the origin of this call. 

   NOTE: If you need to ensure that any account-based filtering is not honored (i.e.  because you expect `proxy` to have been used prior in the call stack and you do not want  the call restrictions to apply to any sub-accounts), then use `as_multi_threshold_1`  in the Multisig pallet instead. 

   NOTE: Prior to version *12, this was called `as_limited_sub`. 

   The dispatch origin for this call must be _Signed_. 
 
 batch(calls: `Vec<Call>`)
- **interface**: `- utility.batch`
- **summary**:    Send a batch of dispatch calls. 

   May be called from any origin except `None`. 

   - `calls`: The calls to be dispatched from the same origin. The number of call must not  exceed the constant: `batched_calls_limit` (available in constant metadata). 

   If origin is root then the calls are dispatched without checking origin filter. (This  includes bypassing `frame_system::Config::BaseCallFilter`). 

-  Complexity 

  - O(C) where C is the number of calls to be batched.

   This will return `Ok` in all circumstances. To determine the success of the batch, an  event is deposited. If a call failed and the batch was interrupted, then the  `BatchInterrupted` event is deposited, along with the number of successful calls made  and the error of the failed call. If all were successful, then the `BatchCompleted`  event is deposited. 
 
 batchAll(calls: `Vec<Call>`)
- **interface**: `- utility.batchAll`
- **summary**:    Send a batch of dispatch calls and atomically execute them.  The whole transaction will rollback and fail if any of the calls failed. 

   May be called from any origin except `None`. 

   - `calls`: The calls to be dispatched from the same origin. The number of call must not  exceed the constant: `batched_calls_limit` (available in constant metadata). 

   If origin is root then the calls are dispatched without checking origin filter. (This  includes bypassing `frame_system::Config::BaseCallFilter`). 

-  Complexity 

  - O(C) where C is the number of calls to be batched.
 
 dispatchAs(as_origin: `KitchensinkRuntimeOriginCaller`, call: `Call`)
- **interface**: `- utility.dispatchAs`
- **summary**:    Dispatches a function call with a provided origin. 

   The dispatch origin for this call must be _Root_. 

-  Complexity 

  - O(1).
 
 dispatchAsFallible(as_origin: `KitchensinkRuntimeOriginCaller`, call: `Call`)
- **interface**: `- utility.dispatchAsFallible`
- **summary**:    Dispatches a function call with a provided origin. 

   Almost the same as [`Pallet::dispatch_as`] but forwards any error of the inner call. 

   The dispatch origin for this call must be _Root_. 
 
 forceBatch(calls: `Vec<Call>`)
- **interface**: `- utility.forceBatch`
- **summary**:    Send a batch of dispatch calls.  Unlike `batch`, it allows errors and won't interrupt. 

   May be called from any origin except `None`. 

   - `calls`: The calls to be dispatched from the same origin. The number of call must not  exceed the constant: `batched_calls_limit` (available in constant metadata). 

   If origin is root then the calls are dispatch without checking origin filter. (This  includes bypassing `frame_system::Config::BaseCallFilter`). 

-  Complexity 

  - O(C) where C is the number of calls to be batched.
 
 ifElse(main: `Call`, fallback: `Call`)
- **interface**: `- utility.ifElse`
- **summary**:    Dispatch a fallback call in the event the main call fails to execute.  May be called from any origin except `None`. 

   This function first attempts to dispatch the `main` call.  If the `main` call fails, the `fallback` is attemted.  if the fallback is successfully dispatched, the weights of both calls  are accumulated and an event containing the main call error is deposited. 

   In the event of a fallback failure the whole call fails  with the weights returned. 

   - `main`: The main call to be dispatched. This is the primary action to execute. 

  - `fallback`: The fallback call to be dispatched in case the `main` call fails.

-  Dispatch Logic 

  - If the origin is `root`, both the main and fallback calls are executed without applying any origin filters. 

  - If the origin is not `root`, the origin filter is applied to both the `main` and `fallback` calls. 

-  Use Case 

  - Some use cases might involve submitting a `batch` type call in either main, fallback or both. 
 
 withWeight(call: `Call`, weight: `SpWeightsWeightV2Weight`)
- **interface**: `- utility.withWeight`
- **summary**:    Dispatch a function call with a specified weight. 

   This function does not check the weight of the call, and instead allows the  Root origin to specify the weight of the call. 

   The dispatch origin for this call must be _Root_. 