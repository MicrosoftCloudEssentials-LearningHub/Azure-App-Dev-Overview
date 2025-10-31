# Azure App Dev Services - Overview

Costa Rica

[![GitHub](https://img.shields.io/badge/--181717?logo=github&logoColor=ffffff)](https://github.com/) [brown9804](https://github.com/brown9804)

Last updated: 2025-08-04

----------------------

<details>
<summary><b>List of References</b> (Click to expand)</summary>

- [Azure Types of cloud computing](https://azure.microsoft.com/en-us/resources/cloud-computing-dictionary/types-of-cloud-computing/)
- [What is Azure Service Bus?](https://learn.microsoft.com/en-us/azure/service-bus-messaging/service-bus-messaging-overview)
- [Message sessions - First-in, first out (FIFO) pattern](https://learn.microsoft.com/en-us/azure/service-bus-messaging/message-sessions#first-in-first-out-fifo-pattern)

    <img width="788" height="443" alt="image" src="https://github.com/user-attachments/assets/7aa221fc-face-4860-919b-8207c99f4f00" />
    
- [Technology choices for Azure solutions](https://learn.microsoft.com/en-us/azure/architecture/guide/technology-choices/technology-choices-overview)

</details>


<details>
<summary><b>Table of Content</b> (Click to expand)</summary>

- [Types of cloud computing](#types-of-cloud-computing)
- [Event, Message, Stream](#event-message-stream)

</details>

## Types of cloud computing

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/4088401d-c4ec-4e6d-9236-01a0658a767f" />

| **Category**          | **Models & Details**                                                                                                                                                                                                                                                                                                                      |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Deployment Models** | -  **Private:** Dedicated infrastructure for one organization; high security and control.<br>-  **Public:** Services delivered over the internet; shared resources; cost-effective and scalable.<br>-  **Hybrid:** Combines private and public clouds; enables workload flexibility and optimization.                                        |
| **Service Models**    | -  **IaaS (Infrastructure as a Service):** Virtualized servers, storage, and networking; you manage OS and apps.<br>-  **PaaS (Platform as a Service):** Complete platform for app development and deployment; no infrastructure management.<br>-  **SaaS (Software as a Service):** Fully managed applications delivered over the internet. |

> Deployment Models & Azure Services

> [!TIP]
> - `Private Cloud`: Dedicated environment for one organization, `hosted on-premises or by a partner`, offering maximum control and compliance.
> - `Public Cloud`: Shared `infrastructure managed by a provider (like Azure)`, delivering scalability and cost efficiency for most workloads.
> - `Hybrid Cloud`: Combines `on-prem (private) and public cloud`, enabling flexibility for regulated data, disaster recovery, and gradual cloud adoption.

<details>
<summary> Private Cloud (Azure Stack) </summary>

-   **What:** Dedicated cloud environment for one organization, hosted on-prem or by a partner.
-   **Why:** Maximum control, security, and compliance for sensitive workloads.
-   **When to Use:**
    *   Regulatory compliance (finance, healthcare).
    *   Mission-critical apps requiring isolation.
-   **Azure Services:**
    *   Azure Stack Hub: Run Azure services in your own datacenter.
    *   Azure Arc: Manage hybrid resources with Azure governance.
-   **Integration Services:**
    *   API Management: Secure APIs for internal apps.
    *   Logic Apps: Automate workflows across on-prem and cloud.
-   **Industry Use Cases:**
    *   Healthcare: HIPAA-compliant patient data storage.
    *   Government: Classified workloads in isolated environments.

</details>

<details>
<summary>Public Cloud (Azure Global)</summary>

-   **What:** Services delivered over the internet, shared across customers.
-   **Why:** Cost-effective, scalable, and fast to deploy.
-   **When to Use:** Dynamic workloads, SaaS adoption, global reach.
-   **Azure Services:**
    *   Azure App Service: Host web apps without managing infrastructure.
    *   Azure Virtual Machines: Compute on demand.
    *   Azure Blob Storage: Scalable object storage.
-   **Integration Services:**
    *   Event Grid: Event-driven architecture for reactive apps.
    *   Service Bus: Reliable messaging between distributed systems.
    *   Event Hubs: Massive data ingestion for telemetry.
-   **Industry Use Cases:**
    *   Retail: E-commerce scaling during seasonal peaks.
    *   Media: Streaming platforms leveraging Azure CDN.

</details>

<details>
<summary>Hybrid Cloud (Azure Hybrid Solutions)</summary>

-   **What:** Combines private and public clouds for flexibility.
-   **Why:** Balance security with scalability; gradual cloud adoption.
-   **When to Use:** Legacy modernization, burst capacity needs.
-   **Azure Services:**
    *   Azure Arc: Unified management across on-prem and cloud.
    *   Azure ExpressRoute: Private connectivity to Azure.
    *   Azure Site Recovery: Disaster recovery for hybrid environments.
-   **Integration Services:**
    *   Logic Apps: Connect on-prem ERP with cloud CRM.
    *   Data Factory: ETL for hybrid data flows.
-   **Industry Use Cases:**
    *   Manufacturing: IoT data processed locally, analytics in Azure.
    *   Finance: Sensitive data on-prem, customer apps in public cloud.

</details>

> Service Models & Azure Services

> [!TIP]
> - **IaaS (Infrastructure as a Service):** Provides `virtualized compute, storage, and networking` resources. Example: Azure Virtual Machines, Virtual Network, Load Balancer.
> - **PaaS (Platform as a Service):** Offers a `managed platform for app development and deployment` without managing infrastructure. Example: Azure App Service, Azure Functions, Azure SQL Database, Azure SQL Managed Instance.
> - **SaaS (Software as a Service):** Delivers `fully managed applications over the internet` for productivity and business needs. Example: Microsoft 365, Dynamics 365, Power BI.


<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/24cff45a-6f9c-4cce-91d4-5dab402a83ef" />

Key foundational components in the traditional cloud service responsibility model: <br/>
`(On-prem → IaaS → PaaS → SaaS)`

> [!NOTE]
> They represent the major areas of control and management. However, `these 9 layers are conceptual, not exhaustive.`
> In reality, `there can be additional sub-layers or specialized services (e.g., security, identity, monitoring, compliance) that span across these layers.`

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/b4a4134b-c2e1-4d7f-ae19-e38a9448021e" />

> 1.  **Applications** → End-user software and business apps running on the platform.
> 2.  **Data** → Information stored, processed, and managed within the system.
> 3.  **Runtime** → Execution environment for applications (e.g., .NET, Java).
> 4.  **Middleware** → Software that connects apps and services (e.g., messaging, APIs).
> 5.  **Operating System (O/S)** → Core system software managing hardware and apps.
> 6.  **Virtualization** → Abstraction layer enabling multiple OS instances on hardware.
> 7.  **Servers** → Physical or virtual machines hosting workloads.
> 8.  **Storage** → Persistent data storage systems (disks, blobs, databases).
> 9.  **Networking** → Connectivity infrastructure for communication and data transfer.

<details>
<summary>IaaS (Infrastructure as a Service)</summary>

-   **What:** Virtualized compute, storage, networking.
-   **Azure Services:**
    *   Azure Virtual Machines
    *   Azure Virtual Network
    *   Azure Load Balancer
    *   **Developer Support:** Microsoft Dev Box (cloud dev environments)
-   **Integration Services:**
    *   Service Bus: Messaging between VMs and apps.
    *   Event Hubs: Streaming telemetry from VMs.
    *   API Management: Expose APIs from VM-hosted apps.
-   **Use Cases:** Lift-and-shift migrations, disaster recovery, custom environments, hosting legacy apps with API exposure.

</details>

<details>
<summary>PaaS (Platform as a Service)</summary>

-   **What:** Managed platform for app development and deployment.
-   **Azure Services:**
    *   Azure App Service: Host web apps and APIs.
    *   Azure Functions: Serverless compute for event-driven apps.
    *   Azure Container Apps: Microservices and containerized workloads.
    *   Azure Kubernetes Service (AKS): Container orchestration.
    *   Azure Spring Apps: Managed Spring Boot for Java.
    *   **Databases:**
        *   Azure SQL Database
        *   Azure SQL Managed Instance
-   **Integration Services:**
    *   Logic Apps: Automate workflows between PaaS apps.
    *   API Management: Secure and publish APIs.
    *   Event Grid: Event-driven architecture for apps.
    *   SignalR Service: Real-time communication for web apps.
-   **Use Cases:** Modern app development, microservices, rapid prototyping, event-driven apps, enterprise integration.

</details>

<details>
<summary>SaaS (Software as a Service)</summary>

-   **What:** Fully managed apps delivered over the internet.
-   **Azure Examples:**
    *   Microsoft 365: Productivity suite.
    *   Dynamics 365: CRM and ERP.
    *   Fabric/Power BI: Analytics and visualization.
    *   Power Platform: Low-code app development (Power Apps, Power Automate, Copilot Studio).
-   **Integration Services:**
    *   Logic Apps: Connect SaaS apps with ERP/CRM.
    *   Event Grid: Trigger workflows from SaaS events.
    *   API Management: Extend SaaS capabilities via APIs.
-   **Use Cases:** Productivity tools, CRM, analytics, low-code/no-code app development.

</details>

> [!NOTE]
> - **Control decreases as you move from On-premises → IaaS → PaaS → SaaS.**
> - Trade-off: **More convenience = Less control.**
> -   Choose based on:
>     *   **IaaS:** When you need OS-level control.
>     *   **PaaS:** When you want to focus on app development.
>     *   **SaaS:** When you want zero infrastructure management.

## Event, Message, Stream

> [!TIP]
> -  **Event (Event Grid)** → Best for **lightweight notifications** and **reactive architectures**.
> - **Message (Service Bus)** → Use when you need **guaranteed delivery**, **ordering**, or **transactional integrity**.
> - **Stream (Event Hubs)** → Ideal for **high-throughput streaming** scenarios like **IoT telemetry** or **real-time analytics**.

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/c9005aac-1014-41d2-85bc-ae7327b87bf2" />

| **Aspect**          | **Event**                                                                                                              | **Message** | **Stream** |
| ------------------- | ------------------------------------------------------------------ | ------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| **Definition**      | Lightweight notification that something happened; does **not** carry full business data.                               | Data packet intended for processing; often contains business-critical info with guaranteed delivery. | Continuous flow of data for real-time processing and analytics.                                                 |
| **Characteristics** | - Fire-and-forget (basic retries only)<br>- Reactive architectures<br>- Small payload (metadata)                       | - Durable storage until processed<br>- Supports sessions, transactions, DLQs<br>- Larger payloads | - High-throughput ingestion<br>- Partitioned for scalability<br>- Designed for streaming scenarios              |
| **Azure Service**   | **Event Grid**: Routes events from sources (Blob Storage, IoT Hub) to subscribers (Functions, Logic Apps).             | **Service Bus**: Enterprise messaging with FIFO, sessions, and reliability. | **Event Hubs**: Ingest millions of events per second for telemetry and analytics.                               |
| **Use Cases**       | - Trigger workflows when a file is uploaded<br>- Notify downstream systems of state changes<br>- Fan-out notifications | - Order processing in e-commerce<br>- Payment workflows requiring guaranteed delivery<br>- Microservice communication with transactional integrity | - IoT telemetry ingestion<br>- Real-time analytics pipelines<br>- Streaming data to Azure Synapse or Databricks |

## Azure App Dev Services 

> Click here to read more about [Technology choices for Azure solutions](https://learn.microsoft.com/en-us/azure/architecture/guide/technology-choices/technology-choices-overview)

<img width="450" alt="image" src="https://github.com/user-attachments/assets/0713d101-94ef-40a9-9e55-0a780036ce7a" />

### Choose a compute service

> This diagram is a **decision-making guide for selecting the right Azure compute service**. It helps you determine the best option based on whether you are **migrating an existing workload** or **building a new application**. The flow considers factors like cloud optimization, containerization, orchestration needs, and control requirements.

<img width="900" height="916" alt="image" src="https://github.com/user-attachments/assets/fb6daaa9-50c2-4e9b-8195-e5f144ac63d2" />

From [Choose an Azure compute service](https://learn.microsoft.com/en-us/azure/architecture/guide/technology-choices/compute-decision-tree)

<details>
<summary>Migration Path Explained</summary>

> When migrating workloads, the first question is whether the application is **already optimized for the cloud**:

*   **If optimized:**
    *   Use **Azure App Service** for web applications.
    *   Use **Azure VMware Solution** for VMware-based workloads.

*   **If not optimized:**
    *   Check if the workload can be **containerized**:
        *   **Yes:** Choose orchestration solutions like:
            *   **VMware Tanzu on Azure VMs**
            *   **Kubernetes on Azure VMs**
            *   **OpenShift on Azure VMs**
        *   **No:** Use **Virtual Machines** for a lift-and-shift approach.

*   For VMware-specific workloads, **Azure VMware Solution** provides a seamless migration path.

</details>

<details>
<summary> Building New Applications Explained </summary>

> For new builds, start by asking if you need **full control**:

*   **Yes:**
    *   Use **Virtual Machines** for complete control.
    *   Use **Azure Batch** for HPC workloads.

*   **No:**
    *   Is the workload **event-driven** with short-lived processes?
        *   **Yes:** Use **Azure Functions** for serverless execution.
    *   Do you need **managed web hosting**?
        *   **Yes:** Use **Azure App Service**.
    *   Do you need **full orchestration**?
        *   **Yes:** Options include:
            *   **Azure Kubernetes Service (AKS)**
            *   **Azure Container Apps**
            *   **Azure Service Fabric**
            *   **Red Hat OpenShift**
        *   **No:** Use **Azure Container Instances** or **Azure Container Apps** for lightweight container hosting.

</details>

<details>
<summary>Service Categories</summary>

- **Container-exclusive services**: These services are designed specifically for containerized workloads and provide orchestration, scaling, and management capabilities tailored for containers:
    *   **Azure Container Instances (ACI):** A lightweight option for running containers without orchestration. Ideal for simple, isolated container tasks.
    *   **Azure Kubernetes Service (AKS):** A fully managed Kubernetes environment for complex container orchestration, scaling, and advanced workloads.
    *   **Azure Container Apps:** A serverless container platform for microservices and event-driven applications, with built-in autoscaling and Dapr integration.
    *   **VMware Tanzu on Azure VMs:** Enables Kubernetes-based container orchestration on Azure Virtual Machines using VMware Tanzu for hybrid and enterprise scenarios.
    *   **OpenShift on Azure VMs:** Provides Red Hat OpenShift capabilities on Azure infrastructure for organizations that prefer OpenShift for container orchestration.
- **Container-compatible services**: These services can run containerized workloads but are not exclusively designed for containers. They offer flexibility for mixed environments:
    *   **Azure Batch:** A compute service for large-scale parallel and HPC workloads. Supports containerized jobs for batch processing.
    *   **Azure Functions:** A serverless compute option for event-driven workloads. Can run containerized functions for portability and custom dependencies.
    *   **Azure App Service:** A managed platform for hosting web apps and APIs. Supports containerized deployments alongside traditional code-based apps.
    *   **Azure Service Fabric:** A distributed systems platform for microservices and containers, offering orchestration and lifecycle management for complex applications.

</details>

Choose an Azure compute option for microservices: 

> In summary, this flowchart helps developers choose between **AKS**, **Azure Container Apps**, and **Azure Functions** by evaluating factors like compute requirements, containerization, Kubernetes control, and workload type. It simplifies decision-making for modern cloud-native architectures.

<img width="983" height="500" alt="image" src="https://github.com/user-attachments/assets/dff4caed-52d9-429a-88cf-2af7de349906" />

From [Choose an Azure compute option for microservices](https://learn.microsoft.com/en-us/azure/architecture/microservices/design/compute-options)

> - This diagram is a **decision-making guide for selecting the right Azure compute service** based on application requirements. It starts with the question of whether your workload needs **dedicated compute resources** or can run in a **serverless environment**.
> - If **dedicated compute is required**, the next consideration is whether **GPU access** is needed. GPU requirements often indicate workloads like AI/ML or high-performance computing.
> - From there, the diagram asks if **Kubernetes API access** is necessary. If yes, the best choice is **Azure Kubernetes Service (AKS)**, which provides full Kubernetes orchestration and control. If Kubernetes API access is not needed, then **Azure Container Apps** is recommended for running containerized microservices without managing Kubernetes directly.
> - If **dedicated compute is not required**, the diagram moves toward **serverless options**. It checks if the workload is a **containerized microservice**. If yes, **Azure Container Apps** is suitable because it supports serverless containers with autoscaling. If not containerized, the next question is whether the workload is **code-based and non-containerized**. If yes, **Azure Functions** is the ideal choice for event-driven, serverless execution of small pieces of code.

### Choose a hybrid option

<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/cd933ab9-4085-4bc9-9896-c3b1c59c33c7" />

From [Hybrid solution decision tree](https://learn.microsoft.com/en-us/azure/architecture/guide/technology-choices/hybrid-considerations#hybrid-solution-decision-tree)
 
<!-- START BADGE -->
<div align="center">
  <img src="https://img.shields.io/badge/Total%20views-1532-limegreen" alt="Total views">
  <p>Refresh Date: 2025-10-23</p>
</div>
<!-- END BADGE -->
