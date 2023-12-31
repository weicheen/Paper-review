# INFOCOM 

## 1.Network Monitoring for SDN Virtual Networks  

*Department of computer science and engineering, Korea University*  
*Citations: 14*

The scenario mentioned in this paper is SDN-NV, which is virtualized SDN. in this network architecture is shown in the following figure.

![image](https://github.com/weicheen/Paper-review/blob/master/infocom/2020/asset/1.png)

Network hypervisor is a good tool for network management and optimization under SDN-VN framework. However, existing NHs do not provide network traffic monitoring capabilities, such that the traditional approach to network monitoring under SDN-VN has three drawbacks:

+ Inaccurate network statistics (statistics are aggregated across multiple VNs running on the network and there is no mechanism to retrieve and isolate these statistics from the VNs)
+ The SDN-NV architecture undoubtedly increases the latency (transmission delay) of statistics information requests between the controller and the switch. When a statistics request message is transmitted from the controller to the NH, the NH must send the corresponding network statistics request message to the physical network (switch) and wait for the result to be received.*
+ *The NH over-consumes control channel traffic relative to non-virtualized SDNs to affect other traffic. the NH must send multiple messages to multiple switches in response to requests from the controller.

In this paper, we propose a new network monitoring framework v-sight with the following architecture:

![image](https://github.com/weicheen/Paper-review/blob/master/infocom/2020/asset/3.png)

V-sight solves the above three problems by:
- Isolated virtual network data is computed from physical network data through Stastistics virtualization.
- pController routinely collects switch statistics and stores them in the VH to reduce latency in data transmission.
- The pController replaces multiple requests with a single request to reduce control information traffic. 

From all perspectives, V-sight greatly improves the efficiency and accuracy of network ground monitoring.
---

## 2.Towards Latency Optimization in Hybrid Service Function Chain Composition and Embedding

*Department of Computer Science, Georgia State University, USA*  
*Citations: 36*

In this paper, they comprehensively study and propose the Hybrid SFC Construction and Embedding (HSFCE) problem, where the ordinary SFCE problem needs to consider the composition of SFCs, the mapping of SF nodes to the physical network, and the mapping of SF links. The HSFCE problem, on the other hand, is how to deploy NFs in a hybrid physical and virtualized manner and embed them into the network topology. In this paper, two algorithms are proposed to optimize the delay of the network based on different physical node-VNF correspondences: BC-HSFP and EC-HSFP. where EC-HSFP is used in the case when there is one VNF on one node, and it is used as a 2-fold approximation algorithm for such an np-hard problem. While BC-HSFP is proposed as a heuristic algorithm corresponding to the case when there are multiple VNFs on a node. Both greatly improve the performance of the network and reduce the delay.

SFCs that require different groups in the forward and reverse directions are called hybrid SFCs (h-SFCs). The following figure shows an example of h-SFC for online machine learning. The SFC in the forward direction should be Source→A→B→DEST, while the reverse direction is DEST→D→C→B→A→Source.To save Operating Expense (OPEX) and latency, the sf required in both directions are usually installed on nodes in the same physical network.

![image](https://github.com/weicheen/Paper-review/blob/master/infocom/2020/asset/4.png)

---

## 3.Coeus: Consistent and Continuous Network Update in Software-Defined Networks

*Yale University, Nanjing University, Lancaster University*  
*Citations: 8*

Updates in the network are usually executed only after the completion of a single update. The high frequency of changes and the large number of events processed in today's network environments have led to high latency as well as low performance of the network in this regular update method, triggering problems such as blackhole, loop, and congestion. And a continuously optimized network can solve these problems. The Coeus model proposed in this paper builds on Update Algebra to continuously update and optimize the network. To this end, this paper is mainly based on the proposed dynamic operation dependency graph to dynamically reconstruct the operation graph to capture unexecuted update operations, operation composition to eliminate redundant commands, and operation node partition Algo to accelerate the update process to solve the congestion to solve the above problems.

The experiments in this paper are done through ***large-scale simulation***. Using two common topologies (i.e., SWAN and fat-tree), the effectiveness of Coeus is verified by constantly changing the arrival rate of update events.

---

## ***4.EScala: Timely Elastic Scaling of control channels in network measurement***

*University of Science and Technology of China*  
*Citations: 15*

This paper focuses on virtualization of elastic networks. The control plane defines network behavior by configuring data plane devices. But there are usually two problems: overload when traffic is high and underload when traffic is low. The simple solution to control channel overload is to open several channels, but this means opening more ports than necessary resulting in a drop in total throughput. Underloading, on the other hand, allows idle channels to consume network resources for nothing. Existing approaches to network virtualization are inelastic and not applicable to cloud computing environments.
To solve this problem, the core approach is to regulate the channel load by migrating the event flow in the channel. For this purpose this paper proposes Escala that contains a monitor to collect data with scaling scenarios and an optimization framework to make choices. The solution in this paper improves network efficiency while reducing the migration footprint by at least an order of magnitude compared to state-of-the-art.


In this paper, a large-scale wide area network (WAN), Internet2 [1] (42 switches and 53 links), is simulated. The WAN switches and links are set up as follows:(1) each switch has 32 100 gbps ports connected to the control plane through a 100 gbps control channel; (2) each switch transmits each packet within 1 µs; (3) the load of each switch is randomly distributed between 20 Gbps ~ 80 Gbps; (4) the load of each link is 10 Gbps ~ 30 Gbps; (5) the delay of each link is randomly distributed between 1 ms ~ 10 ms; and (5) each control channel transmits at least 20 concurrent event streams. We set the deadline Φs for collecting events to be randomly distributed between 30 ms and 80 ms.

+ (1) Each switch has 32 100gbps ports connected to the control plane via a 100gbps control channel;
+ (2) Each switch transmits each packet within 1 µs; + (3) Each switch is loaded at 20 Gbps.
+ (3) Each switch's load is randomly distributed between 20 Gbps ~ 80 Gbps; + (4) Each switch is connected to the control plane via a 100gbps control channel.
+ (5) Each link delay is randomly distributed between 1 ms ~ 10 ms; + (6) Each link load is randomly distributed between 10 Gbps ~ 30 Gbps
+ (6) Each control channel transmits at least 20 concurrent event streams. We set the deadline Φs for collecting events to be randomly distributed between 30 ms and 80 ms.

![image](https://github.com/weicheen/Paper-review/blob/master/infocom/2020/asset/5.png)

**[1]https://www.glif.is/meetings/2006/plenary/summerhill-internet2.pdf**

---

## 5.Incremental Server Deployment for Scalable NFV-enabled Networks

This paper investigates the incremental server deployment problem for scalable NFV networks. In order to build new NFV networks, there are two key requirements: minimizing server deployment cost and meeting switch resource constraints. However, previous work focuses on server deployment cost and ignores switch resource constraints (e.g., switch flow table size). This leads to a lot of rules on the switches, which incurs a lot of control overhead. To address this problem, the authors present an Incremental Server Deployment (INSD) problem for building scalable NFV networks. They prove that the INSD problem is NP-hard and that there exists no polynomial-time algorithm with an approximation ratio of (1 - ε) - ln m, where ε is an arbitrarily small value and m is the number of requests in the network. They then propose an efficient algorithm. The authors evaluated the performance of the algorithm in a physical platform (Pica8), Open vSwitches and large-scale simulations. Both experimental and simulation results show that the proposed algorithm is highly scalable.

---

## ***6.Inferring Firewall Rules by Cache Side-channel Analysis in Network Function Virtualization***

*Kwangwoon University，Hansung University，Korea University*
*Citations: 3*

In the NFV architecture, CPU caches are shared among VMs, so a VM that shares CPU resources with another VM can be analyzed by a resource measurement channel in order to view the internal process of forwarding and filtering. Cache Measurement Channel Analysis leads to leakage of sensitive network function information to unauthorized users, which has serious security implications. Although there have been many studies on security challenges in NFV, the impact of cache bypass threats on virtualized network functions has never been studied. In this paper, the security impact of cache bypass attacks on NFV applications is investigated and cache-based virtual firewall policy scanning is implemented. Firewall policy scanning is a network scanning technique used to learn the packet filtering rules of a firewall. As a preliminary step to network intrusion, this technique allows them to know what types of packets (i.e., IP addresses, protocols, and port numbers) can pass through the firewall. In particular, the paper investigates the security implications of these attacks on virtualized network functions and proposes a cache-based reconnaissance technique for virtualized Linux-based firewalls. First, it enhances stealth against intrusion detection through source address forgery. Second, it permits the inference of various filtering rules. In experiments with VyOS, the method can infer firewall rules using only a few dozens of packets with over 90% accuracy. In addition, the paper proposes mitigations against cache-based attacks on virtualized network functions.

The experimental architecture of the paper is two virtual machines on the same host. One acts as the attacker and one acts as the attacked. A VNF, such as a firewall, is placed on the attacked. The attacker sends packets to the victim and speculates on the operation and rules of the firewall on the victim by observing the cache.

---

## ***7.Short-Term Memory Sampling for Spread Measurement in High-Speed Networks***

*Soochow University*  
*Citations: 2*

Flow transmission diffusion measurements in high-speed networks can provide indispensable information for many practical applications. However, it is challenging to measure millions of streams at line speeds when chip memory modules cannot provide both large capacity and large bandwidth. Previous studies have addressed this mismatch by either using the chip's compact data structures exclusively or utilizing off-chip space to assist with the limited chip memory. However, their on-chip data structures record a large number of transient elements, each of which occurs only at short intervals during long measurement tasks, thus wasting a large amount of chip space. 

The paper proposes a novel diffusion estimator called ***short-term memory sampling***, which samples new elements while maintaining only short-term elements. The estimator in this paper can use tiny chip space and provide accurate estimates for online queries.


## 8.Elastic Network Virtualization

*Lisboa University*  
*Citations: 2*

This paper focuses on elastic network virtualization. Existing network virtualization approaches lack elasticity and are not applicable to cloud computing environments. To address this problem, the thesis proposes a new embedding approach that adds elasticity to a tenant's virtual infrastructure, allowing the topology of the virtual network to be changed flexibly. For this purpose, the paper introduces four tenant virtual network primitives, scale in, scale out, scale down, scale up,and proposes new algorithms to realize them. The main challenge is to make these new services available while maximizing resource efficiency without compromising the quality of service. Since migration cause network fluctuations, the solution in this paper cautiously uses this technique to limit the impact on running services. Compared to existing techniques, the solution in this paper improves network efficiency while reducing the migration footprint by at least an order of magnitude.

The following figure demonstrates the entire system, centered on their contribution. The current state of network virtualization is shown in white, and their extensions are shown in green.The Use API has been extended to allow users to not only create and destroy virtual networks, but also to rescale them. This process can be done on-demand or automatically triggered by the user's pre-configured VN monitor (e.g., the VN can be scaled in a pre-configured manner when a customer request exceeds a certain threshold). The VN request is then embedded using ElasticVNE, resulting in a mapping of the virtual network to the substrate network. The provider can also intervene to trigger reconfiguration (on-demand or by monitoring key metrics such as average path length). After defining the mappings, the system will implement them in the substrate.

![Alt text](./infocom/2020/asset/image.png)


## 9.SDN-based Order-aware Live Migration of Virtual Machines

This paper proposes an SDN-based approach for orderly live migration of virtual machines. Live migration is a key technique for moving VMs running on one server to another server. Typically, multiple VMs need to be migrated when events such as server maintenance, load balancing, and impending failures occur. However, VM migration is a resource-intensive operation that puts pressure on CPU, memory, and network resources of the source and target hosts, as well as intermediate network links. Live migration mechanisms compete for limited resources with the VMs that need to be migrated, which prolongs the total migration time and degrades the performance of applications running inside the VMs. In this paper, we propose SOLive, a new approach to reduce the resource competition between the migration process and the VMs being migrated. First, by taking into account the characteristics of the VM workload, SOLive manages the migration order of multiple VMs to significantly reduce the total migration time. Second, to reduce the migration process and network contention between VMs, SOLive uses software-defined network-based resource reservation and scatter gather-based VM migration to quickly release resources from the source host. A prototype implementation on the KVM/QEMU platform shows that SOLive can quickly evict VMs from the source host with minimal impact on VM performance.

## 10.Bandwidth Isolation Guarantee for SDN Virtual Networks

This paper introduces TeaVisor, which provides bandwidth isolation guarantees for network virtualization underlying SDN.SDN-NV provides topology and address virtualization while allowing flexible resource provisioning, control, and monitoring of virtual networks. However, bandwidth isolation guarantees are missing in SDN-NV, which is critical for providing stable and reliable network services. Without bandwidth isolation guarantees, tenants suffer from quality of service and revenue loss. In SDN-NV, routing is performed by tenants, and existing research has not addressed the problem of overloaded links. To address this problem, TeaVisor designs three components: path virtualization, bandwidth reservation, and path establishment. With these, TeaVisor achieves bandwidth isolation guarantees while preserving tenants' routes. In addition, TeaVisor guarantees both minimum and maximum bandwidth. This paper fully implements TeaVisor, and a comprehensive evaluation shows near-zero error rates in achieving bandwidth isolation guarantees. This paper also analyzes the overhead of control traffic and memory consumption.

## 11.Expectile Tensor Completion to Recover Skewed Network Monitoring Data

This paper investigates how the missing data can be recovered using the expectation value tensor complementation method in the case of heavily skewed and tail-heavy distribution of network monitoring data. Network applications such as network state tracking, prediction, anomaly detection and fault recovery require complete network monitoring data. However, monitoring data is often incomplete due to the use of partial measurements and unavoidable data loss during transmission. Tensor-completion methods have recently attracted attention because they can utilize multidimensional data structures for more accurate inference of unmeasured/missing data. Although the traditional tensor complementation algorithm works well when the applied data conforms to a symmetric normal distribution, it does not handle heavily skewed and tail-heavy network monitoring data well. To better follow the data distribution in order to recover missing entries with large values more accurately, this paper proposes a novel expectation tensor complementation (ETC) formulation and a simple but efficient tensor complementation algorithm that does not need to be hardwired with parameters for easy implementation. Both experimentally and theoretically, this paper demonstrates the convergence of the proposed algorithm. Extensive experiments on two real network monitoring datasets demonstrate the effectiveness of the proposed ETC.

## ***12.Robust Online Learning against Malicious Manipulation with Application to Network Flow Classification***

*University of Toronto*
*Citations: 2*

Network traffic classification is key to modern network management, and machine learning methods rely on reliable knowledge of flow feature values for its success. Malicious network traffic generators may manipulate their traffic features to deceive classifiers, e.g., by prioritizing network resource allocations or bypassing detection. To cope with attacks on machine learning systems, other papers have proposed defense strategies for adversarial learning (AL), mostly offline strategies. However, in many applications, training data is generated (e.g., traffic in a computer network), so online learning is often more attractive. Since malicious data generators can manipulate data features to best respond to the classifier's latest classification model, regular updates of the classifier are important to counter these malicious attacks. In this paper, we propose two online classification algorithms for dealing with the problem of network traffic classification.

## 13.Safety Critical Networks using Commodity SDNs

Network flows in safety-critical systems often have stringent timing and performance constraints often referred to as RealTime (RT) requirements. They must also be resilient to failures. In this paper, we propose the RealFlow framework that uses commodity SDNs to realize networks with end-to-end timing guarantees, while also increasing resiliency against link/switch failures and increasing network utilization.   They firstly present a new static path allocation algorithm that can multiplex RT flows onto the same queues while still meeting the end-to-end delay and bandwidth requirements and also develop algorithms and mechanisms to pre-compute and deploy backup paths for critical flows to increase system resiliency in the presence of link failures.

The authors demonstrated the feasibility of RealFlow in a real-world hardware testbed (Pica8 SDN switch + Raspberry Pi end host) and a practical avionics case study. Evaluations show that RealFlow can accommodate 63% of network traffic with safety-critical guarantees compared to current designs, and up to 18% when link resiliency (via alternate paths) is considered.

## 14.Self-Adaptive Sampling for Network Traffic Measurement




## ***15.FlowShark: Sampling for High Flow Visibility in SDNs***

*University of Calgary*  
*Citations: 0

This paper describes a high traffic visibility sampling system called FlowShark for SDN. As modern networks continue to grow in size and speed, traffic sampling has become an indispensable tool for network management. While a large number of sampling solutions exist, they provide limited traffic visibility or have poor scalability in large networks. In FlowShark, the key idea is to separate the sampling decisions for short-term and long-term traffic, where the sampling of short-term traffic is managed locally at the edge switches, while a central controller optimizes the sampling decisions for long-term traffic. To this end, this paper represents traffic sampling as an optimization problem and designs an online algorithm with a bounded competitive ratio to solve the problem efficiently. To demonstrate the feasibility of the design, this paper implements FlowShark using Mininet in a small OpenFlow network.The experiments in this paper show that FlowShark improves the classification recall of a machine learning-based traffic classifier by 27% and 19% precision compared to existing sampling methods.hine learning-based traffic classifier by 27% and 19% precision compared to existing sampling methods.

## ***16.NMMF-Stream: A Fast and Accurate Stream-Processing Scheme for Network Monitoring Data Recovery***

*Hunan University,State University of New York at Stony Brook*  
*Citations: 0*

Comprehensive performance monitoring of networks introduces a very high measurement cost. In order to reduce the measurement cost, network monitoring systems usually employ a sampling mechanism where only a small fraction of OD pairs of source and target nodes are measured. In order to record end-to-end network performance data for the entire network in a single time slot, a matrix is created where the rows denote the source nodes and the columns denote the target nodes. In this paper, we call such a matrix a network monitoring matrix (NMM). Under the sampling mechanism, the NMM is usually sparse, with only a small number of observed entries, while most of the remaining entries are unknown. Some network applications, such as network state tracking, prediction and fault recovery, require complete network monitoring data and are very sensitive to missing data. In order to achieve fast feature extraction and missing data filling at low sampling rates, this paper proposes some novel techniques, including context extraction based on positive and negative monitoring data, context validation through mutual information between measurement points, GRU-based temporal feature learning and memorization, and a new composite loss function to guide fast and accurate data filling. Experimental results show that NMMF-Stream can populate newly arrived surveillance data quickly and accurately.

