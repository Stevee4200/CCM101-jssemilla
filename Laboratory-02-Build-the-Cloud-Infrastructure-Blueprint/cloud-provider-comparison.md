# Cloud Provider Comparison

## Comparison of Core Cloud Infrastructure Services

## Introduction

The three leading public cloud providers—AWS, Microsoft Azure, and Google Cloud Platform (GCP)—offer similar infrastructure services under different names. Although their service names and interfaces differ, all three provide resources for computing, storage, networking, and identity and access management.

## Cloud Service Comparison

| Infrastructure Component                 | AWS                                      | Microsoft Azure                 | Google Cloud Platform (GCP) |
| ---------------------------------------- | ---------------------------------------- | ------------------------------- | --------------------------- |
| **Compute**                              | Amazon EC2                               | Azure Virtual Machines          | Compute Engine              |
| **Storage**                              | Amazon S3                                | Azure Blob Storage              | Cloud Storage               |
| **Networking**                           | Amazon VPC                               | Azure Virtual Network (VNet)    | Virtual Private Cloud (VPC) |
| **Identity and Access Management (IAM)** | AWS Identity and Access Management (IAM) | Microsoft Entra ID / Azure RBAC | Google Cloud IAM            |

Amazon EC2 provides virtual servers for computing, while Amazon S3 provides object storage. Amazon VPC creates logically isolated virtual networks, and AWS IAM controls access to AWS resources through identities, roles, and permissions.

The equivalent services from Azure are Azure Virtual Machines for compute, Azure Blob Storage for object storage, Azure Virtual Network for networking, and Microsoft Entra ID together with Azure role-based access control for identity and permissions.

For GCP, Compute Engine provides virtual machine resources, Cloud Storage provides storage, Virtual Private Cloud provides networking, and Google Cloud IAM manages identities, roles, permissions, and access to cloud resources.

---

## Guide Questions

### 1. Which cloud provider offers the broadest range of services? Explain your answer.

AWS is generally considered to offer one of the broadest ranges of cloud services and has a large ecosystem covering compute, storage, databases, networking, security, analytics, AI, and many other areas. AWS provides many specialized services in addition to its core infrastructure offerings.

### 2. Which cloud platform would you recommend for an organization that primarily uses Microsoft products? Why?

I would recommend **Microsoft Azure** for an organization that primarily uses Microsoft products. Azure integrates well with Microsoft technologies and services, making it a practical choice for organizations that already use Windows Server, Microsoft 365, Active Directory, and other Microsoft products.

### 3. Which platform is widely recognized for Artificial Intelligence (AI), Machine Learning (ML), and Kubernetes services?

**Google Cloud Platform (GCP)** is widely recognized for its strengths in Artificial Intelligence, Machine Learning, and Kubernetes. Google developed Kubernetes, and GCP provides services such as Google Kubernetes Engine (GKE) and various AI and machine learning tools.

### 4. What similarities did you observe among the three cloud providers?

All three cloud providers offer the same basic categories of cloud infrastructure, including compute, storage, networking, and identity and access management. The main difference is usually the service name, interface, and specific features, but they all allow organizations to build, manage, secure, and scale cloud-based applications.

---

## Conclusion

AWS, Microsoft Azure, and Google Cloud Platform provide similar core cloud infrastructure services even though they use different names. Understanding the equivalent services helps cloud engineers transfer their knowledge between platforms and choose the most appropriate provider based on an organization's existing technology, requirements, and goals.

## Official Resources

### Amazon Web Services (AWS)

* [AWS Official Website](https://aws.amazon.com/?utm_source=chatgpt.com)
* [Amazon EC2 Documentation](https://docs.aws.amazon.com/ec2/?utm_source=chatgpt.com)
* [Amazon S3 Documentation](https://docs.aws.amazon.com/s3/?utm_source=chatgpt.com)
* [Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/?utm_source=chatgpt.com)


### Microsoft Azure

* [Microsoft Azure Official Website](https://azure.microsoft.com/?utm_source=chatgpt.com)
* [Azure Virtual Machines Documentation](https://learn.microsoft.com/azure/virtual-machines/?utm_source=chatgpt.com)
* [Azure Blob Storage Documentation](https://learn.microsoft.com/azure/storage/blobs/?utm_source=chatgpt.com)
* [Azure Virtual Network Documentation](https://learn.microsoft.com/azure/virtual-network/?utm_source=chatgpt.com)

### Google Cloud Platform (GCP)

* [Google Cloud Official Website](https://cloud.google.com/?utm_source=chatgpt.com)
* [Compute Engine Documentation](https://cloud.google.com/compute/docs?utm_source=chatgpt.com)
* [Cloud Storage Documentation](https://cloud.google.com/storage/docs?utm_source=chatgpt.com)
* [Virtual Private Cloud (VPC) Documentation](https://docs.cloud.google.com/vpc/docs?utm_source=chatgpt.com)

## Tools and Assistance

### Tools Used

* **KillerCoda** – Used to access and explore the Linux environment and practice basic cloud and Linux concepts.
* **GitHub** – Used for repository hosting, version control, and organizing laboratory files.
* **Web Browser and Search Tools** – Used to research and access the official documentation of AWS, Microsoft Azure, and Google Cloud.

### Assistance and Resources

* **Official AWS Documentation** – Used to identify and understand services such as Amazon EC2, Amazon S3, Amazon VPC, and AWS IAM.
* **Microsoft Learn** – Used to research Azure Virtual Machines, Azure Blob Storage, Azure Virtual Network, Microsoft Entra ID, and Azure RBAC.
* **Google Cloud Documentation** – Used to identify equivalent Google Cloud services, including Compute Engine, Cloud Storage, VPC, and Google Cloud IAM.
* **ChatGPT** – Used as an assistance tool to help organize the comparison, improve the Markdown formatting, explain cloud infrastructure concepts, and structure the report.


## References

Amazon Web Services. (n.d.). *Amazon EC2 documentation*. AWS Documentation. [AWS Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/security-iam.html?utm_source=chatgpt.com)

Amazon Web Services. (n.d.). *Amazon S3 documentation*. AWS Documentation. [AWS Documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/security-iam.html?utm_source=chatgpt.com)

Amazon Web Services. (n.d.). *Amazon Virtual Private Cloud documentation*. AWS Documentation. [AWS Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/security-iam.html?utm_source=chatgpt.com)

Amazon Web Services. (n.d.). *AWS Identity and Access Management documentation*. AWS Documentation. [AWS Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/security-iam.html?utm_source=chatgpt.com)

Google Cloud. (n.d.). *Compute Engine documentation*. Google Cloud Documentation. [Google Cloud Documentation](https://docs.cloud.google.com/compute/docs/authentication?hl=en&utm_source=chatgpt.com)

Google Cloud. (n.d.). *Identity and Access Management documentation*. Google Cloud Documentation. [Google Cloud Documentation](https://docs.cloud.google.com/compute/docs/access/iam?hl=en&utm_source=chatgpt.com)

Microsoft. (n.d.). *Authorize access to blobs using Microsoft Entra ID*. Microsoft Learn. [Microsoft Learn](https://learn.microsoft.com/en-us/azure/storage/blobs/authorize-access-azure-active-directory?utm_source=chatgpt.com)

Microsoft. (n.d.). *Azure built-in roles for compute*. Microsoft Learn. [Microsoft Learn](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles/compute?utm_source=chatgpt.com)
