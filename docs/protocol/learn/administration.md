---
sidebar_position: 3
---
# Administration

The protocol has very minimal global governance. The following are the only global functions that can be accessed by a privileged administrating address, initially the JuiceboxDAO multisig:

* **[`JBProjects.setTokenUriResolver(...)`](/protocol/api/contracts/jbprojects/write/settokenuriresolver.md)**<br/>
  Allows the owner of the [`JBProjects`](/protocol/api/contracts/jbprojects/README.md) contract to provide and change the [`IJBTokenUriResolver`](/protocol/api/interfaces/ijbtokenuriresolver.md) used to resolve metadata for project NFTs in its [`tokenURI(...)`](/protocol/api/contracts/jbprojects/read/tokenuri.md) function.
  <br/>
* **[`JBPrices.addFeedFor(...)`](/protocol/api/contracts/jbprices/write/addfeed.md)**<br/>
  Allows the owner of the [`JBPrices`](/protocol/api/contracts/jbprices/README.md) contract to add new price feeds used to convert amounts denoted in one currency to another. Once added, a price feed cannot be removed.
  <br/>
* **[`JBDirectory.setIsAllowedToSetFirstController(...)`](/protocol/api/contracts/jbdirectory/write/setisallowedtosetfirstcontroller.md)**<br/>
  Allows the owner of the [`JBDirectory`](/protocol/api/contracts/jbdirectory/README.md) contract to add/remove addresses that can set a project's first controller on its behalf. 
  <br/>
* **[`JBETHPaymentTerminal.setFee(...)`](/protocol/api/contracts/or-abstract/jbpayoutredemptionpaymentterminal/write/setfee.md)**<br/>
  Allows the owner of the [`JBETHPaymentTerminal`](/protocol/api/contracts/or-payment-terminals/jbethpaymentterminal/README.md) (or any other terminal inheriting from [`JBPayoutRedemptionPaymentTerminal`](/protocol/api/contracts/or-abstract/jbpayoutredemptionpaymentterminal/README.md)) to change the protocol fee incurred when projects distribute their treasury funds outside of the protocol ecosystem. The max fee is 5%.
  <br/>
* **[`JBETHPaymentTerminal.setFeeGauge(...)`](/protocol/api/contracts/or-abstract/jbpayoutredemptionpaymentterminal/write/setfeegauge.md)**<br/>
  Allows the owner of the [`JBETHPaymentTerminal`](/protocol/api/contracts/or-payment-terminals/jbethpaymentterminal/README.md) (or any other terminal inheriting from [`JBPayoutRedemptionPaymentTerminal`](/protocol/api/contracts/or-abstract/jbpayoutredemptionpaymentterminal/README.md)) to change the fee gauge used to provide fee discounts on a per-project basis. 
  <br/>
* **[`JBETHPaymentTerminal.setFeelessAddress(...)`](/protocol/api/contracts/or-abstract/jbpayoutredemptionpaymentterminal/write/setfeelessaddress.md)**<br/>
  Allows the owner of the [`JBETHPaymentTerminal`](/protocol/api/contracts/or-payment-terminals/jbethpaymentterminal/README.md) (or any other terminal inheriting from [`JBPayoutRedemptionPaymentTerminal`](/protocol/api/contracts/or-abstract/jbpayoutredemptionpaymentterminal/README.md)) to add/remove any other address used by other projects to/from a list of address to which distributed funds can be sent without incurring protocol fees, and from which funds can be added back to the project's balance without refunding held fees. 
  <br/>

Ownership for each contract is managed independently and can be transferred to a new owner by the current owner.
