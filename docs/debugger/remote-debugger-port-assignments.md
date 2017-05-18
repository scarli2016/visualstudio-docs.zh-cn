---
title: "远程调试器端口分配 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 238bb4ec-bb00-4c2b-986e-18ac278f3959
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# 远程调试器端口分配
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 远程调试器可作为应用程序或后台服务运行。 当它作为应用程序运行时，它将使用默认分配的端口，如下所示：  
  
-   Visual Studio 2015：4020  
  
-   Visual Studio 2013：4018  
  
-   Visual Studio 2012：4016  
  
 换而言之，分配给远程调试器的端口数每个版本递增 2。 你可以根据需要设置其他端口号。 我们将在后面部分说明如何设置端口号。  
  
## 32 位操作系统上的远程调试器端口  
 TCP 4020（在 Visual Studio 2015 中）是主端口，所有方案都必需。 你可以在命令行或远程调试器窗口中对此进行配置。  
  
 在远程调试器窗口中，单击“工具\/选项”，并设置 TCP\/IP 端口号。  
  
 在命令行中，通过 **\/port** 开关启动远程调试器：**msvsmon \/port \<端口号\>**.  
  
 你可以在远程调试帮助（在远程调试器窗口中按 **F1** 或单击“帮助\/用法”）中找到所有远程调试器命令行开关。  
  
## 64 位操作系统上的远程调试器端口  
 当启动 64 位版远程调试器时，它默认使用 4020 端口。  如果调试 32 位进程，则 64 位版远程调试器将在端口 4021 上启动 32 位版远程调试器。 如果运行 32 位远程调试器，它将使用 4020，而不使用 4021。  
  
 此端口可在命令行中进行配置：**Msvsmon \/wow64port \<端口号\>**。  
  
## 发现端口  
 UDP 3702 用于在网络上查找远程调试器的运行实例（例如，“附加到进程”对话框中的“查找”对话框）。 它仅用于发现运行远程调试器的计算机，因此如果你有某种其他方式来了解计算机名称或目标计算机的 IP 地址，它是可选的。 这是用于发现的标准端口，因此不能配置端口号。  
  
 如果你不想启用发现，可以在禁用发现的情况下从命令行启动 msvsmon：**Msvsmon \/nodiscovery**。  
  
## Azure 上的远程调试器端口  
 Azure 上的远程调试器使用以下端口。 云服务上的端口映射到各 VM 上的端口。 所有端口都是 TCP。  
  
||||  
|-|-|-|  
|**连接**|**云服务上的端口**|**VM 上的端口**|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Connector|30400|30398|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Forwarder|31400|31398|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.FileUpload|32400|32398|  
  
## 请参阅  
 [远程调试](../debugger/remote-debugging.md)