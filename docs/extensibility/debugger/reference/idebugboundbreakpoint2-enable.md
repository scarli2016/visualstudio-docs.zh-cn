---
title: "IDebugBoundBreakpoint2::Enable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugBoundBreakpoint2::Enable"
helpviewer_keywords: 
  - "Enable 方法"
  - "IDebugBoundBreakpoint2::Enable 方法"
ms.assetid: 1b4e3f73-c94d-4aa3-9aa8-0d8cb8a6c5ca
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugBoundBreakpoint2::Enable
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

启用或禁用断点。  
  
## 语法  
  
```cpp#  
HRESULT Enable(   
   BOOL fEnable  
);  
```  
  
```c#  
int Enable(   
   int fEnable  
);  
```  
  
#### 参数  
 `fEnable`  
 \[in\] 设置为非零 \(`TRUE`\) 启用或零 \(`FALSE`\) 禁用断点。  
  
## 返回值  
 如果成功，则返回; `S_OK`否则，返回错误代码。  返回 `E_BP_DELETED` ，如果绑定断点对象的状态设置为 `BPS_DELETED` \(的一部分 [BP\_STATE](../../../extensibility/debugger/reference/bp-state.md) 枚举\)。  
  
## 示例  
 下面的示例演示如何执行显示 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md) 接口的简单 `CBoundBreakpoint` 对象的方法。  
  
```  
HRESULT CBoundBreakpoint::Enable(BOOL fEnable)    
{    
   HRESULT hr;    
  
   // Verify that the bound breakpoint has not been deleted. If deleted,   
   // then return hr = E_BP_DELETED.    
   if (m_state != BPS_DELETED)    
   {    
      // Check the state of the bound breakpoint. If the breakpoint is  
      // supposed to be, but has not already been, enabled, then have the  
      // interpreter set the breakpoint.    
      if (fEnable && m_state != BPS_ENABLED)    
      {    
         hr = m_pInterp->SetBreakpoint(m_sbstrDoc, this);    
         if (hr == S_OK)    
         {    
            // Change the state of the breakpoint to BPS_ENABLED.    
            m_state = BPS_ENABLED;    
         }    
      }    
      // Check the state of the bound breakpoint. If the breakpoint is   
      // supposed to be, but has not already been, disabled, then have the   
      // interpreter remove the breakpoint.    
      else if (!fEnable && m_state != BPS_DISABLED)    
      {    
         hr = m_pInterp->RemoveBreakpoint(m_sbstrDoc, this);    
         if (hr == S_OK)    
         {    
            // Change the state of the breakpoint to BPS_DISABLED.    
            m_state = BPS_DISABLED;    
         }    
      }    
      else    
      {    
         hr = S_FALSE;    
      }    
   }    
   else    
   {    
      hr = E_BP_DELETED;    
   }    
  
   return hr;    
}    
```  
  
## 请参阅  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [BP\_STATE](../../../extensibility/debugger/reference/bp-state.md)