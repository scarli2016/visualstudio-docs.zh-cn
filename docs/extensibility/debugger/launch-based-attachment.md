---
title: 启动基于附件 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, launching
- debug engines, attaching to programs
ms.assetid: 362f00ac-1909-4a3a-bacb-c0ceb5549816
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 892518cc92286f9415e39c96b6ed2afa8eb0d792
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="launch-based-attachment"></a>启动基于附件
自动启动基于附件添加到某个程序。 当托管该程序的进程由 SDM 启动时，启动基于附件遵循类似于手动附件方法的路径。 有关信息，请参阅[附加到程序](../../extensibility/debugger/attaching-to-the-program.md)。  
  
## <a name="the-attaching-process"></a>附加进程  
 主要区别是以下事件的顺序**附加**调用，，如下所示：  
  
1.  发送**IDebugEngineCreateEvent2**到 SDM 事件对象。 有关详细信息，请参阅[发送事件](../../extensibility/debugger/sending-events.md)。  
  
2.  调用`IDebugProgram2::GetProgramId`方法**IDebugProgram2**接口传递到**附加**方法。  
  
3.  发送**IDebugProgramCreateEvent2**事件对象，以通知 SDM，本地**IDebugProgram2**创建对象来表示 DE 到的程序。  
  
4.  发送[IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md)事件对象，以通知 SDM 启动的进程会创建新线程。  
  
## <a name="see-also"></a>另请参阅  
 [发送所需的事件](../../extensibility/debugger/sending-the-required-events.md)   
 [启用要进行调试的程序](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)