## payment
 
 queryFeeDetails(extrinsic: `Bytes`, at?: `BlockHash`): `FeeDetails`
- **interface**: `payment.queryFeeDetails`
- **jsonrpc**: `payment_queryFeeDetails`
- **summary**: Query the detailed fee of a given encoded extrinsic
- **deprecated**: Use `api.call.transactionPaymentApi.queryFeeDetails` instead
 
 queryInfo(extrinsic: `Bytes`, at?: `BlockHash`): `RuntimeDispatchInfoV1`
- **interface**: `payment.queryInfo`
- **jsonrpc**: `payment_queryInfo`
- **summary**: Retrieves the fee information for an encoded extrinsic
- **deprecated**: Use `api.call.transactionPaymentApi.queryInfo` instead