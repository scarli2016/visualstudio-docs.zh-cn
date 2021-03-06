---
title: "如何：禁用托管进程 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- hosting process, disabling
- vshost.exe, disabling the hosting process
ms.assetid: 9157488d-737f-454b-8d8d-36f99de38bb0
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b43e285c35601cb0d50536a5f4c499d09ae9bbad
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-disable-the-hosting-process"></a>How to: Disable the Hosting Process
启用承载进程时可能会影响对某些 API 的调用。 在这些情况下，必须禁用托管进程以返回正确的结果。  
  
### <a name="to-disable-the-hosting-process"></a>禁用托管进程  
  
1.  在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 中打开可执行项目。 不会生成可执行文件的项目（例如，类库或服务项目）没有此选项。  
  
2.  在“项目”菜单上，单击“属性”。  
  
3.  单击“调试”选项卡。  
  
4.  清除“启用 Visual Studio 托管进程”复选框。  
  
 禁用托管进程时，几种调试功能会不可用或性能下降。 有关详细信息，请参阅[调试和承载进程](../debugger/debugging-and-the-hosting-process.md)。  
  
 一般情况下，禁用托管进程时：  
  
-   开始调试 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 应用程序需要的时间会增长。  
  
-   设计时表达式计算不可用。  
  
-   部分信任调试不可用。  
  
## <a name="see-also"></a>请参阅

[调试和承载进程](../debugger/debugging-and-the-hosting-process.md)   
[承载进程 (vshost.exe)](../ide/hosting-process-vshost-exe.md)