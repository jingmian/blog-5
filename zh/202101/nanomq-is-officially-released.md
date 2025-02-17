2021 年伊始，物联网开源基础软件领导者 EMQ 携手 NNG 为开源社区献上开年贺礼： **面向边缘计算和 5G MEC 的开源轻量级边缘 MQTT 消息引擎—— [NanoMQ](https://nanomq.io)**
NanoMQ 的正式问世填补了国产基础软件在此领域的空白，将与边缘流式数据处理软件 Kuiper、消息中间件 EMQX 和分布式流处理数据库 HStream 一起，形成 5G&IoT 的全场景消息与流处理和全栈解决方案。



## NNG & NanoMQ 合作

**[NNG](https://nng.nanomsg.org/)** 作为 **[Nanomsg](https://nanomsg.org/index.html)** 项目的衣钵传承者，是一个强大的消息总线库，支持 SP 协议和 HTTP/WebSocket 等拓展。在其优秀的多线程模型和网络层 API 基础上，NNG 提供了各种丰富的消息模式支持，在物联网、工业控制、游戏、金融交易等领域都有广泛应用。
EMQ 在项目早期就开始了对其的持续关注，发掘并优化了 NNG 的高效多线程模型。而后，EMQ 与 NNG 达成长期技术合作，将 NNG 作为底层消息总线打造了 NanoMQ。未来，EMQ 将依靠自己在 5G&IoT 领域深厚的开发经验和产品实施落地能力，帮助 NNG 集成更多泛用的物联网协议，拓宽其应用面。在 NanoMQ 项目合作的同时，也将通过开源社区技术反哺 NNG 项目，为其提供 MQTT 协议支持，使其可以作为一个性能优秀的 [MQTT SDK](https://www.emqx.com/zh/mqtt-client-sdk) 使用。 

![logo.png](https://assets.emqx.com/images/52ed45dd2467e5ee1db6c4279c8f3261.png)

## NanoMQ 项目概述

NanoMQ 项目致力于交付实现适用于现代 IoT 和嵌入式平台的超轻量 MQTT 消息引擎，通过高效的内部 IPC 能力，弥合边缘硬件和云端的架构差异，连接物理世界与数字智能。接棒 EMQX Edge，赋予边缘消息汇聚再分发能力，进而为边缘计算应用开发提供便利。

NanoMQ 分为 3 个部分：

1. **nanolib**：主要提供边缘数据缓存、MQTT 订阅关系存储和消息路由能力。
2. **nanomq**：是一系列工具和服务的入口，其中消息引擎（Broker）功能是其主要功能，管理所有连接，负责提供如状态通知、钩子函数等功能。目前还有消息队列 mq 功能。
3. **nanonng**：是基于 NNG 优化的可用于 [MQTT 协议](https://www.emqx.com/zh/mqtt-guide)的多线程模型和异步 IO 库。

![产品图.png](https://assets.emqx.com/images/d29c92307e8a830de317e8c2fd460eab.png)



## NanoMQ 优势特点

- **超轻量**：安装包约 200KB 左右；不依赖于第三方的库与运行时，运行占用资源极小，根据编译和启动的配置，启动所需资源从 300Kb - 3Mb 不等。 
- **多兼容&可移植**：NanoMQ 采用纯净 C/C++ 开发，只依赖于标准 POSIX API，具有绝佳的兼容性和可移植性，大小端兼容，无缝对接各类网络应用，可 0 成本迁移到各类嵌入式平台。
- **可伸缩**：得益于内置的异步 IO 架构和多线程模型，在做到轻量化的同时仍具备一定可横向拓展的并发吞吐能力。可以不到 10MB 的内存消耗支持超过10W 的消息吞吐。
- **易调试**：可以自行配置日志开关和级别，有完整的调试接口和日志接口，与syslog 标准兼容。方便进行边缘端的故障排查和追踪。
- **SMP 支持**： 在边缘多核平台上，对 SMP 有良好支持，能够尽可能发挥多处理器能力。
- **容器支持**：可以通过容器进行部署运行。兼容主流边缘容器编排方案。



## NanoMQ 发展规划

目前 NanoMQ 完整支持 MQTT 3.1.1 协议，部分支持 [MQTT 5.0](https://www.emqx.com/zh/blog/introduction-to-mqtt-5) 协议。下一版本的规划中，还将具有边缘 MQTT 分布式桥接、嵌入式规则引擎和边缘消息缓存等功能。
未来 EMQ 将与 NNG 一同集成支持包括 ZMQ、MQTT 等在内的更多常用 IoT 协议支持，优化多线程模型，提高吞吐，完善网络 IPC 能力。使广大开发者告别繁杂的 SDK 集成，获得一站式物联网开发体验，探索消息引擎在边缘计算领域的更广泛应用，加速各类边缘计算应用的开发和落地。
同时 NanoMQ 还将集成 NNG 已有的 SP 协议，提高与 NNG 的开源协同配合度，实现底层 API 互相兼容。

![架构图.png](https://assets.emqx.com/images/c40f88d0449f2152b862cf3af9c92195.png)

## NanoMQ 在边缘计算中的应用

在边缘端并非所有的消息数据都需要上云，需要有极强的边缘自治和业务自洽能力，因此一个边缘消息引擎必不可少。同时，物联网边缘计算的应用部署受嵌入式环境资源有限、硬件对成本敏感等因素限制，大多采用高性价比的解决方案和硬件平台，如 OpenWRT 等精简的类 Linux 构建系统。面对以上情况和实际需求， **NanoMQ 可以说是未来边缘计算的最佳选择。**
随着技术进步和时间推移，边缘计算平台芯片算力将逐步提高并向多核化发展。对于 MEC 平台和边缘的核心网关场景，NanoMQ 的多线程能力也可以完美转换，发挥出强大的吞吐能力，成为边缘应用之间的消息路由，承担内容中转、聚合再分发的任务。



## NanoMQ 开源项目与社区

用户可以参考 NanoMQ 的 Github 和 wiki 文档来单独试用 NanoMQ，也可以 **配合 EMQ 已发布的其它边缘计算产品形成一套完整高效的解决方案：**

- 将各类传感器数据利用工业协议接入软件 Neuron 采集，并转换为标准 MQTT 协议；
- 利用 NanoMQ 汇聚来自于 Neuron 的 MQTT 工业数据；
- 利用边缘流式数据处理软件 Kuiper 对工业数据进行实时分析，结果将由 Kuiper 汇聚至 NanoMQ 中进行归集聚合和再分发
- NanoMQ 将其最终传回云端 EMQX 后进行持久化，从而满足各类上层应用的开发需要。

NanoMQ 后续将与 [EMQ 边缘管理套件](https://github.com/emqx/edge-stack)进行集成，为用户提供更好的使用体验。
NanoMQ 基于 MIT 开源协议，后续将与 CNCF 以及 Linux LF 基金会等项目进行合作，真诚欢迎社区各方的建议和帮助。


<section class="promotion">
    <div>
        免费试用 NanoMQ
    </div>
    <a href="https://www.emqx.com/zh/try?product=nanomq" class="button is-gradient px-5">开始试用 →</a >
</section>
