
# Start ethereum

## 资源

- [Nodes and Clients](https://ethereum.org/en/developers/docs/nodes-and-clients/#consensus-clients)
- [Consensus Layer](https://docs.prylabs.network/docs/getting-started)
  - [Github](https://github.com/prysmaticlabs/prysm)
- Source code
  - [Understanding Ethereum Go](https://github.com/ABCDELabs/Understanding-Ethereum-Go-version)
  - [go-ethereum-code-analysis](https://github.com/ZtesoftCS/go-ethereum-code-analysis)
  - [go-ethereum-code-analysis english version](https://github.com/agiletechvn/go-ethereum-code-analysis)
  - [深入理解以太坊](https://gist.github.com/stonegao/16b8a30d98c4723f04f8259b7eda5da8)
  - [以太坊设计与实现](https://learnblockchain.cn/books/geth/)

## 基本结构

Ethereum 在 The-Merge 之后，由 Execution node 和 Beacon node 组成，Execution Client 和 Consensus Client 组合在一起工作，他们
两者之间可以使用 IPC 或 HTTP + JWT 的方式相互通信

## Build & Start

从启动 Ethereum 开始

项目提供了 Makefile，非常方便的帮助我们来编译 Go 项目

```shell
make all
```

运行之后会在 project 中会自动创建 build 目录，在 `build/bin` 中就可以找到 `geth` 可运行客户端；同时还生成了其他的工具命令。在 README.md 中对命令
的详细解释

|  Command   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| :--------: |------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`geth`** | 这个是以太坊 cli 客户端                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|   `clef`   | 一个独立的签名工具，可以作为 geth 的签名工具                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|  `devp2p`  | 与网络层上的节点交互的实用程序，无需运行完整的区块链。                                                                                                                                                                                                                                                                                                                                                                                                                       |
|  `abigen`  | 源代码生成器，用于将以太坊合约定义转换为易于使用、编译时类型安全的 Go 包。 它在普通的[以太坊合约 ABI](https://docs.soliditylang.org/en/develop/abi-spec.html) 上运行，如果合约字节码也可用，则具有扩展功能。 然而，它也接受 Solidity 源文件，使开发更加简化。 请参阅我们的 [Native DApps](https://geth.ethereum.org/docs/developers/dapp-developer/native-bindings) 页面了解详细信息。 |
| `bootnode` | 我们的以太坊客户端实现的精简版本，仅参与网络节点发现协议，但不运行任何更高级别的应用程序协议。 它可以用作轻量级引导节点，以帮助在专用网络中查找对等点。                                                                                                                                                                                                                                |
|   `evm`    | EVM（以太坊虚拟机）的开发实用程序版本，能够在可配置的环境和执行模式中运行字节码片段。 其目的是允许对 EVM 操作码进行隔离、细粒度的调试，例如 evm --code 60ff60ff --debug run                                                                                                                                                                                                                                                                                                                                                                                                             |
| `rlpdump`  | 用于转换二进制 RLP（[递归长度前缀](https://ethereum.org/en/developers/docs/data-structs-and-encoding/rlp)）转储（以太坊协议和网络使用的数据编码）的开发人员实用工具 以及共识）到用户友好的层次表示（例如`rlpdump --hex CE0183FFFFFFC4C304050583616263`）。                                                                                                                                                               |

运行 geth 可以启动一个 Ethereum 的节点。


