# PalletOne安全和隐私注意事项

## 安全考虑

PalletOne DID方法作为安全性考虑到以下几点：

- 防止DDoS攻击


PalletOne DID方法通过以下几个方面防止DDoS攻击：

1. Request频率限制；
2. 交易费证明；
3. 数据大小限制；
4. PalletOne作为基础公链，本身具有防止DDoS攻击的功能。

- 防止隐私数据盗窃攻击


在PlletOne DID方法中，用户可以选择将隐私数据存放在本地，或者存放在IPFS上。IPFS的两个特点是：数据分散存储，并且每一份数据文件都通过用户的私钥进行加密。而IPFS的私钥信息由用户进行保管。所以即使黑客获取到了IPFS的数据，没有用户的私钥信息也无法获取其中的内容。

- 共识安全


PalletOne采用DPOS和PBFT两层共识算法来保持区块链节点的稳定性。PalletOne每一轮有21个超级节点在负责产块，产块间隔是5秒。如要成为PalletOne的超级节点，有两步：1）需要质押50万个PTN；2）由所有拥有PTN的PalletOne用户对这些质押节点进行投票，投票总数为前21个作为每轮PalletOne公链区块的生产者。而且如果发现有的节点恶意不产块或其他作恶情况，则可以由社区投票，去掉该作恶节点超级节点的身份，并没收其质押的50万个PTN。

## 隐私注意事项

PalletOne对用户隐私数据的保护主要从以下几个方面进行。

- 隐私数据存储保护

上述“安全考虑”模块中提到，为了防止隐私数据盗窃攻击，PalletOne DID 方法中用户可以选择本地存储和IPFS存储两种方式。

- 隐私数据不上链

在PalletOne DID方法中，用户的隐私数据，比如DID Document、可验证声明等信息是不存储在区块链上，而是将Anchor File的Hash存储的区块链上。这样既可以在区块链上做了存证，也保护了用户各种证件的隐私性。

- 数据多重授权访问

由于可验证声明是隐私性极高的证件信息，所以在PalletOne DID方法中，用户可以设置文件为3中属性：公开、半透明、绝对私密。公开属性是所有人都可以看，极少使用。而半透明属性需要用户的授权别人才能访问，且即使授权了也无法获得整个文件信息，而是只是返回对应的认证信息。绝对私密是除了用户本人，其他任何人都是无法看到的。