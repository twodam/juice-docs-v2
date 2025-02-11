# Pay delegate

Before implementing, learn about delegates [here](/protocol/learn/glossary/delegate.md).
#### Specs

A contract can become a treasury pay delegate by adhering to [`IJBPayDelegate`](/protocol/api/interfaces/ijbpaydelegate.md):

```
interface IJBPayDelegate {
  function didPay(JBDidPayData calldata _data) external;
}
```

When extending the pay functionality with a delegate, the protocol will pass a [`JBDidPayData`](/protocol/api/data-structures/jbdidpaydata.md) to the `didPay(...)` function:

```
struct JBDidPayData {
  address payer;
  uint256 projectId;
  uint256 currentFundingCycleConfiguration;
  JBTokenAmount amount;
  uint256 projectTokenCount;
  address beneficiary;
  bool preferClaimedTokens;
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

The `msg.sender` to the delegate will be the payment terminal that facilitated the payment. 

In payment terminals based on the [`JBPayoutRedemptionPaymentTerminal`](/protocol/api/contracts/or-abstract/jbpayoutredemptionpaymentterminal), such as [`JBETHPaymentTerminal`](/protocol/api/contracts/or-payment-terminals/jbethpaymentterminal/README.md)'s and [`JBERC20PaymentTerminal`](/protocol/api/contracts/or-payment-terminals/jberc20paymentterminal/README.md)'s, the pay delegate hook gets called _after_ the project's tokens have been minted and distributed. [View the docs](/protocol/api/contracts/or-abstract/jbpayoutredemptionpaymentterminal/write/-_pay.md). 

Make sure to only allow trusted contracts to access the `didPay(...)` transaction.

#### Attaching

A delegate contract should be deployed independently. Once deployed, its address can be returned from a data source hook. See [how to build a data source](/protocol/build/treasury-extensions/data-source.md) for more.
