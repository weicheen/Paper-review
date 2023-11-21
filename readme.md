# INFOCOM 

## 1.Network Monitoring for SDN Virtual Networks  

*Department of computer science and engineering, Korea University*  
*Citations: 14*


本文提到的场景为SDN-NV，也就是virtualized SDN。在这种网络架构如下图所示。
![image](https://github.com/weicheen/Paper-review/blob/master/infocom/2020/asset/1.png)

在SDN-VN框架下，Network hypervisor是一种很好的网络管理和优化的工具。但是现有的NH没有提供网络流量监控功能，以致于传统的SDN-VN下的网络监控方法有三个弊端：

+ 不准确的网络统计信息（统计信息是多个运行在网络上的 VN 的汇总，而且没有机制可以从 VN 中检索和隔离这些统计信息）
+ SDN-NV 架构无疑增加了控制器与交换机之间统计信息请求之间的延迟（传输延迟）。统计信息请求消息从控制器传到 NH 时，NH 必须将相应的网络统计信息请求消息发送到物理网络（交换机）并等待接收结果。
+ NH 相对于非虚拟化 SDN 过度消耗控制信道流量，以影响其他的流量。NH 必须发送多个消息到多个交换机以响应来自控制器的请求。

本文提出了一个新的网络监控框架v-sight。V-sight很好地解决了以上三个问题：
- 通过Stastistics virtualization来根据物理网络数据计算孤立的虚拟网络数据。
- pcontroller例行地收集switch中并存在VH中，以减少数据传输地延迟。
- pController用一条请求代替多条请求，以减少控制信息流量。从各个角度，V-sight大大提高了网+-2A络地监控效率和准确性。  

SDN中网络监控有三个步骤如下图所示：
![image](https://github.com/weicheen/Paper-review/blob/master/infocom/2020/asset/2.png)

本文提出的架构如下图：
![image](https://github.com/weicheen/Paper-review/blob/master/infocom/2020/asset/3.png)

## 2.Towards Latency Optimization in Hybrid Service Function Chain Composition and Embedding

*Department of Computer Science, Georgia State University, USA*  
*Citations: 36*

本文全面研究并提出了混合SFC构建和嵌入（HSFCE）问题，普通的SFCE问题需要考虑SFC的构成，SF节点和物理网络的映射，以及SF链路的映射。而HSFCE问题则是如何将NF以物理和虚拟化的方式混合部署，并嵌入到网络拓扑中。本文根据不同的物理节点与VNF对应情况提出了两种算法以优化网络的延迟：BC-HSFP与EC-HSFP。其中EC-HSFP用于一个节点上有一个VNF时的情况，它作为一个2倍近似算法用于针对这样一个np-hard问题。而BC-HSFP作为一个启发式算法则对应一个节点上有多个VNF的情况被提出。二者都大大提高了网络的性能，降低了延迟。

## 3.Consistent and Continuous Network Update in Software-Defined Networks

*Yale University, Nanjing University, Lancaster University*  
*Citations: 8*

网络中的更新通常只能在单个更新完成后执行。而由于现在的网络环境的高频变化以及大量处理事件，导致网络在这种常规更新方式下的高延迟以及低性能，引发了blackhole，loop以及congestion等问题。而持续优化的网络可以解决这些问题。本文提出的Coeus模型在Update Algebra的基础之上了网络的持续更新和优化。为此，本文主要基于提出的dynamic operation dependency graph动态重建操作图以捕捉未执行的更新操作，operation composition消除冗余命令，以及operation node partition Algo加速更新过程解决堵塞，解决上述问题。

## 4.Elastic Network Virtualization

*University of Science and Technology of China*  
*Citations: 15*

这篇论文主要讨论了弹性网络虚拟化的问题。现有的网络虚拟化方法缺乏弹性，不适用于云计算环境。为解决这个问题，论文提出了一种新的嵌入方法，为租户的虚拟基础设施增加了弹性，使得虚拟网络的拓扑结构可以灵活改变。为此，论文引入了四个租户虚拟网络的原语，包括扩展和缩放，并提出了实现它们的新算法。主要挑战在于在最大化资源效率的同时，使这些新服务可用，而不影响服务质量。与进一步改进现有在线嵌入算法不同，本文采用了另一种方法，利用网络迁移进行嵌入过程，并为基础设施提供商引入了一种新的重构原语。。与现有技术相比，本文的解决方案提高了网络效率，同时将迁移足迹减少了至少一个数量级。

## 5.Incremental Server Deployment for Scalable NFV-enabled Networks

这篇论文研究了可扩展的网络功能虚拟化（NFV）网络的增量服务器部署问题。为了构建新的NFV网络，有两个关键要求：最小化服务器部署成本和满足交换机资源限制。然而，以前的工作主要关注服务器部署成本，而忽略了交换机资源限制（例如，交换机的flow table大小）。这导致交换机上有很多规则，从而产生大量的控制开销。为了解决这个问题，作者提出了一个用于构建可扩展NFV网络的增量服务器部署（INSD）问题。他们证明了INSD问题是NP-hard的，并且不存在具有近似比为(1-ε)·ln m的多项式时间算法，其中ε是一个任意的较小值，m是网络中的请求数量。然后，他们提出了一种高效的算法。作者在物理平台（Pica8）、Open vSwitches和大规模仿真中评估了算法的性能。实验和仿真结果均表明，所提出的算法具有较高的可扩展性。

## ***6.Inferring Firewall Rules by Cache Side-channel Analysis in Network Function Virtualization***

*Kwangwoon University，Hansung University，Korea University*
*Citations: 3*

在 NFV 架构中，CPU 缓存被共享在各个虚拟机之间，因此，一个与虚拟机共享的 VM 可以查看转发和过滤的内部过程。缓存旁路分析导致敏感的网络功能信息泄露给未经授权的用户，对安全性造成严重影响。虽然 NFV 中的安全挑战已有很多研究，但从未研究过缓存旁路威胁对虚拟化网络功能的影响。在本文中，研究了缓存旁路攻击对 NFV 应用的安全影响，并实现了基于缓存的虚拟防火墙策略扫描。防火墙策略扫描是一种网络扫描技术，用于学习防火墙的包过滤规则。作为网络入侵的初步步骤，这种技术对攻击者至关重要，因为它允许他们知道哪些类型的数据包（即 IP 地址、协议和端口号）可以经过防火墙。文特别研究了这些攻击对虚拟化网络功能的安全影响，提出了一种针对虚拟化基于Linux防火墙的基于缓存的侦察技术。该技术在攻击者的角度具有显著的优势，首先，它通过源地址伪造增强了对抗入侵检测的隐蔽性。其次，它允许推断各种过滤规则。在VyOS的实验中，该方法可以使用只有几十个数据包来推断防火墙规则，准确率超过90%。此外，论文还提出了针对虚拟化网络功能上缓存基攻击的缓解措施。

## 7.Latency-aware VNF Chain Deployment with Efficient Resource Reuse at Network Edge

本篇论文研究了在网络边缘低延迟网络服务需求不断增长的情况下，如何有效地在网络边缘部署虚拟网络功能（VNF）链路并实现资源的高效利用。移动边缘计算（MEC）作为一种新兴的计算范式，通过在网络边缘提供服务器资源和处理能力，以满足低延迟网络服务的需求。基于网络功能虚拟化（NFV），网络服务可以作为虚拟网络功能（VNF）链路在边缘服务器上进行灵活部署。然而，由于网络边缘的资源短缺，如何在有限的延迟条件下，实现VNF链路的有效部署和资源高效利用仍然是一个具有挑战性的问题。
在这篇论文中，作者关注于在延迟限制下优化边缘服务器和物理链路的资源利用率。具体来说，作者将VNF链路部署问题形式化为一个混合整数线性规划（MILP）问题，以最小化总资源消耗。作者设计了一个新颖的两阶段延迟感知VNF部署方案：以约束深度优先搜索算法（CDFSA）选择路径，以基于路径的贪婪算法（PGA）分配VNF，尽可能地重用现有VNF。作者证明，所提出的算法可以有效地实现近似最优解，具有理论证明的最坏情况性能边界。大量仿真结果表明，所提出的算法优于三种先前的启发式算法。

## 8.Network Slicing in Heterogeneous Software-defined RANs

这篇论文探讨了异构软件定义无线接入网络（RAN）中的网络切片技术。5G技术需要将将资源利用推向极限。除了更好的容量外，本文还需要通过虚拟化实现更好的资源管理。端到端的网络切片不仅涉及核心网络，还涉及无线接入网（RAN），这使得解决这个问题具有挑战性。这是因为存在多种可选的无线接入技术（例如，LTE，WLAN和WiMAX），并且没有统一的抽象来比较和组合不同的技术。此外，现有工作假设所有RAN基础设施都存在于单个管理域内。软件定义无线接入网（SD-RAN）提供了可编程性，促进了多个提供商之间资源共享和组合的统一抽象。在本文中，本文提出了一个跨越多个提供商的异构RAN切片的新的架构。本文架构的一个核心组件是一个服务编排器，它与多个网络提供商和服务提供商互动，以协商资源分配，这些资源分配是共同最优的。本文提出了一个双重拍卖机制，捕捉自私各方之间的互动，并保证在有限时间内收敛到最优社会福利。然后，本文通过使用开源SD-RAN系统（如EmPOWER（WiFi）和FlexRAN（LTE））来证明本文提出的系统的可行性。

## 9.SDN-based Order-aware Live Migration of Virtual Machines

这篇论文提出了一种基于SDN的有序实时迁移虚拟机的方法。实时迁移是将在一台服务器上运行的虚拟机（VM）转移到另一台服务器的关键技术。通常，在服务器维护、负载均衡和即将发生的故障等事件发生时，需要迁移多个虚拟机。然而，虚拟机迁移是一项资源密集型的操作，会对源主机和目标主机的CPU、内存和网络资源以及中间网络链路造成压力。实时迁移机制与需要迁移的虚拟机竞争有限的资源，从而延长了总迁移时间，并降低了运行在虚拟机内部的 applications 的性能。本文提出了SOLive，一种新的方法来减少迁移过程和正在迁移的虚拟机之间的资源竞争。首先，通过考虑虚拟机工作负载的特性，SOLive管理多个虚拟机的迁移顺序，以显著减少总迁移时间。其次，为了减少迁移过程和虚拟机之间的网络竞争，SOLive使用基于软件定义网络的资源预留和基于 scatter gather 的虚拟机迁移来快速从源主机中释放资源。在KVM/QEMU平台上的原型实现表明，SOLive可以快速将虚拟机从源主机中驱逐，对虚拟机性能的影响很小。

## 10.Bandwidth Isolation Guarantee for SDN Virtual Networks

这篇论文介绍了TeaVisor，为软件定义网络（SDN）基础的网络虚拟化（NV）提供了带宽隔离保证。SDN-NV提供拓扑和地址虚拟化，同时允许虚拟网络的灵活资源配置、控制和监控。然而，带宽隔离保证在SDN-NV中缺失，这对于提供稳定可靠的网络服务至关重要。没有带宽隔离保证，租户会遭受服务质量和收入损失。在SDN-NV中，路由由租户执行，而现有的研究没有解决过载链路问题。为解决这个问题，TeaVisor设计了三个组件：路径虚拟化、带宽预留和路径建立。通过这些，TeaVisor实现了带宽隔离保证，同时保留了租户的路由。此外，TeaVisor同时保证最小和最大带宽。本文完全实现了TeaVisor，全面的评估结果显示，在实现带宽隔离保证方面接近零错误率。本文还对控制流量和内存消耗进行了开销分析。

## 11.Expectile Tensor Completion to Recover Skewed Network Monitoring Data

这篇论文研究了在网络监控数据严重偏斜且尾部沉重的分布情况下，如何利用期望值张量补全方法来恢复缺失的数据。网络应用，如网络状态跟踪、预测、异常检测和故障恢复等都需要完整的网络监控数据。然而，由于使用部分测量和传输过程中无法避免的数据丢失，监控数据往往是 incomplete 的。张量补全方法最近引起了人们的关注，因为它可以利用多维数据结构进行更准确的不测量/缺失数据推理。尽管传统的张量补全算法在应用数据符合对称正态分布时可以正常工作，但它无法很好地处理严重偏斜且尾部沉重的网络监控数据。为了更好地跟随数据分布，以更准确地恢复具有大值的缺失条目，本文提出了一种新颖的期望值张量补全（ETC）公式和一个简单但高效的张量补全算法，无需硬设定参数以方便实现。从实验和理论两个方面，本文都证明了所提出的算法的收敛性。在两个真实的网络监控数据集上的大量实验证明了所提出的 ETC 的有效性。

## ***12.Robust Online Learning against Malicious Manipulation with Application to Network Flow Classification***

*University of Toronto*
*Citations: 2*

网络流量分类是现代网络管理的关键，机器学习方法对其成功依赖于可靠的知识流特征值。恶意网络流量生成器可能操纵其流量特征以欺骗分类器，例如优先获得网络资源分配或规避检测。为了应对机器学习系统的攻击，其他文章提出了对抗性学习（adversarial learning）的防御策略，大多数是离线策略。然而，在许多应用中，训练数据是生成的（例如，计算机网络中的流量），因此在线学习通常更具有吸引力。由于恶意数据生成者可以操纵数据特征以最好地响应分类器最新的分类模型，因此定期更新分类器对于应对这些恶意攻击很重要。 本文提出两种在线分类算法，用于处理网络流量分类问题。

## 13.Safety Critical Networks using Commodity SDNs

这篇论文研究了使用商品软件定义网络（SDN）实现安全关键网络的方法。安全关键网络通常具有严格的实时要求，并且必须对故障具有弹性。在论文中，作者提出了RealFlow框架，该框架利用商品SDN实现具有端到端时间保证的网络，同时：1）增加对链路/交换机故障的弹性；2）提高网络利用率。SDN在这个领域的使用也提高了系统的管理能力，因为全局网络可见性。RealFlow作为一个兼容标准OpenFlow协议的北向SDN控制器应用程序实现，运行时开销很小。作者在实际的硬件测试平台（Pica8 SDN开关+树莓派终端主机）和一个实用的航空电子案例研究中证明了RealFlow的可行性。评估结果显示，与当前设计相比，RealFlow可以容纳63%具有安全关键保证的网络流量，在考虑链路弹性（通过备用路径）时，可容纳多达18%的流量。

## 14.Self-Adaptive Sampling for Network Traffic Measurement

这篇论文研究了使用商品软件定义网络（SDN）实现安全关键网络的方法。安全关键网络通常具有严格的实时要求，并且必须对故障具有弹性。在论文中，作者提出了RealFlow框架，该框架利用商品SDN实现具有端到端时间保证的网络，同时：1）增加对链路/交换机故障的弹性；2）提高网络利用率。SDN在这个领域的使用也提高了系统的管理能力，因为全局网络可见性。RealFlow作为一个兼容标准OpenFlow协议的北向SDN控制器应用程序实现，运行时开销很小。作者在实际的硬件测试平台（Pica8 SDN开关+树莓派终端主机）和一个实用的航空电子案例研究中证明了RealFlow的可行性。评估结果显示，与当前设计相比，RealFlow可以容纳63%具有安全关键保证的网络流量，在考虑链路弹性（通过备用路径）时，可容纳多达18%的流量。

## ***15.FlowShark: Sampling for High Flow Visibility in SDNs***

*University of Calgary*  
*Citations: 0

这篇论文介绍了一种名为FlowShark的高流量可见性采样系统，用于软件定义网络（SDNs）。随着现代网络规模和速度的不断增长，流量采样已成为网络管理不可或缺的工具。尽管存在大量的采样解决方案，但它们在提供有限的流量可见性或在大型网络中具有较差的可扩展性。在FlowShark中，关键思想是将短期和长期流量的采样决策分开，其中短期流量的采样在边缘交换机上本地管理，而中央控制器优化长期流量的采样决策。为此，本文将流量采样表示为优化问题，并设计了一种具有有界竞争比的在线算法来有效地解决问题。为了展示设计的可行性，本文在一个小型OpenFlow网络中使用Mininet实现了FlowShark。本文的实验表明，与现有的采样方法相比，FlowShark可将基于机器学习的流量分类器的分类召回率提高27%和19%的精度。

## ***16.NMMF-Stream: A Fast and Accurate Stream-Processing Scheme for Network Monitoring Data Recovery***

*Hunan University,State University of New York at Stony Brook*  
*Citations: 0*

网络全面的性能监测引入了非常高的测量成本。为了降低测量成本，网络监控系统通常采用抽样机制，只测量源节点和目标节点的一小部分 OD 对。为了在单个时间槽内记录整个网络的端到端网络性能数据，建立一个矩阵，其中行表示源节点，列表示目标节点。本文称这样的矩阵为网络监控矩阵（NMM）。在抽样机制下，NMM 通常稀疏，只有少量已观测到的条目，而其余大部分条目是未知的。一些网络应用程序，如网络状态跟踪、预测和故障恢复，需要完整的网络监控数据，对数据缺失非常敏感。为了在低采样率下实现快速特征提取和缺失数据填充，本文提出了一些新颖的技术，包括基于正负监控数据的上下文提取、通过测量点间互信息进行上下文验证、基于GRU的时序特征学习和记忆以及一个新的复合损失函数以引导快速准确的数据填充。实验结果表明，NMMF-Stream可以快速且准确地填充新到达的监控数据。

## ***17.Short-Term Memory Sampling for Spread Measurement in High-Speed Networks***

*Soochow University*  
*Citations: 2*

在高速网络中进行每流传输扩散测量可以为许多实际应用提供不可或缺的信息。然而，在芯片内存模块无法同时提供大容量和大带宽的情况下，以线路速度测量数百万个流是具有挑战性的。先前的研究通过完全使用芯片紧凑数据结构或利用芯片外空间来协助有限的芯片内存来解决这种不匹配问题。然而，它们在芯片上的数据结构记录了大量的瞬时元素，其中每一个仅在长时间测量任务中的短时间间隔内出现，从而浪费了大量的芯片空间。文提出了一种名为短期记忆采样的新颖扩散估计器，该估计器在仅保持短期元素的同时采样新元素。本文的估计器可以使用微小的芯片空间，并为在线查询提供准确的估计。

## ***18.EScala: Timely Elastic Scaling of control channels in network measurement***

*Zhejiang University, Beijing University, Fuzhou University*  
*Citations: 2*

数据平面根据控制平面的配置和规则来处理数据包，而控制平面则通过配置数据平面的设备来定义网络的行为。二者相互协作。负责两者的通讯与协调的组件教控制通道。而本文的提出控制通道有两个问题：网络流量大时通道的过度负载，导致数据丢失以及应用层的准确性下降；网路流量小时的欠载，导致闲置信道占用物理资源造成能源浪费和效率下降。本问提出的Escala可以通过迁移多个信道中的事件流来提供弹性控制信道扩展。Escala由一个监视器和一个优化框架组成。监视器可以收集数据并基于此分析扩展情况。而优化框架则是做出扩展决定。Escala最后在真是的testbed上测试后，比现有的其他解决方案，在迁移事件流和执行时间上都有了很大的提升。