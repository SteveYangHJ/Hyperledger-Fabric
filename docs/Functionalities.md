# Hyperledger Fabric 功能
Hyperledger Fabric 是一个实现了分布式账本技术的模块化区块链架构，对此它提供了企业级的安全防护，可扩展性，保密性，以及高性能。

## 身份管理

为了实现权限管控的网络系统，Hyperledger Fabric 提供了包含管理用户 ID 以及对所有网络参与者进行验权的会员身份服务的功能。访问控制列表可以当做额外的权限层，以此来实现不同的用户授权不同的网络操作权限。比如说，一个特定的用户id可以被允许唤起一个 chaincode 应用，但却无法部署新的 chaincode。

## 隐私与保密

Hyperledger Fabric 使相互竞争的商业利益以及任何需要私密交易的群体能够在同一个许可的网络上共存。专用的网络通道（channel）提供一种受限制的消息传输方式，可以向特定的网络成员子集提供事务隐私和机密性。通道上的所有数据（包括交易，成员和频道信息）都是不可见的，任何未明确授予访问该频道的网络成员都无法访问。

## 高效处理

Hyperledger Fabric 按节点类型分配网络角色。为了向网络提供高并发性，事务执行与事务排序及事务广播都是分开的。事务执行的优先级会高于事务排序，这样设计的原因是为了支持多个节点并发的处理事务。这种事务的并发执行特性提高了每个对节点的处理效率，而且也加快了向合约中服务订购者交付的速度。

除了支持并行处理任务外，网络通过劳动分工，分为排序节点（ordering node）与对等节点（peer node），排序节点可以对交易执行进行排序和账本维护，这样一来对等节点也就可以从排序（一致性）工作负载中解脱出来。所有对等节点都不必信任所有的排序节点，反之亦然，因此一个节点上的进程可以独立于另一节点的验证运行。

## Chaincode 功能

Chaincode 应用程序对由通道上特定类型的事务调用的逻辑进行编码。 chaincode 可以为资产所有权变更指定特定参数，这样一来，就确保所有的更换所有权的交易都遵循同样的规则（同一个参数）。其中 system chaincode 与 chaincode 还有所不同，它定义了整个通道（channel）的操作参数：生命周期和配置类的 system chaincode 定义通道的规则；确认和验证类型的 system chaincode 定义了批准和验证交易的要求。

Hyperledger Fabric 为网络设计者实现了模块化的架构。诸如身份识别、排序（共识）、加密算法都能在 Hyperledger Fabric 网络中选择使用（热插拔特性）。这样的结果是任何行业或公共领域都可以采用通用的区块链体系结构，并保证其网络能够跨市场，监管的进行操作。

