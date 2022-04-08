# SkyForm AIP (Application Intelligent Placer) 高性能和高通量计算任务调度系统
SkyForm AIP是北京天云融创软件自主研发的高性能计算（HPC）和高通量计算（HTC）任务调度系统，有支持数万个节点的集群、每小时百万任务通量调度的能力。

SkyForm AIP在众多公共和企业的超算生产环境中得到使用，具有强大的容错、稳定、可靠、安装简单、使用免维护、应用兼容性强等特色，
适用于任何行业的高性能计算和高性能数据分析应用场景。

SkyForm AIP具有以下主要功能：
- 自动检测节点上的CPU、GPU、内存、存储、网卡等资源
- 支持英伟达A100 MIG调度
- 支持Docker容器作业和Apptainer(Singularity) MPI容器作业
- 提供MPI远程任务分发机制和监控功能，调度和运行MPI作业无需设置免密ssh
- 支持分布式AI和数据分析框架，如JupyterLab、TensorFlow等多CPU、多节点并行作业
- 丰富的调度策略：优先级、抢占、负载阈值、公平分享
- 异构资源拓扑作业的调度：如一个分布式作业包含 1个1GPU的任务1GPU + 2个1 CPU的任务 1 CPU +5个1 CPU和1 GPU的任务
- 可配置任务资源使用控制：时长、CPU和绑定、内存总量、GPU使用与调度分配的不符的等
- 支持所有国产芯片和操作系统
- 利用灵活的“资源传感器”自动检测特殊资源，以用于调度，如FPGA、各种协处理器
- 支持国际通用调度器的常用命令行：SLURM、PBS、LSF
- 对接多个已有HPC集群，平衡多个集群间的负载
- 提供REST API，便于第三方集成

# SkyForm AIP版本

|                                           | SkyForm AIP快捷版 | SkyForm AIP企业版    |
|-------------------------------------------|-------------------|----------------------|
| 大机群支持                                | 支持              | 支持                 |
| 高性能、高通量调度                        | 支持              | 支持                 |
| GPU调度                                   | 支持              | 支持                 |
| Docker和Apptainer作业                     | 支持              | 支持                 |
| 不依赖ssh的MPI深度集成                    | 支持              | 支持                 |
| 优先级调度                                | 支持              | 支持                 |
| 分布式AI框架支持                          | 支持              | 支持                 |
| 异构资源拓扑作业的调度                    | 支持              | 支持                 |
| FPGA、各种协处理器外插资源传感器          | 支持              | 支持                 |
| 支持国际通用调度器的常用命令行            | 支持              | 支持                 |
| REST API                                  | 支持              | 支持                 |
| 公有云弹性集群                            | 支持              | 支持                 |
| 高级调度功能：抢占、负载阈值、公平分享等  |                   | 支持                 |
| 可配置任务资源使用控制                    |                   | 支持                 |
| ARM、申威、龙芯CPU                        |                   | 支持                 |
| 对接多个已有HPC集群，平衡多个集群间的负载 |                   | 支持                 |
| 与SkyForm应用平台对接                     |                   | 支持                 |
| Windows支持                               |                   | 支持                 |
| 第三方OEM                                 |                   | 支持                 |
| 节电调度                                  |                   | 支持                 |
| 技术支持                                  | 社区              | 天云融创软件专业服务 |
| 软件获得                                  | 免费下载          | [联系天云融创软件](http://www.skycloudsoftware.com/index.php/contact)    |

# 下载
[稳定版](http://skyformaip.com/skyformaip-9.22.1.tar.gz)

# 文档
- [快速安装指南](https://github.com/skyformaip/skyformaip/blob/main/INSTALL.md)
- [wiki](https://github.com/skyformaip/skyformaip/wiki)

# 论坛
[用户问题讨论、信息分享](https://github.com/skyformaip/skyformaip/discussions)

# 许可证
- [天云融创软件许可证](https://github.com/skyformaip/skyformaip/blob/main/license.md)
- [第三方组件许可证](https://github.com/skyformaip/skyformaip/blob/main/thirdpartylicenses.md)
