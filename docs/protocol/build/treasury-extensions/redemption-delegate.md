# Redemption delegate

Before implementing, learn about delegates [here](/protocol/learn/glossary/delegate.md).
#### Specs

A contract can become a treasury redemption delegate by adhering to [`IJBRedemptionDelegate`](/protocol/api/interfaces/ijbredemptiondelegate.md):

```
interface IJBRedemptionDelegate {
  function didRedeem(JBDidRedeemData calldata _data) external;
}
```

When extending the redemption functionality with a delegate, the protocol will pass a [`JBDidRedeemData`](/protocol/api/data-structures/jbdidredeemdata.md) to the `didRedeem(...)` function:

```
struct JBDidRedeemData {
  address holder;
  uint256 projectId;
  uint256 currentFundingCycleConfiguration;
  uint256 projectTokenCount;
  JBTokenAmount reclaimedAmount;
  address payable beneficiary;
  string memo;
  bytes metadata;
}
```

```
struct JBTokenAmount {
  address token;
  uint256 value;
  uint256 decimals;
  uint256 currency;
}
```

The `msg.sender` to the delegate will be the payment terminal that facilitated the redemption. 

In payment terminals based on the [`JBPayoutRedemptionPaymentTerminal`](/protocol/api/contracts/or-abstract/jbpayoutredemptionpaymentterminal), such as [`JBETHPaymentTerminal`](/protocol/api/contracts/or-payment-terminals/jbethpaymentterminal/README.md)'s and [`JBERC20PaymentTerminal`](/protocol/api/contracts/or-payment-terminals/jberc20paymentterminal/README.md)'s, the redemption delegate hook gets called _before_ the reclaimed amount is sent to the redemption beneficiary, but after all internal accounting has been updated.  [View the docs](/protocol/api/contracts/or-abstract/jbpayoutredemptionpaymentterminal/write/redeemtokensof.md). 

Make sure to only allow trusted contracts to access the `didPay(...)` transaction.

#### Attaching

A delegate contract should be deployed independently. Once deployed, its address can be returned from a data source hook. See [how to build a data source](/protocol/build/treasury-extensions/data-source.md) for more.
