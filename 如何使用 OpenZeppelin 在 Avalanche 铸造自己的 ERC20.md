# 使用 OpenZeppelir 在 Avalanche 上铸造 ERC20 
本篇教程参考 [Avalanche 文档](https://docs.avax.network/build/tutorials/smart-digital-assets/create-erc-20-token-on-avalanche-c-chain)
整个流程总共分为 4 步：

1.铸造 ERC20 代币

2.部署合约

3.进行代币交互

4.将代币添加到 Metamask

## 铸造 ERC20 代币
在浏览器中打开 [Remix](https://remix.ethereum.org/#optimize=false&evmVersion=null&version=soljson-v0.6.6+commit.6c089d02.js&runs=200)，点击图中红框标注的 SOLIDITY 。

![](https://github.com/zq19/CatchBall/blob/master/images/20210804004506.jpg)

点击 SOLIDITY 后，如下图，接着点击图中红框标注的 New File。

![](https://github.com/zq19/CatchBall/blob/master/images/20210804005629.jpg)

如果点击 New File 后没有反应，可以点击左上角的文件 icon。

![](https://github.com/zq19/CatchBall/blob/master/images/20210804232717.jpg)

接着我们点击图中红框标注的 icon 来手动创建文件.

![](https://github.com/zq19/CatchBall/blob/master/images/20210804232925.jpg)

可以任意命名，但文件后缀要以 .sol 结尾我这里使用的是Test_File.sol。

![](https://github.com/zq19/CatchBall/blob/master/images/20210804233523.jpg)

接下来我们要编辑这个文件，我们要用到 OpenZeppelir ，在 Test_File.sol 的第一行输入 

```python
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/presets/ERC20PresetMinterPauser.sol";
```
![](https://github.com/zq19/CatchBall/blob/master/images/20210804234416.jpg)

接着我们对 Test_File.sol 进行保存，保存后可以看到出现了许多文件。

![](https://github.com/zq19/CatchBall/blob/master/images/20210804235506.jpg)

我们可以在左侧文件树区域看到一个 ERC20PresetMinterPauser.sol 文件，

![](https://github.com/zq19/CatchBall/blob/master/images/20210804235758.jpg)

这个文件是 OpenZeppelir 通过具有矿工功能的 ERC20 标准编写的。在对这个文件进行部署后，我们将会成为这个合约的 Owner，同时也拥有了对该代币挖矿的权利与能力。

## 部署合约

