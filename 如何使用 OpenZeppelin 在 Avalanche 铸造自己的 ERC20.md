# 使用 OpenZeppelir 在 Avalanche 上铸造 ERC20 
本篇教程参考 [Avalanche 文档](https://docs.avax.network/build/tutorials/smart-digital-assets/create-erc-20-token-on-avalanche-c-chain)
整个流程总共分为 4 步：

1.铸造 ERC20 代币

2.部署合约

3.进行代币交互

4.将代币添加到 Metamask

## 铸造 ERC20 代币
在浏览器中打开 [Remix](http://remix.ethereum.org/#optimize=false&evmVersion=null&version=soljson-v0.8.6+commit.11564f7e.js&runs=200)，浏览器可能会提示不安全，不用担心。

接着我们点击图中红框标注的 icon 或者 New File 来手动创建文件.

![](https://github.com/zq19/CatchBall/blob/master/images/20210806000111.jpg)

可以任意命名，但文件后缀要以 .sol 结尾我这里使用的是Test_File.sol。

![](https://github.com/zq19/CatchBall/blob/master/images/20210806000321.jpg)

回车保存 Test_File.sol 后，我们开始编辑这个文件，这里我们要用到 OpenZeppelir ，在 Test_File.sol 的第一行输入 

```python
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/presets/ERC20PresetMinterPauser.sol";
```

保存后可以看到左侧出现了一系列的文件。

![](https://github.com/zq19/CatchBall/blob/master/images/20210806000630.jpg)

点击 ERC20PresetMinterPauser.sol 文件后，会自动进行编译。

![](https://github.com/zq19/CatchBall/blob/master/images/20210806001221.jpg)

这个文件是 OpenZeppelir 通过具有矿工功能的 ERC20 标准编写的。在对这个文件进行部署后，我们将会成为这个合约的 Owner，同时也拥有了对该代币挖矿的权利与能力。

## 部署合约

前面我们点击 ERC20PresetMinterPauser.sol 文件后，自动进行了编译。我们点击左侧第二个 tab "SOLIDITY COMPILER"，进行查看，可以看到编译已经完成(红框标注的地方)。如果点击进来后，发现还没有编译完成，不要着急。首先确定两个绿色标注的版本号是否符合要求，当 COMPILER 的版本号大于等于 pragma solidity 的版本号时，编译才可正常进行。切换至满足要求的 COMPILER 版本号后，我们可以点击蓝色框标注的编译按钮进行编译（当你切换至满足要求的 COMPILER 版本号后，Remix 会自动尝试编译）。

![](https://github.com/zq19/CatchBall/blob/master/images/20210806001600.jpg)

接下来我们点击左侧第三个 tab "DEPLOY & RUN TRANSACTION"。

![](https://github.com/zq19/CatchBall/blob/master/images/20210806002228.jpg)

在我们部署之前，我们要先切换环境至 "Injected Web3"，另外确保你的浏览器装有可正常使用的 MetaMask 钱包插件。

![](https://github.com/zq19/CatchBall/blob/master/images/20210806002732.jpg)

在切换环境至 "Injected Web3" 之后，Remix 需要连接 MetaMask 进行交互。连接之后，可以看到连接的钱包地址，以及 "Deploy" 按钮。

![](https://github.com/zq19/CatchBall/blob/master/images/20210806003147.jpg)

接着我们需要更换合约 "CONTRACT"，选择图中红框标注的合约 "ERC20PresetMinterPauser"。

![](https://github.com/zq19/CatchBall/blob/master/images/20210806003747.jpg)

接着我们点击 "Deploy" 按钮旁的下拉菜单来设置 ERC20 代币的名称和符号。
