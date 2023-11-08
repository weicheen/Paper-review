# INFOCOM 20

### 1.Network Monitoring for SDN Virtual Networks  

*Department of computer science and engineering, Korea University*  
*Citations: 14*

在SDN-VN框架下，Network hypervisor是一种很好的网络管理和优化的工具。但是现有的NH没有提供网络流量监控功能，以致于传统的SDN-VN下的网络监控方法有三个弊端：

+ 不准确的网络统计信息（统计信息是多个运行在网络上的 VN 的汇总，而且没有机制可以从 VN 中检索和隔离这些统计信息）
+ SDN-NV 架构无疑增加了控制器与交换机之间统计信息请求之间的延迟（传输延迟）。统计信息请求消息从控制器传到 NH 时，NH 必须将相应的网络统计信息请求消息发送到物理网络（交换机）并等待接收结果。
+ NH 相对于非虚拟化 SDN 过度消耗控制信道流量，以影响其他的流量。NH 必须发送多个消息到多个交换机以响应来自控制器的请求。

本文提出了一个新的网络监控框架v-sight。V-sight很好地解决了以上三个问题：
- 通过Stastistics virtualization来根据物理网络数据计算孤立的虚拟网络数据。
- pcontroller例行地收集switch中并存在VH中，以减少数据传输地延迟。
- pController用一条请求代替多条请求，以减少控制信息流量。从各个角度，V-sight大大提高了网络地监控效率和准确性。  

  
---  


### 2.Towards Latency Optimization in Hybrid Service Function Chain Composition and Embedding

*Department of Computer Science, Georgia State University, USA*  
*Citations: 36*

本文全面研究并提出了混合SFC构建和嵌入（HSFCE）问题，普通的SFCE问题需要考虑SFC的构成，SF节点和物理网络的映射，以及SF链路的映射。而HSFCE问题则是如何将NF以物理和虚拟化的方式混合部署，并嵌入到网络拓扑中。本文根据不同的物理节点与VNF对应情况提出了两种算法以优化网络的延迟：BC-HSFP与EC-HSFP。其中EC-HSFP用于一个节点上有一个VNF时的情况，它作为一个2倍近似算法用于针对这样一个np-hard问题。而BC-HSFP作为一个启发式算法则对应一个节点上有多个VNF的情况被提出。二者都大大提高了网络的性能，降低了延迟。

###
