# isFeelessAddress

Contract: [`JBPayoutRedemptionPaymentTerminal`](/protocol/api/contracts/or-abstract/jbpayoutredemptionpaymentterminal/README.md)​‌

Interface: [`IJBPayoutRedemptionPaymentTerminal`](/protocol/api/interfaces/ijbpayoutredemptionpaymentterminal.md)

**Addresses that can be paid towards from this terminal without incurring a fee.**

#### Definition

```
/**
  @notice
  Addresses that can be paid towards from this terminal without incurring a fee.

  _address The address that can be paid toward.
*/
mapping(address => bool) public override isFeelessAddress;
```

* Arguments:
  * `_address` is the address that can be paid toward.
* The resulting view function can be accessed externally by anyone.
* The resulting function overrides a function definition from the [`IJBPayoutRedemptionPaymentTerminal`](/protocol/api/interfaces/ijbpayoutredemptionpaymentterminal.md) interface.
