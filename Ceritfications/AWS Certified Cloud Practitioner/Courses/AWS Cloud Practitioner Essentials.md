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

## Module 2 Computing in the Cloud

### Terms
- Amazon EC2: Amazon Elastic Comput Cloud.
- Multitenancy: Sharing underlying hardware between virtual machines.
- Caas: Comput as a Service.
- Vertical Scaling

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