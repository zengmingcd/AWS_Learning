# Course: AWS Cloud Practitioner Essentials

## Module 1 Introduction to Amazon Web Services

### 3 deployment models for cloud computing / 3种云服务部署模式
- Cloud-based deployment / 基于云的部署
  - Run all parts of the application in the cloud. 
  - Migrate existing applications to the cloud.
  - Design and build new applications in the cloud.
- On-premises deployment (Private cloud) / 本地部署(私有云)
  - Deploy resources by using virtualization and resource management tools.
  - Increase resource utilization by using application management and virtualization technologies.
- Hybrid deployment / 混合部署
  - Connect cloud-based resources to on-premises infrastructure.
  - Integrate cloud-based resources with legacy IT applications.

### 6 benefits of cloud computing / 云计算的6个好处。
- Trade upfront expense for variable expense. / 将前期数据中心、物理服务器等其他资源的投入，转变为按计算资源付费，减少前期投资。
- Stop spending money to run and maintain data centers. / 减少数据中心运行和维护的投入。
- Stop guessing capacity. / 不用事前预测容量，根据实际情况启动实例。按用量付费。
- Benefit from massive economies of scale. / 用户体量实现规模效应，分摊成本，转化为随用随付价格（pay-as-you-go prices）
- Increase speed and agility. / 相比数据中心需要花费更多时间采购、安装、调试等工作，云计算更快分配资源。
- Go global in minutes. / 全球化部署，降低用户访问延迟。

---

## Module 2 Computing in the Cloud

### Terms
- Amazon EC2: Amazon Elastic Comput Cloud.
- Multitenancy: Sharing underlying hardware between virtual machines.
- Caas: Comput as a Service.
- Vertical Scaling
- ELB: Elastic Load Balancing. The AWS service that automatically distributes incoming application traffic across multiple resources.
- Monolithic application: all components are in a same application, tightly coupled components. One component fails, others will fail.
- Microservices: all components are individual, loosely coupled. One component fails, others will keep running.
- Amazon SNS: Amazon Simple Notification Service, a publish/subscribe service. Using Amazon SNS topic, a publisher publishes messages to subscribers. Subscribers can be web servers, email address, AWS Lambda functions, or several other options.
- Amazon SQS: Amazon Simple Queue Service, a message queuing service. Using Amazon SQS, you can send, store, and recieve messages between software components, without losing messsages or requiring other services to be available. An application sends messages into a queue. A user or service retrieves a message from the queue, processes it, and the deletes it from the queue.
- Serverless computing: your code runs on servers, but you don't need to provision or manage these servers. The flexibility to scale serverless applications automatically. You can not see or access the underlying infrastructure. Running less than 15 minutes applications. 
- AWS Lambda: a serverless computing service. Pay only for the compute time that you consume.
- Containers: Provide you with a statndard way to package your application's code and dependencies into a single object. Can be used for processes and workflows in which there are essentail requirements for security, reliability, and scalability.

### 5 type of Amazon EC2 Instance
- General purpose instance
  - Provide a balance of compute, memory, and network resources.
  - Use for: application servers, gaming servers, backend servers for enterprise applications, small and medium database.
- Compute optimized instance
  - ideal for compute-bound applications that benefit from high-performance processors.
  - Use for: high-performance web servers, compute-intensive applications servers, dedicated gaming servers, batch processing workloads that require processing many trasactions in a sigle group.
- Memory optimized instance
  - ideal for process large datasets in memory.
  - Use for: requires large amounts of data to be preload before running an application.
- Accelerated computing instance
  - Use hardware accelerators, or coprocessors, to perform some functions more efficiently than is possible in sofware running on CPUs.
  - Use for: floating-point number calculations, graphics processing and data patten matching. Such as graphics applications, game streaming, application streaming.
- Storage optimized instance
  - designed for require high, sequential read and write access to large datasets on local storage. Tens of thousands of low-latency, random IOPS (input/output operations per second) to applications.
  - Use for distributed file systems, data warehousing applications, high-frequency online trasaction processing (OLTP) systems.

### 5 pricing options of EC2
- On-Demand
  - ideal for shor-term, irregular workloads that cannot be interrupted.
  - No upfront costs or minimum contracts apply.
  - The instances run continously until you stop them, and you pay for only the compute time you use.
  - Not recommand for last a year or longer.
- Reserved Instances
  - Billing discount appplied to the use of On-Demand Instance. 2 types: 
    - Standard Reserved Instance
      - good fit if you know the type and size you need:
        - Instance type and size.
        - Platform description (operating system)
        - Tenancy: Default tenancy or dedicated tenancy
    - Convertible Reserved Instance
      - good if you need to run EC2 instances in defferent Availability Zones ro different instance types.
  - At the end of a reserved term, you can continue using the EC2 instance without interruption. You are charged On-Demand rates until you do one of the following:
    - Terminate the instance.
    - Purchase a new reserved instance that matches the instance attributes.
- EC2 Instance Saving Plans
  - make an hourly spend commitment to an instance family and region for a 1-year or 3-year term.
  - saving up to 72%
  - fit for flexibility usage
  - no need to specify up front resouces
- Spot Instances
  - flexible start and end times. or can withstand interruptions.
  - use unused EC2 computing capacity and saving at up to 90% off of On-Demand prices.
- Dedicated Hosts / 专用主机
  - physical servers with EC2 instance capacity that is fully dedicated to your use.

### Scalabiltiy
- Scalability involves beginning with only the resources you need and designing your architecture to automatically respond to changing demand by scaling out or in. / 可扩展性是指仅从需要的资源开始，并设计架构以便自动扩展和缩减，从而相应不断变化的需求。

### 2 approaches in Amazon EC2 Auto Scaling
- Dynamic scaling responds to changing demand. 动态扩展
- Predictive scaling automatically schedules the right number of Amazon EC2 instances based on predicted demand. 预测性扩展

### Amazon EC2 Auto Scaling config
- Set minimum capacity. 
  - minimum capacity is the number of Amazon EC2 instances that launch immediately after you have created the Auto Scaling Group.
- Set desired capacity.
- Set maximum capacity. max instance you will have.

### How AWS Lambda works
- Upload code to Lambda
- Set code to trigger from an event source.
- Code runs only when triggered.
- Pay only for the compute time you use.

### 3 types of Service for Container
- Amazon Elastic Container Service (Amazon ECS): a highly scalable, high-performance container management system that enables you to run and scale containerized applications on AWS. Supports Docker.
- Amazon Elastic Kubernetes Service (Amazon EKS): a fully managed service that you can use to run Kubernetes on AWS.
- AWS Fragate: a serverless compute engine for containers. Works with both Amazon ECS and Amazon EKS.

### 3 Compute services
- Amazon EC2
  - Host traditiondal applications / 托管传统应用程序
  - Full access to the OS / 对操作系统的完全访问权限
- AWS Lambda
  - Host short running functions / 托管短时间运行函数
  - Service-oriented applications / 面向服务的应用程序
  - Event driven applications / 事件驱动型应用程序
  - No provisioning or managing servers / 无需预置或管理服务器
- Container(Amazon EC2 or AWS fragate) + Amazon ECS or Amazon EKS
  - Run Docker container-based workloads on AWS

---

# Module 3 Global Infrastructure and Reliability

### Terms
- Availability Zone: a single data center or a group of data centers within a Region. Locate tens of miles apart from each other. A region consists of three of more Availability Zones.
- Edge location: a site that Amazon CloudFront uses to store cached copies of your content closer to your customers for faster delivery. 
- Amazon Outposts: a service that enables you to run infrastructure in a hybird cloud approach.

### 4 Business Factor when selecting a region
- Compliance with data governance and legal requirements. / 遵守数据监管和法律要求
- Proximity to your customers. Help you to get content to them faster. / 靠近客户
- Available services within a region. / 区域内的可用服务
- Pricing. / 定价

### 3 Key Points of Region
- Regions are geographically isolated areas. / 区域是在地理位置上隔离的区域。
- Regions contain availability Zones. / 区域包含可用区。
- Edge locations run Amazon CloudFront. / Amazon CloudFront 在边缘站点运行。

### 3 Ways to interact with AWS services
- AWS Management Console: a web-based interface for accessing and managing AWS services.
- AWS Command Line Interface (CLI): Control multiple AWS services directly from the command line within one tool. 
- Software Development Kits (SDK): Use AWS services through an API designed for your programming language or platform.


### 2 Ways to provision AWS resources automaticly
- AWS Elastic Beanstalk: User provide code and configuration settings, and Elastic Beanstalk deploys the resources necessary to perform the following tasks:
  - Adjust capacity
  - Load balancing
  - Automatic scaling
  - Application health monitoring
- AWS CloudFormation: Treat your infrastructure as code.

---

# Module 4 Networking
