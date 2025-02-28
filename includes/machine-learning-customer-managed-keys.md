---
author: Blackmist
ms.service: machine-learning
ms.topic: include
ms.date: 03/02/2022
ms.author: larryfr
---

> [!IMPORTANT]
> The Cosmos DB instance is created in a Microsoft-managed resource group in __your subscription__. The following services are also created in this resource group, and are used by the customer-managed key configuration:
> * Azure Storage Account
> * Azure Search
>
> Since these services are created in your Azure subscription, it means that you are charged for these service instances. If your subscription does not have enough quota for the Azure Cosmos DB service, a failure will occur. For more information on quotas, see [Azure Cosmos DB service quotas](../articles/cosmos-db/concepts-limits.md)
>
> The managed resource group is named in the format `<AML Workspace Resource Group Name><GUID>`. If your Azure Machine Learning workspace uses a private endpoint, a virtual network is also created in this resource group. This VNet is used to secure communication between the services in this resource group and your Azure Machine Learning workspace.
> 
> * __Do not delete the resource group__ that contains this Cosmos DB instance, or any of the resources automatically created in this group. If you need to delete the resource group, Cosmos DB instance, etc., you must delete the Azure Machine Learning workspace that uses it. The resource group, Cosmos DB instance, and other automatically created resources are deleted when the associated workspace is deleted.
> * The  [__Request Units__](../articles/cosmos-db/request-units.md) used by this Cosmos DB account automatically scale as needed.
> * You __cannot provide your own VNet for use with the Cosmos DB instance__ that is created. You also __cannot modify the virtual network__. For example, you cannot change the IP address range that it uses.
> 
> To estimate the additional cost of the Azure Cosmos DB instance, use the [Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/).