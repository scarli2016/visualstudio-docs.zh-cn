---
title: IDiaStackWalkFrame |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame interface
ms.assetid: 42d82845-d6f6-4846-9ecd-9dd169216077
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f16d6f824b3b150406c23cce87e186fe9b120999
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="idiastackwalkframe"></a>IDiaStackWalkFrame
可维护的调用之间的堆栈上下文[idiaframedata:: Execute](../../debugger/debug-interface-access/idiaframedata-execute.md)方法。  
  
## <a name="syntax"></a>语法  
  
```  
IDiaStackWalkFrame : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDiaStackWalkFrame`。  
  
|方法|描述|  
|------------|-----------------|  
|[IDiaStackWalkFrame::get_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-get-registervalue.md)|检索寄存器的值。|  
|[IDiaStackWalkFrame::put_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-put-registervalue.md)|设置寄存器的值。|  
|[IDiaStackWalkFrame::readMemory](../../debugger/debug-interface-access/idiastackwalkframe-readmemory.md)|从映像进行读取内存。|  
|[IDiaStackWalkFrame::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddress.md)|搜索指定的堆栈帧接近函数寄信人地址。|  
|[IDiaStackWalkFrame::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddressstart.md)|搜索指定的堆栈帧的寄信人地址处或附近指定的地址。|  
  
## <a name="remarks"></a>备注  
 在程序执行期间使用此接口来读取和写入寄存器，以及访问内存和查找返回地址。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 客户端应用程序实现此接口，并将传递到接口的实例[idiaframedata:: Execute](../../debugger/debug-interface-access/idiaframedata-execute.md)方法。 此接口的同一个实例用于反复每次调用期间维持的状态的寄存器`execute`方法。 `execute`方法还使用此接口来确定的寄信人地址。  
  
## <a name="requirements"></a>要求  
 标头： Dia2.h  
  
 库： diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>请参阅  
 [接口 （调试接口访问 SDK）](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaFrameData::execute](../../debugger/debug-interface-access/idiaframedata-execute.md)