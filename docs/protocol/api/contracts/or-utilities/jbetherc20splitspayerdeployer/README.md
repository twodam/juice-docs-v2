# JBETHERC20SplitsPayerDeployer

_Deploys [`JBETHERC20SplitsPayer`](/protocol/api/contracts/or-utilities/jbetherc20splitspayer) contracts._

https://github.com/jbx-protocol/juice-contracts-v2/blob/main/contracts/JBETHERC20SplitsPayerDeployer.sol

#### Addresses

Ethereum mainnet: [`0xA699372AF7DD3D451Ac27a75715E025103b6A0c5`](https://etherscan.io/address/0xA699372AF7DD3D451Ac27a75715E025103b6A0c5)

Ethereum rinkeby: [`0x3DB8832Cb07e130C14E7f02Ea7e0A8e901D41737`](https://rinkeby.etherscan.io/address/0x3DB8832Cb07e130C14E7f02Ea7e0A8e901D41737)

#### Interfaces

| Name                                                 | Description                                                                                                                              |
| ---------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| [**`IJBETHERC20SplitsPayerDeployer`**](/protocol/api/interfaces/ijbetherc20splitspayerdeployer.md) | General interface for the methods in this contract that interact with the blockchain's state according to the protocol's rules. |


#### Events

| Name                                                                                                      | Data                                                                                                                                                                                                                                 |
| --------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [**`DeploySplitsPayer`**](/protocol/api/contracts/or-utilities/jbetherc20splitspayerdeployer/events/deploysplitspayer.md)                                                                          | <ul><li><code>[IJBSplitsPayer](/protocol/api/interfaces/ijbsplitspayer.md) indexed splitsPayer</code></li><li><code>uint256 indexed defaultSplitsProjectId</code></li><li><code>uint256 defaultSplitsDomain</code></li><li><code>uint256 defaultSplitsGroup</code></li><li><code>[IJBSplitStore](/protocol/api/interfaces/ijbsplitsstore.md) splitStore</code></li><li><code>uint256 defaultProjectId</code></li><li><code>address defaultBeneficiary</code></li><li><code>bool defaultPreferClaimedTokens</code></li><li><code>string defaultMemo</code></li><li><code>bytes defaultMetadata</code></li><li><code>bool preferAddToBalance</code></li><li><code>address caller</code></li></ul>                  |


#### Write

| Function                                                                                                     | Definition                                                                                                                                                                                                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [**`deploySplitsPayer`**](/protocol/api/contracts/or-utilities/jbetherc20splitspayerdeployer/write/deploysplitspayer.md)                                                                        | <p><strong>Params</strong></p><ul><li><code>uint256 defaultSplitsProjectId</code></li><li><code>uint256 _defaultSplitsDomain</code></li><li><code>uint256 _defaultSplitsGroup</code></li><li><code>[IJBSplitStore](/protocol/api/interfaces/ijbsplitsstore.md) _splitsStore</code></li><li><code>uint256 _defaultProjectId</code></li><li><code>address _defaultBeneficiary</code></li><li><code>bool _defaultPreferClaimedTokens</code></li><li><code>string _defaultMemo</code></li><li><code>bytes _defaultMetadata</code></li><li><code>bool _preferAddToBalance</code></li><li><code>address _owner</code></li></ul><p><strong>Returns</strong></p><ul><li><code>[IJBSplitsPayer](/protocol/api/interfaces/ijbsplitspayer.md) splitsPayer</code></li></ul>                                            |
                                             |
