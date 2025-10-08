# 知识点汇总（Week1–11）/ Bilingual Key Points

根据目录中材料自动汇总。每周包含知识点、记忆点与练习题。

**Week 1 | 第1周 — Cloud Basics and Models / 双语要点**
- Files 文件: W1-L2.pdf, Week1-L1.pdf
- 知识点 Knowledge Points:
  - EN: Cloud computing models: IaaS, PaaS, SaaS
  - CN: 云计算模型：IaaS、PaaS、SaaS
  - EN: Benefits: elasticity, on-demand, pay-as-you-go
  - CN: 优势：弹性、按需、按量付费
  - EN: Shared responsibility model (intro)
  - CN: 共享责任模型（入门）
  - EN: Core services overview: compute, storage, network
  - CN: 核心服务概览：计算、存储、网络
- 材料摘录 Highlights:
  - EN: Secure Cloud Application Engineering
  - CN: Secure Cloud Application Engineering
  - EN: CLOUD COMPUTING?
  - CN: 云计算
- 记忆点 Memory Hooks:
  - Cloud computing models
  - Benefits
  - Shared responsibility model (intro)
  - Core services overview
  - Secure Cloud Application Engineering
  - CLOUD COMPUTING?
-

Week2 

Amazon Web Services (AWS)
AWS是什么：

IT基础设施服务和资源的集合
由亚马逊提供
公开通过互联网按需提供
可扩展性强
按使用量付费
成立于2006年，最初为扩展亚马逊电商网站而设计
在所有云计算服务提供商中占有最大市场份额

云服务的基本组件
云服务需要四个核心服务组件：

计算服务
存储服务
数据库
网络

所有其他云服务都建立在这四个基础服务之上。
1. 计算服务 (Compute Service)
Amazon EC2（弹性计算云）：

按需提供虚拟机
提供不同类型和容量
容量可快速扩展或缩减
不使用时可终止实例

Amazon Lambda：

无服务器计算函数
按需运行
响应事件自动执行代码
自动扩展
支持多种编程语言（C#、Java、Node.js等）

2. 存储服务 (Storage Service)
Amazon S3（简单存储服务）：

分布式对象存储
可随时随地存储和检索数据
提供存储桶访问

Amazon EBS（弹性块存储）：

EC2实例的持久块存储
相当于服务器的附加驱动器
独立于EC2实例的持久存储卷

3. 数据库服务 (Database Service)
三种主要数据库：

Amazon Aurora：兼容MySQL和PostgreSQL数据库引擎
Amazon RDS：功能类似MySQL的关系数据库服务
Amazon DynamoDB：无服务器NoSQL数据库

这些数据库的共同特点：可扩展、管理任务对终端用户透明化
4. 网络服务 (Network Service)
Amazon VPC（虚拟私有云）：

定义类似传统数据中心的虚拟网络拓扑
逻辑隔离
用户完全控制网络

Amazon ELB（弹性负载均衡）：

将流量分配到指定目标（EC2实例、IP地址）
支持应用层（Layer 7：HTTP/HTTPS）和网络层（Layer 4：TCP/UDP）负载均衡

Amazon Route 53：

DNS服务
将用户流量路由到应用程序和服务

5. 叠加服务 (Overlay Services)
构建在基础服务之上的高级服务：

Amazon SNS：分布式系统和应用程序的消息服务
Amazon SES：事务性邮件发送服务
Amazon CloudFront：内容分发网络(CDN)服务，将数据、视频等高效传递到靠近终端用户的位置

这些服务需要计算、网络和存储的综合支持。

运维、管理和维护服务 (OAM Services)
这些服务用于安全部署、运行和管理AWS上的各种服务：
AWS Calculator（成本计算器）：

计算使用AWS服务的价格
比较不同配置的成本

AWS IAM（身份和访问管理）：

安全控制对AWS服务的访问
创建用户和组
管理用户和服务的访问权限和特权

AWS CloudWatch：

监控和分析AWS资源和服务的日志

AWS CloudTrail：

监控和分析AWS API调用的日志

AWS CloudFormation：

使用模板配置和管理AWS资源

访问AWS服务的三种方式

AWS管理控制台

Web界面
适合执行简单操作


AWS命令行界面（CLI）（推荐）

支持自动化
可重复和可验证的操作
实现基础设施即代码


AWS软件开发工具包（SDK）

针对不同编程语言定制
应用程序可使用SDK与AWS服务交互
也支持基础设施即代码



AWS区域 (AWS Regions)
地理分布：

37个地理区域：全球多个位置，各区域相互隔离
117个可用区：每个区域内有多个隔离位置
43个本地区域：区域的扩展，将服务更靠近终端用户

AWS CLI详解
功能：

通过命令行与AWS服务交互
可执行操作：创建EC2实例、获取实例详情、远程运行命令、终止实例
支持Linux、Windows和Mac

安全凭证：

账户ID、用户名和密码：用于登录在线管理控制台
AWS访问密钥：用于运行AWS CLI命令

包括访问密钥ID和秘密访问密钥
在IAM管理控制台中创建



配置步骤：
bash> aws configure
AWS Access Key ID: **********************
AWS Secret Access Key: **************************************
Default region name: us-east-1
Default output format: json
常用命令示例：

S3存储桶操作：

创建存储桶：aws s3 mb s3://my-first-COMPX527
列出所有存储桶：aws s3 ls
上传文件：aws s3 cp test.txt s3://my-first-COMPX527
查看存储桶文件：aws s3 ls s3://my-first-COMPX527


EC2实例查询：

按实例类型列出
按账户ID列出
显示实例详细信息（ID、子网、公网IP、卷信息、状态等）


DynamoDB操作：

创建新表，定义属性和密钥架构



AWS SDK
特点：

直接从代码访问AWS服务
支持多种编程语言：JavaScript、Python、Java、.NET、Node.js、C++、PHP、Ruby、Go

示例（Python）：
pythonimport boto3
s3 = boto3.resource('s3')
bucket = s3.Bucket('my-bucket')
for obj in bucket.objects.all():
    print(obj.key)

总结： AWS提供了完整的工具生态系统，从Web控制台到命令行工具和SDK，满足不同用户的需求。通过CLI和SDK可以实现自动化和基础设施即代码，提高运维效率。

Week3

一、云安全六大原则(图1)
1. 最小权限原则 (Least Privilege Principle)
仅授予完成任务所需的最小访问权限
2. 启用可追溯性 (Enable Traceability)
确保所有操作和变更都可被监控、审计和追踪
3. 多层安全 (Multi-Layer Security)
采用纵深防御策略,在多个层面部署安全控制
4. 自动化安全最佳实践 (Automate Security Best Practices)
通过自动化提高安全性和效率
5. 增强数据保护 (Enhanced Data Protection)
对数据进行分类并实施适当的加密和访问控制
6. 为安全事件做好准备 (Prepare for Security Events)
建立事件响应计划和恢复机制

二、SIEM工作流程(图2)
SIEM (安全信息和事件管理) 的四个关键步骤:

从源收集数据 - 从各种系统和设备收集日志和事件数据
聚合数据 - 将来自不同源的数据集中整合
发现和检测威胁 - 通过分析识别潜在的安全威胁
识别入侵并调查警报 - 确认安全事件并进行深入调查


三、云安全详细框架(图3-6)
核心安全领域:
1. 安全开发 (Secure Development)

编码标准
代码审查
单元测试

2. 完整性 (Integrity)

防篡改机制
内容检查
快照管理

3. 托管/主机安全 (Hosting)

物理安全
环境安全
存储安全
通信安全

4. 合规性 (Compliance)

审计
识别法规要求
测试
转换/实施

5. 加密技术 (Cryptography)

数据加密
密钥管理

6. 访问管理 (Access Management)

身份管理
注册
配置
特权管理
目录服务
联合身份
策略
过滤
验证/认证/授权

7. 可用性 (Availability)

业务连续性:

BC规划、实施、测试


备份:

故障转移


灾难恢复:

DR规划、实施、测试



8. 安全管理 (Security Management)

保证
架构与设计
程序
传播/执行
策略研究/设计

9. 风险管理 (Risk Management)

分类
评估
处理
认可
通知

10. 人员安全 (Personnel Security)

审查
培训
纪律
协调

11. 安全治理 (Security Governance)
统筹所有安全活动和策略
12. 安全运营 (Security Operations)

监控: 日志、分析、事件管理、报告
管理: 安全通道、管理、部署、配置
变更管理: 问题管理、漏洞管理
事件管理: 响应、调查、行动、关闭
资产管理: 目录、配置管理、许可证


四、责任共担模型(图4-6 - 颜色编码)
图片通过颜色标识不同的责任归属:
绿色区域 - 客户主要责任

合规性
访问管理
人员安全

黄色区域 - 共同责任

安全开发
可用性
加密技术
安全管理
风险管理
安全治理

橙色/红色区域 - 提供商主要责任

托管/主机安全
完整性(部分)
安全运营(部分)

侧边栏标识:

消费者责任 - 客户负责的安全领域
联合责任 - 双方共同负责
提供商责任 - 云服务商负责


五、AWS共享责任模型(图7)
客户责任 - "云中"的安全:

客户数据 - 完全由客户管理
平台、应用程序、身份与访问管理
操作系统、网络和防火墙配置
客户端数据加密与数据完整性认证
服务器端加密(文件系统和/或数据)
网络流量保护(加密、完整性、身份)

AWS责任 - "云本身"的安全:

软件层:

计算
存储
数据库
网络


硬件/AWS全球基础设施:

区域(Regions)
可用区(Availability Zones)
边缘位置(Edge Locations)




六、具体安全措施详解
1. 最小权限原则与执行

为每次与AWS资源的交互应用适当的授权
实施职责分离
从拒绝所有访问开始,根据需要授予权限

2. 多层安全

采用纵深防御方法
结合其他安全控制措施

3. 自动化安全最佳实践

基于软件的自动化安全机制
提高安全扩展能力
更具成本效益

4. 启用可追溯性

实时监控、警报和审计
跟踪环境中的操作和变更

5. 增强数据保护

根据敏感度对数据进行分类
适当使用加密和访问控制机制

6. 为安全事件做好准备

运行事件响应模拟
使用自动化工具进行:

早期检测
调查
恢复


示例工具: SIEM - 负责持续收集和分析数据


关键要点

云安全是共同责任 - 客户和提供商各有明确的责任范围
自动化至关重要 - 提高响应速度和效率
多层防御 - 不依赖单一安全措施
持续监控 - 通过SIEM等工具实现实时威胁检测
最小权限 - 减少潜在的攻击面
事先准备 - 制定并测试事件响应计划

Week4

虚拟化技术知识点总结
1. 虚拟化基础概念
虚拟化定义：虚拟化是将服务请求与其底层物理交付分离的技术。
Virtualization is the separation of a service request from the underlying physical delivery of that service.
虚拟化架构类型：

托管架构(Hosted/Type 2)：在操作系统之上安装虚拟化层作为应用程序
Hosted architecture installs the virtualization layer as an application on top of an operating system.

示例：Oracle VirtualBox, Parallel Desktops
优点：用户友好
缺点：性能较低


裸机架构(Bare-Metal/Type 1)：直接在x86系统上安装虚拟化层
Hypervisor architecture installs the virtualization layer directly on a clean x86-based system.

示例：VMWare ESX Server
优点：性能更高，可扩展性更强
缺点：配置复杂



2. CPU虚拟化技术
模拟(Emulation)：虚拟机管理程序在软件中模拟硬件资源
The hypervisor emulates hardware resources in software and presents them to the guest VM.
完全虚拟化(Full Virtualization)：将内核代码转换为新指令序列，无需修改客户操作系统
Full virtualization translates kernel code to replace non-virtualizable instructions with new sequences that have the intended effect on virtual hardware.
硬件辅助虚拟化(Hardware Assisted)：使用Intel VT-x或AMD-V技术，在Ring 0根模式下运行
Hardware assisted virtualization uses Intel VT-x or AMD-V technologies running under Ring 0 in a new root mode.
3. 虚拟化关键属性
抽象(Abstraction)：隐藏物理硬件的复杂性
Abstraction hides the complexity of physical hardware from virtual machines.
隔离(Isolation)：确保虚拟机之间相互独立
Isolation ensures that virtual machines operate independently from each other.
资源池化(Resource Pooling)：将物理资源聚合供多个虚拟机使用
Resource pooling aggregates physical resources for use by multiple virtual machines.
可移植性(Portability)：虚拟机可在不同硬件平台间迁移
Portability allows virtual machines to be migrated between different hardware platforms.
4. 网络虚拟化
网络虚拟化定义：将传统硬件交付的网络资源抽象到软件中
Network virtualization abstracts network resources that were traditionally delivered in hardware to software.
虚拟交换机(vSwitch)：虚拟机通过vNIC连接到端口组，再通过vmnic连接物理交换机
Virtual machines connect to port groups through vNICs, then connect to physical switches through vmnics.
AWS VPC组件：

互联网网关(Internet Gateway)：连接VPC与互联网
The Internet Gateway connects the VPC to the wider internet.
公有子网(Public Subnet)：绑定到可用区，可从互联网访问
Public subnets are tied to availability zones and accessible from the internet.
私有子网(Private Subnet)：不可从互联网访问
Private subnets are not accessible from the internet.

5. 内存虚拟化
内存虚拟化：共享物理系统内存并动态分配给虚拟机
Memory virtualization shares physical system memory and dynamically allocates it to VMs.
地址映射：操作系统维护虚拟页号到物理页号的映射
The OS maintains a mapping of virtual page numbers to physical page numbers stored in page tables.
三层地址转换：

虚拟地址(VA) → 物理地址(PA) → 机器地址(MA)
Virtual Address (VA) → Physical Address (PA) → Machine Address (MA)

6. I/O和设备虚拟化
设备虚拟化：虚拟化物理设备供多个虚拟机共享使用
Device virtualization virtualizes physical devices for shared use by multiple virtual machines.
支持的设备类型：网卡、声卡、显卡、并口、串口、存储设备等
Supported device types include network cards, sound cards, video cards, parallel ports, serial ports, and storage devices.
7. 虚拟化安全问题
主要安全威胁：

虚拟机管理程序攻击(Hypervisor Attacks)：针对虚拟化层的攻击
Hypervisor attacks target the virtualization layer itself.
跨虚拟机攻击(Cross VM Attacks)：一个虚拟机攻击另一个虚拟机
Cross VM attacks occur when one virtual machine attacks another.
主机操作系统入侵(Host OS Compromise)：宿主系统被攻破
Host OS compromise occurs when the host system is breached.
侧信道攻击(Side-Channel Attacks)：通过共享资源泄露信息
Side-channel attacks leak information through shared resources.
权限提升(Privilege Escalation)：获取未授权的高级权限
Privilege escalation involves gaining unauthorized elevated privileges.

Week5

1. 云计算最大威胁：身份与访问管理
关键知识点：

如果实体未被正确识别，且其权限未被明确定义，数据或系统被入侵的风险会显著增加
Identity and Access Management (IAM) are critical because improper access control in cloud environments exposes services to the entire world without physical perimeter protection.

2. IAM核心概念区分
关键知识点：

身份（Identity）：每个实体需要一个身份
认证（Authentication）：验证身份的过程
访问管理（Access Management）：确保实体只能执行其需要执行的任务
授权（Authorization）：检查实体应具有的访问权限
Authentication verifies who you are, while authorization determines what you are allowed to do.

3. 云环境中的认证三层级
关键知识点：

Business-to-Business (B2B)：组织员工与云服务提供商的认证
Business-to-Employee (B2E)：组织员工与自有应用的认证
Business-to-Consumer (B2C)：组织客户与自有应用的认证


Cloud authentication operates at three levels: authenticating employees with cloud providers, employees with internal applications, and customers with your services.

4. 外部身份提供商（IdP）
关键知识点：

IdP存储和管理数字身份
优势：避免密码疲劳、利用专家资源提升安全性
风险：必须安全使用API、必须了解IdP如何验证身份
Identity Providers allow users to authenticate using existing credentials from services like Google or Facebook, reducing password fatigue while requiring careful API security.

5. 授权的两大核心原则
最小权限原则（Least Privilege）
关键知识点：

用户或应用只能访问完成工作所需的资源
实践中通常采用"默认拒绝"策略
The principle of least privilege ensures that users can only access what they need to perform their jobs, with access policies being deny by default.

职责分离（Separation of Duties）
关键知识点：

确保单个人无法完成恶意操作所需的所有权限
敏感操作需要多人协作完成
Separation of duties prevents one individual from having all necessary permissions to complete malicious actions involving sensitive information.

6. 策略类型
关键知识点：

基于身份的策略（Identity-based policies）：控制身份能执行的操作
基于资源的策略（Resource-based policies）：附加到特定资源
基于角色的策略（Role-based policies）：将权限应用于角色而非个人
基于属性的策略（Attribute-based policies）：基于标签属性授予权限


Cloud policies define who can perform what actions on which resources under what conditions, with multiple policy types available for different use cases.

7. AWS IAM术语
关键知识点：

账户（Account）：12位账户ID，控制创建的资源
主体（Principal）：可对资源执行操作请求的用户、服务或账户
IAM用户（IAM User）：账户内创建的实体，具有独特安全凭证
IAM角色（IAM Role）：可授予其他账户用户临时访问权限
An IAM role includes a trust policy specifying which principals can assume the role and permissions defining what actions the role can perform.

8. 角色使用流程
关键知识点：

创建角色时必须包含信任策略（Trust Policy）
用户需要权限才能担任角色（AssumeRole）
用户还需要权限将角色传递给其他用户或服务（PassRole）


To use a role, you must first create it with a trust policy, then users need both AssumeRole permission and PassRole permission to utilize it.

9. 标签（Tags）策略
关键知识点：

标签由键值对组成（tag key + tag value）
可应用于实体和资源
单个资源不能同时有两个相同键的标签
条件中使用：aws:ResourceTag/key-name 和 aws:PrincipalTag/key-name
Tags enable attribute-based access control by allowing policies to check resource tags using aws:ResourceTag and principal tags using aws:PrincipalTag in condition statements.

Week6

1. 最小权限原则 (Least Privilege)
核心挑战：

确定适当的"最小权限"是一个复杂的问题
Determining the appropriate "least privilege" for a given use case is a surprisingly complex issue.
权限配置会随时间漂移和变化
Even successful least privilege implementations tend to shift and drift over time.
过于严格的访问控制会影响可用性
Too strict access controls impact usability.

实施策略：

需要高权限的用户：管理员、工程师、安全人员
Privileged users who need high privileges include those performing administration, engineering, and security-focused tasks.
关系映射：创建最严格的权限模型
Relationship mapping helps create the most restrictive privilege models needed.

2. 网络分段 (Network Segmentation)
安全价值：

减少横向移动风险
A least privilege model reduces the scope of impact when an attacker has illicitly gained access to an asset within a cloud environment.
默认拒绝所有，然后只添加必要的访问
The classic model for implementing least privilege at the network level starts with a network access control policy of Deny All.
示例：使用 VPC 实现网络隔离
VPC is an example of implementing network segmentation in cloud environments.

3. 云安全态势管理 (CSPM)
主要功能：

监控服务、账户和权限的错误配置
CSPM monitors your services, accounts, and privileges for known misconfiguration issues.
工具示例：Prowler、AWS Security Hub、第三方 CSPM 工具
Examples of CSPM tools include Prowler, AWS Security Hub, and third-party CSPM tools.

4. 基础设施即代码 (IaC)
核心概念：

自动化：使用工具执行可重复的配置操作
Automation uses tools and software to perform repeatable configuration actions and processes.
编排：协调多个自动化任务按顺序或并行工作
Orchestration coordinates multiple automated tasks to work together in a sequence or in parallel.
配置管理：保持基础设施配置的一致性
Configuration management keeps your configuration uniform across your infrastructure.

5. Terraform 工作原理
三个核心步骤：

Write（编写）：定义资源配置

In the Write phase, you define resources which may be across multiple cloud providers and services.


Plan（计划）：创建执行计划

Terraform creates an execution plan describing the infrastructure it will create, update, or destroy based on existing infrastructure and configuration.


Apply（应用）：执行批准的操作

On approval, Terraform performs the proposed operations in the correct order.



6. Terraform 关键特性
不可变基础设施方法：

Terraform 采用不可变方法，而非可变方法
Terraform takes an immutable approach, reducing the complexity of upgrading or modifying your services and infrastructure.
不可变方法：创建新资源，更新引用，销毁旧资源
The immutable approach creates a new instance, updates references like load balancer targets, then destroys the old instance.

状态管理：

状态文件作为环境的真实来源
The state file acts as a source of truth for the environment.
Terraform 通过状态文件确定需要对基础设施进行的更改
Terraform uses a state file to determine the changes to make to your infrastructure so that it will match your configurations.

声明式配置：

配置文件描述基础设施的最终状态
Terraform configuration files are declarative and describe the end state of the infrastructure.
Terraform 自动处理底层逻辑
Terraform handles the underlying logic automatically.

Week9

云计算数据安全完整知识点总结
1. 数据的重要性和分类
所有计算系统都是为了消费、服务和/或操作数据而构建的,数据分为个人数据、财务数据、数字身份、运营数据、业务数据和安全数据六大类。
All computing systems are built to consume, serve and/or manipulate data, which is classified into six major categories: personal data, financial data, digital identities, operational data, business data, and security data.
2. 数据安全的必要性
数据安全对于风险管理(防止财务损失、声誉损害、运营中断)、遵守法律法规(GDPR、PCI-DSS等)以及保证机密性、完整性和可用性至关重要。
Data security is crucial for risk management (preventing financial loss, reputation harm, operational discontinuity), compliance with laws and regulations (GDPR, PCI-DSS, etc.), and ensuring confidentiality, integrity, and availability.
3. IaaS中的数据类型
IaaS提供三种数据存储:卷存储(如Amazon EBS,作为虚拟硬盘附加到实例)、对象存储(如Amazon S3,通过API或Web界面访问)和原始存储(物理介质)。
IaaS provides three types of data storage: volume storage (like Amazon EBS, attached to instances as virtual hard drives), object storage (like Amazon S3, accessed via APIs or web interfaces), and raw storage (physical media).
4. PaaS中的数据类型
PaaS提供结构化数据(数据库即服务,如AWS RDS、Azure MSSQL,可以是关系型或平面数据库)和非结构化数据(大数据即服务,如Google BigTable、DynamoDB)。
PaaS provides structured data (Database as a Service like AWS RDS, Azure MSSQL, which can be relational or flat) and unstructured data (Big Data as a Service like Google BigTable, DynamoDB).
5. SaaS中的数据类型
SaaS提供信息存储和管理(通过Web界面输入的数据,如Gmail)以及内容/文件存储(在SaaS应用中存储的基于文件的内容,如Dropbox)。
SaaS provides information storage and management (data entered via web interfaces like Gmail) and content/file storage (file-based content stored within SaaS applications like Dropbox).
6. 云服务模型中的责任划分(Pizza as a Service)
从传统本地到IaaS、PaaS、SaaS,用户管理的组件逐渐减少,供应商管理的组件逐渐增多;蓝色代表用户管理,绿色代表供应商管理。
From traditional on-premises to IaaS, PaaS, and SaaS, the components managed by users gradually decrease while vendor-managed components increase; blue represents user-managed and green represents vendor-managed.
7. 数据保护策略制定
确定保护哪些数据需要:威胁建模、数据清单和分类、遵守法律法规、制定信息管理策略和位置/管辖权策略。
Determining what data to protect requires: threat modeling, data inventory and classification, compliance with laws and regulations, establishing information management policies and location/jurisdiction policies.
8. GDPR与云计算
GDPR要求:了解云应用处理或存储数据的位置、与云应用签订数据处理协议、采取适当安全措施保护个人数据、只收集必要数据并限制特殊数据处理、确保数据删除能力。
GDPR requirements include: knowing the location where cloud apps process or store data, closing data processing agreements with cloud apps, taking adequate security measures to protect personal data, collecting only necessary data and limiting special data processing, and ensuring the ability to stop using apps and erase data.
9. 数据安全生命周期 - 创建阶段
创建阶段是生成新数字内容或修改现有内容的过程,可以在云中或云外进行,需要根据敏感性和组织价值对数据进行分类。
The creation phase is the generation of new digital content or alteration of existing content, which can occur in or outside the cloud, and requires classifying data according to sensitivity and value to the organization.
10. 数据安全生命周期 - 静态数据(Data at Rest)
静态数据是创建后存储或离开活跃使用后归档的数据,数据大部分时间处于此阶段,需要考虑:数据是否安全存储、密钥如何管理、如何防范恶意内部人员、篡改保护等。
Data at rest is data stored after creation or archived after leaving active use, where data spends most of its time, requiring considerations for: secure storage, key management, protection from malicious insiders, and tamper protection.
11. 数据安全生命周期 - 传输数据(Data in Motion)
传输数据是在云之间或云与用户之间传输的数据,需要考虑:安全传输、数据完整性、信息权限管理、SLA合规性,必须在数据传输前建立安全通道。
Data in motion is data being transported between clouds or between cloud and user, requiring considerations for: secure transmission, data integrity, information rights management, SLA compliance, and secure channels must be established before data transfer.
12. 数据安全生命周期 - 使用中数据(Data in Use)
使用中数据是被查看、处理或用于某种活动的数据,这是最脆弱的阶段,因为某些安全控制可能需要关闭,需要考虑:计算保证、信息泄漏、未授权访问等。
Data in use is data being viewed, processed or used in activities, which is the most vulnerable stage as some security controls may need to be turned off, requiring considerations for: computation guarantee, information leakage, and unauthorized access.
13. 数据安全生命周期 - 销毁阶段
数据销毁意味着数据不再可用,根据数据内容和应用可能有不同含义:逻辑删除指针(数据可能未真正删除)或物理永久删除数据。
Data destruction means data ceases to be available for use, which can mean different things: logically erasing pointers (data may not be truly deleted) or physically permanent data deletion.
14. 访问控制的三层架构
访问控制应在三个层面实施:管理平面控制(管理直接访问云平台的用户)、公共和内部共享控制(外部共享的第二层控制)、应用级控制(自建应用的访问管理)。
Access controls should be implemented at three layers: management plane controls (for users directly accessing the cloud platform), public and internal sharing controls (second layer for external sharing), and application-level controls (for custom-built applications).
15. 权限矩阵(Entitlement Matrix)
权限矩阵定义不同角色对不同操作的访问权限,角色包括超级管理员、服务管理员、存储管理员、开发人员、安全审计和安全管理员。
The entitlement matrix defines access permissions for different roles to different operations, including Super-Admin, Service-Admin, Storage-Admin, Dev, Security-Audit, and Security-Admin.
16. 加密基础概念
加密是使用密钥将数据(明文)编码为随机数据(密文)的过程,包括加密密钥用于加密明文为密文,解密密钥用于将密文解密回明文。
Encryption is the process of encoding data (plain-text) into random data (cipher-text) using a key, where an encryption key is used to encrypt plaintext into ciphertext, and a decryption key is used to decrypt ciphertext back to plaintext.
17. 对称加密 vs 非对称加密
对称加密使用相同的密钥(秘密密钥)进行加密和解密,密钥尺寸较小、速度快但密钥管理困难,通常用于数据加密;非对称加密使用公钥/私钥对,密钥尺寸较大、速度较慢但密钥管理更容易,通常用于数字签名。
Symmetric encryption uses the same key (secret key) for encryption and decryption, with smaller key sizes, faster speed but harder key management, typically used for data encryption; asymmetric encryption uses public/private key pairs, with larger key sizes, slower speed but easier key management, typically used for digital signatures.
18. 静态数据加密 - 对象级加密
对象级加密有两种方式:云处理加密(云在接收数据后进行加密,云提供商可访问密钥)和应用处理加密(应用或客户端在发送到云之前加密数据,云只存储已加密对象)。
Object-level encryption has two approaches: cloud-handled encryption (cloud encrypts data after receiving it, cloud provider has access to the key) and application-handled encryption (application or client encrypts data before sending to cloud, cloud only stores encrypted objects).
19. 传输中数据加密
大多数云提供商的API原生支持通过IPsec、VPN等进行传输加密,用户和应用需要在数据往返云端时使用传输加密,混合架构中数据在本地存储和云之间移动时也应使用。
Most cloud providers' APIs natively support data in motion encryption through IPsec, VPN, etc.; users and applications need to use DIM encryption when data moves between cloud and user; in hybrid architectures DIM encryption should be used when data moves between on-premises storage and cloud.
20. 使用中数据加密 - 飞地技术(Enclaves)
在RAM中创建飞地区域,进程数据在其中以加密形式存储,数据仅在CPU寄存器或缓存中解密,这样可以保护数据免受内存转储攻击。
Enclaves are created within RAM where process data is stored encrypted, and data is only decrypted in CPU registers or cache, protecting data from memory dump attacks.
21. 同态加密(Homomorphic Encryption)
同态加密允许对加密数据进行有限操作(通常是加法、乘法、比较或搜索);部分同态加密只允许一种操作,完全同态加密允许加法和乘法两种操作。
Homomorphic encryption allows limited operations on encrypted data (typically addition, multiplication, comparison or search); partially homomorphic encryption allows only one operation, while fully homomorphic encryption allows both addition and multiplication.
22. 密钥管理方案
密钥管理有四种选项:HSM/设备(传统硬件安全模块,通常在本地)、虚拟设备/软件(云中部署)、云提供商服务(需了解安全模型和SLA)、混合方案(如HSM作为信任根,虚拟设备管理应用密钥)。
There are four key management options: HSM/appliance (traditional hardware security module, typically on-premises), virtual appliance/software (deployed in cloud), cloud provider service (need to understand security model and SLAs), and hybrid (such as HSM as root of trust with virtual appliance for application keys).
23. 令牌化(Tokenization)
令牌化是将有意义的数据(如账号)转换为无意义随机字符串(令牌)的过程,令牌作为原始数据的引用但不能用于猜测原始值,即使被泄露也没有价值。
Tokenization is the process of turning meaningful data (such as account numbers) into random strings called tokens that have no meaningful value if breached; tokens serve as references to original data but cannot be used to guess those values.
24. 云环境的安全威胁
云环境面临三类攻击者:内部攻击者(在私有网络内部)、外部攻击者(通过互联网)和云服务提供商,需要通过虚拟交换机、Hypervisor和物理交换机等多层防护。
Cloud environments face three types of attackers: insider attackers (within private network), external attackers (through internet), and cloud service providers, requiring multi-layer protection through virtual switches, hypervisors, and physical switches.

Week10

Web应用安全风险知识点总结
核心概念
1. 云应用定义
云应用提供本地应用程序的功能，可能有轻量级客户端或完全基于Web，并可能与多个云接口连接。
Cloud applications provide the functionality of native applications, may have lightweight clients or be completely web-based, and can interface with multiple clouds.
2. 云应用安全的特殊性
云应用安全与非云应用的不同在于：可见性有限、攻击面更广、应用和数据不完全由所有者管理、威胁模型不同。
Securing cloud applications differs from non-cloud applications due to limited visibility, wider attack surfaces, applications and data not being fully managed by owners, and different threat models.
OWASP Top 10 Web应用安全风险
3. 十大安全风险（2021版）
OWASP十大安全风险包括：访问控制失效、加密失败、注入攻击、不安全设计、安全配置错误、易受攻击和过时的组件、身份验证失败、软件和数据完整性失败、安全日志和监控失败、服务器端请求伪造。
The OWASP Top 10 security risks include Broken Access Control, Cryptographic Failures, Injection, Insecure Design, Security Misconfiguration, Vulnerable and Outdated Components, Identification and Authentication Failures, Software and Data Integrity Failures, Security Logging and Monitoring Failures, and Server-Side Request Forgery.
安全防护措施
4. 风险缓解策略
缓解安全风险的方法包括：安全编码实践、漏洞评估和渗透测试。
Security risk mitigation methods include secure coding practices, vulnerability assessment, and penetration testing.
5. 漏洞评估
漏洞评估是识别和优先处理系统中存在的漏洞的过程，漏洞扫描器是搜索和报告漏洞的工具。
Vulnerability assessment is a process to identify and prioritize vulnerabilities present in a system, and vulnerability scanners are tools that assess applications and servers to search for and report vulnerabilities.
6. 持续漏洞扫描的三种类型
SAST在编译前检测代码中的漏洞，SCA分析代码依赖关系并检测漏洞，DAST通过动态交互检测运行中应用的漏洞。
SAST detects vulnerabilities in code before compilation, SCA analyzes code dependencies and detects vulnerabilities, and DAST detects vulnerabilities in running applications through dynamic interaction.
7. 渗透测试类型
渗透测试包括三种类型：白盒测试（完全了解系统）、黑盒测试（无系统知识）和灰盒测试（部分系统知识）。
Penetration testing includes three types: white box testing (full system knowledge), black box testing (no system knowledge), and grey box testing (partial system knowledge).


Week11

一、核心法律风险与关注点
1. 隐私保护 (Privacy)
当组织迁移到公共云时，必须识别与应用程序和数据相关的法律法规要求以及法律风险。
When moving to a public cloud, organizations must identify legal and regulatory requirements as well as legal risks associated with their applications and data.
2. 个人可识别信息 (PII - Personally Identifiable Information)
个人可识别信息是指任何可以用来区分或追踪个人身份的信息，包括姓名、社会保障号、护照号码、生物识别信息等。
Personally Identifiable Information refers to any information that can be used to distinguish or trace an individual's identity, including name, social security number, passport number, and biometric information.
3. 六大法律风险

隐私 (Privacy)
数据位置 (Data Location)
数据所有权 (Data Ownership)
数据保留 (Data Retention)
声誉共担 (Reputation Fate Sharing)
调查取证 (Investigation - Forensics)

二、法律尽职调查 (Legal Due Diligence)
4. 数据托管责任
公司是委托给他们的数据的保管人，必须遵守众多禁止、限制和限制向第三方披露和传输数据的法律法规。
Companies are custodians of data entrusted to them and must comply with numerous laws and regulations that prohibit, restrict, and limit disclosure and transfer of data to third parties.
5. 关键考虑问题

客户是否接受数据传输给第三方
处理的数据是否允许跨越国界
如何识别并采取适当行动来降低法律风险

三、主要法律法规
6. 新西兰隐私法 2020 (NZ Privacy Act 2020)
新西兰隐私法定义了13项信息隐私原则，规定机构如何收集、存储、访问、更正、使用和披露个人信息。
The NZ Privacy Act defines 13 Information Privacy Principles that set out how agencies collect, store, access, correct, use, and disclose personal information.
13项原则包括：

IPP 1-4: 收集个人信息
IPP 5: 存储个人信息
IPP 6-7: 访问和更正个人信息
IPP 8, 10, 11: 使用和披露个人信息
IPP 9: 信息保留期限
IPP 12: 境外披露
IPP 13: 唯一标识符使用

7. 新西兰信息安全手册 (NZISM)
该手册为政府机构及其供应商提供信息系统安全指南，所有云计算决策应在风险评估后个案处理。
This manual provides information systems security guidance for government agencies and their vendors, and all cloud computing decisions should be made on a case-by-case basis after risk assessment.
8. 其他重要法规

澳大利亚: 国家隐私法 (Australian National Privacy Act)
美国:

GLBA (控制金融机构存储和处理的个人数据)
SOX (保护股东和公众免受会计错误和欺诈)
CLOUD Act (美国执法部门可要求美国公司提供数据，即使数据中心在境外)



四、国际标准
9. 安全与合规标准
ISO/IEC 27001和27002是治理、风险和合规的国际标准，而ISO/IEC 27017和27018专门针对云安全。
ISO/IEC 27001 and 27002 are international standards for governance, risk, and compliance, while ISO/IEC 27017 and 27018 specifically address cloud security.
主要标准包括：

治理、风险、合规: ISO/IEC 27001/27002, COBIT, ITIL
云安全: ISO/IEC 27017, 27018
数据保护: GDPR, ISO/IEC 29151, HIPAA, PCI-DSS, FIPS 140

五、合规失败的后果
10. 处罚与责任
未能遵守法律法规通常会导致严重的处罚和责任问题。
Failure to comply with laws and regulations often results in heavy punishment and liability issues.

