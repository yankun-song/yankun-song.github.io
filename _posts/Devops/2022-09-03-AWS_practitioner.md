---
title: AWS Certified Cloud Practitioner Exam
date: 2022-09-03 00:00:00 -500
categories: [Devops]
tags: [AWS] # TAG names should always be lowercase
img_path: /assets/posts/
---

CloudFront 是内容传播

AWS 可以降低运营成本，变化快（不需要更换设备等）

迁移到 AWS serverless 表现更好

AWS organizations 可以允许共享账号和 reserved instances

Availability Zone 由离散的数据中心，且数据中心有冗余的算力、网络等

AMI/ snapshots 都是备份

EC2 的购买选项：

- On demand: 随要随用，无折扣 类比：临时出去玩住酒店
- Reserved: 对需求清楚明确，提前预定需要的服务，享受折扣 类比：提前预定圣诞节要住的房间
- Saving Plans: 对服务内容不是特别固定，但是有保底消费金额 类比：可在套房、海景房自由切换，但是消费金额不得小于 x
- Spot Instances: 竞拍闲置的资源，有低价的就用，涨价了就不用 类比：淡季出行
- Dedicated Hosts: 包场
- Capacity Reservations: 租制定的房间一整年，就算今天不住也掏钱

AWS Lambda 由数据的变化或系统状态的变化触发

AWS SDKs 允许用户程序化地部署云服务

Cost Allocation Tags 可以查看哪个部分在用哪个 AWS 资源

AWS Consulting Partners 帮助客户提供设计、构造、迁移和管理 AWS 的意见。

AWS Managed Services 提供优化服务的意见。

Service Quotas 跟踪服务极限的增长。

AWS Artifact 提供 AWS 的 ISO 认证，下载相关的安全和协议报告。

更改 AWS support plan 需要根用户权限。

AWS Simple Queue Service（SQS)每秒可处理 1 - 10,000 条消息

VPC 可以拓展到同一个 region 下的所有 AZ

AWS site-to-site VPN 由 virtual private gateway 和 customer gateway 组成。

连接在不同 region 的 VPC 可以用 VPC peering。

AWS WAF 是 stateless，可以防范 DDoS 攻击。AWS Shield 也可以防范，但是功能仅此而已。

对于 EC2 来说，Security group 起到了防火墙的作用。

AWS Enterprise support：24/7 technical account manager/ support of third-party software integration to AWS/ 15 min response time.

AWS developer support: business hours

AWS Organizations 用 Service control policies（SCP）来控制权限。

AWS Service Catalog 可以控制员工访问资源的权限。

ACL 是 stateless，按顺序处理 rules，从最小数字的 rule 开始。

Direct Connect 能提供 on-premises 和 AWS 之间的连接。PrivateLink 是在 AWS 内部提供连接。

Amazon Macie 使用 Machine Learning 帮助发现 S3 中的敏感数据。

AWS Global Accelerator 可以提高 availability 和 performance。

AWS IAM Access Analyzer 可以识别与外界共享的 S3 和 IAM role。

AWS Transit Gateway 连接并管理不同区域的 VPC。相比于 VPX peering, Transit Gateway 更适合很多的 VPC。

Cost Explorer 查看账单，支持数据可视化

Amazon QuickSight 是数据可视化工具，可以提供 interactive dashboards。 Amazon Athena 用来分析 S3 中的数据。实时分析用户数据需要 Kinesis Data Analytics。

Amazon CloudWatch 检测 EC2 的 CPU 和网络使用情况。

AWS Trusted Advisor 监控套餐使用量。

AWS CloudTrail 找到用户访问 console 和用户发送 request 的记录。

infrastructure-as-code(IaC) --> AWS CloudFormation

AWS Local Zones 把 AWS 部署在大城市，降低延迟。

AppStream 允许用户即时在任意地点，访问特定的 desktop applications。

Amazon Workspace 允许用户在个人设备上访问公司桌面。

GuardDuty 可以实现威胁**监测**。Amazon Inspector 发现 EC2 中的弱点和漏洞。

Fargate 是 serverless。

Snowball Edge 把数据传送到 AWS。

AWS Key Management Service (AWS KMS)在空闲时对数据进行**加密**。

AWS Pricing Calculator 预估未来收费。

on-prem 和 AWS 之间的连接用 Direct Connect 和 VPN。

Outposts: on-prem 和 AWS 的 hybrid

AWS Storage Gateway 提供 on-prem 和 AWS 的 hybrid 的备份。

对于频繁改动的数据： EFS + RDS。

CloudFront 和 Wavelength 利用了 global edge locations。

Operational Excellence:小步迭代

Security group 是在 instance level，Network Access Control List(ACL)是在 subnet level。

Traceability 带来了安全。

Redshift: 分析 PB 级别的数据.

Route 53: Highly available and scalable DNS web service。

AWS Systems Manager Session Manager 是除 SSH 外另一种登录 EC2 的方式。

Rekognition 分析照片，Comprehend 分析文本背后的内容， Textract 识别图片形式的文本。

S3 Standard-Infrequent Access (S3 Standard-IA)适合不常访问的内容，且无法被再创造的数据。S3 One Zone-IA 要求数据 re-createable。

AWS Compliance Program 可以帮助用户决定符合地区法规要求的服务。

Amazon Cognito 身份管理，设置用户登录。

AWS X-Ray 提供端对端表现评估。

AWS Glue 用于 ETL。

AWS CodeCommit 提供 private version control system。CodeStar 提供 CI/CD。CodeGuru 提供代码质量建议。
预估未来 AWS 用量： Cost Explorer; 预估项目中的未来数据： Amazon Forecast。

想使用 licensing physical cores 的软件，则用 dedicated host。

AWS compute services: Lightsail 和 Batch。
