---
title: include file
description: include file
services: data-factory
author: chez-charlie
ms.service: data-factory
ms.topic: include
ms.date: 09/21/2021
ms.author: chez
ms.custom: include file
---

Azure Data Factory is a multitenant service that has the following default limits in place to make sure customer subscriptions are protected from each other's workloads. To raise the limits up to the maximum for your subscription, contact support.

### Version 2

| Resource | Default limit | Maximum limit |
| -------- | ------------- | ------------- |
| Total number of entities, such as pipelines, data sets, triggers, linked services, Private Endpoints, and integration runtimes, within a data factory | 5,000 | [Find out how to request a quota increase from support](https://azure.microsoft.com/blog/azure-limits-quotas-increase-requests/). |
| Total CPU cores for Azure-SSIS Integration Runtimes under one subscription | 64 | [Find out how to request a quota increase from support](https://azure.microsoft.com/blog/azure-limits-quotas-increase-requests/). |
| Concurrent pipeline runs per data factory that's shared among all pipelines in the factory | 10,000  | 10,000 |
| Concurrent External activity runs per subscription per [Azure Integration Runtime region](../articles/data-factory/concepts-integration-runtime.md#azure-ir-location)<br><small>External activities are managed on integration runtime but execute on linked services, including Databricks, stored procedure, Web, and others. This limit does not apply to Self-hosted IR.</small> | 3,000 | 3,000 |
| Concurrent Pipeline activity runs per subscription per [Azure Integration Runtime region](../articles/data-factory/concepts-integration-runtime.md#azure-ir-location) <br><small>Pipeline activities execute on integration runtime, including Lookup, GetMetadata, and Delete. This limit does not apply to Self-hosted IR.</small> | 1,000 | 1,000                                                        |
| Concurrent authoring operations per subscription per [Azure Integration Runtime region](../articles/data-factory/concepts-integration-runtime.md#azure-ir-location)<br><small>Including test connection, browse folder list and table list, preview data. This limit does not apply to Self-hosted IR.</small> | 200 | 200                                                          |
| Concurrent Data Integration Units<sup>1</sup> consumption per subscription per [Azure Integration Runtime region](../articles/data-factory/concepts-integration-runtime.md#integration-runtime-location)| Region group 1<sup>2</sup>: 6,000<br>Region group 2<sup>2</sup>: 3,000<br>Region group 3<sup>2</sup>: 1,500 | Region group 1<sup>2</sup>: 6,000<br/>Region group 2<sup>2</sup>: 3,000<br/>Region group 3<sup>2</sup>: 1,500 |
| Concurrent Data Integration Units<sup>1</sup> consumption per subscription per [Azure Integration Runtime region](../articles/data-factory/concepts-integration-runtime.md#integration-runtime-location) in managed virtual network|  2,400 | [Find out how to request a quota increase from support](https://azure.microsoft.com/blog/azure-limits-quotas-increase-requests/). |
| Maximum activities per pipeline, which includes inner activities for containers | 40 | 40 |
| Maximum number of linked integration runtimes that can be created against a single self-hosted integration runtime | 100 | 100 |
| Maximum number of node that can be created against a single self-hosted integration runtime | 4 | [Find out how to request a quota increase from support](https://azure.microsoft.com/blog/azure-limits-quotas-increase-requests/). |
| Maximum parameters per pipeline | 50 | 50 |
| ForEach items | 100,000 | 100,000 |
| ForEach parallelism | 20 | 50 |
| Maximum queued runs per pipeline | 100 | 100 |
| Characters per expression | 8,192 | 8,192 |
| Minimum tumbling window trigger interval | 5 min | 15 min |
| Maximum timeout for pipeline activity runs | 7 days | 7 days |
| Bytes per object for pipeline objects<sup>3</sup> | 200 KB | 200 KB |
| Bytes per object for dataset and linked service objects<sup>3</sup> | 100 KB | 2,000 KB |
| Bytes per payload for each activity run<sup>4</sup> | 896 KB | 896 KB |
| Data Integration Units<sup>1</sup> per copy activity run | 256 | 256 |
| Write API calls | 1,200/h | 1,200/h<br/><br/> This limit is imposed by Azure Resource Manager, not Azure Data Factory. |
| Read API calls | 12,500/h | 12,500/h<br/><br/> This limit is imposed by Azure Resource Manager, not Azure Data Factory. |
| Monitoring queries per minute | 1,000 | 1,000 |
| Maximum time of data flow debug session | 8 hrs | 8 hrs |
| Concurrent number of data flows per integration runtime | 50 | [Find out how to request a quota increase from support](https://azure.microsoft.com/blog/azure-limits-quotas-increase-requests/). |
| Concurrent number of data flows per integration runtime in managed vNet| 20 | [Find out how to request a quota increase from support](https://azure.microsoft.com/blog/azure-limits-quotas-increase-requests/). |
| Concurrent number of data flow debug sessions per user per factory | 3 | 3 |
| Data Flow Azure IR TTL limit | 4 hrs |  4 hrs |
| Meta Data Entity Size limit in a factory | 2 GB | [Find out how to request a quota increase from support](https://azure.microsoft.com/blog/azure-limits-quotas-increase-requests/). |

<sup>1</sup> The data integration unit (DIU) is used in a cloud-to-cloud copy operation, learn more from [Data integration units (version 2)](../articles/data-factory/copy-activity-performance.md#data-integration-units). For information on billing, see [Azure Data Factory pricing](https://azure.microsoft.com/pricing/details/data-factory/).

<sup>2</sup> [Azure Integration Runtime](../articles/data-factory/concepts-integration-runtime.md#azure-integration-runtime) is [globally available](https://azure.microsoft.com/global-infrastructure/services/) to ensure data compliance, efficiency, and reduced network egress costs. 

| Region group | Regions |
| -------- | ------ |
| Region group 1 | Central US, East US, East US 2, North Europe, West Europe, West US, West US 2 |
| Region group 2 | Australia East, Australia Southeast, Brazil South, Central India, Japan East, North Central US, South Central US, Southeast Asia, West Central US |
| Region group 3 | Other regions |

If managed virtual network is enabled, the data integration unit (DIU) in all region groups are 2,400.

<sup>3</sup> Pipeline, data set, and linked service objects represent a logical grouping of your workload. Limits for these objects don't relate to the amount of data you can move and process with Azure Data Factory. Data Factory is designed to scale to handle petabytes of data.

<sup>4</sup> The payload for each activity run includes the activity configuration, the associated dataset(s) and linked service(s) configurations if any, and a small portion of system properties generated per activity type. Limit for this payload size doesn't relate to the amount of data you can move and process with Azure Data Factory. Learn about the [symptoms and recommendation](../articles/data-factory/data-factory-troubleshoot-guide.md#payload-is-too-large) if you hit this limit.

### Version 1

| **Resource** | **Default limit** | **Maximum limit** |
| --- | --- | --- |
| Pipelines within a data factory |2,500 |[Find out how to request a quota increase from support](https://azure.microsoft.com/blog/azure-limits-quotas-increase-requests/). |
| Data sets within a data factory |5,000 |[Find out how to request a quota increase from support](https://azure.microsoft.com/blog/azure-limits-quotas-increase-requests/). |
| Concurrent slices per data set |10 |10 |
| Bytes per object for pipeline objects<sup>1</sup> |200 KB |200 KB |
| Bytes per object for data set and linked service objects<sup>1</sup> |100 KB |2,000 KB |
| Azure HDInsight on-demand cluster cores within a subscription<sup>2</sup> |60 |[Find out how to request a quota increase from support](https://azure.microsoft.com/blog/azure-limits-quotas-increase-requests/). |
| Cloud data movement units per copy activity run<sup>3</sup> |32 |32 |
| Retry count for pipeline activity runs |1,000 |MaxInt (32 bit) |

<sup>1</sup> Pipeline, data set, and linked service objects represent a logical grouping of your workload. Limits for these objects don't relate to the amount of data you can move and process with Azure Data Factory. Data Factory is designed to scale to handle petabytes of data.

<sup>2</sup> On-demand HDInsight cores are allocated out of the subscription that contains the data factory. As a result, the previous limit is the Data Factory-enforced core limit for on-demand HDInsight cores. It's different from the core limit that's associated with your Azure subscription.

<sup>3</sup> The cloud data movement unit (DMU) for version 1 is used in a cloud-to-cloud copy operation, learn more from [Cloud data movement units (version 1)](../articles/data-factory/v1/data-factory-copy-activity-performance.md#cloud-data-movement-units). For information on billing, see [Azure Data Factory pricing](https://azure.microsoft.com/pricing/details/data-factory/).

| **Resource** | **Default lower limit** | **Minimum limit** |
| --- | --- | --- |
| Scheduling interval |15 minutes |15 minutes |
| Interval between retry attempts |1 second |1 second |
| Retry timeout value |1 second |1 second |

#### Web service call limits
Azure Resource Manager has limits for API calls. You can make API calls at a rate within the [Azure Resource Manager API limits](../articles/azure-resource-manager/management/azure-subscription-service-limits.md#resource-group-limits).
