---
title: “计算语句”命令 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.evaluatestatement
helpviewer_keywords:
- Debug.EvaluateStatement command
- Evaluate Statement command
ms.assetid: 032039bc-9477-4f93-9b9d-66d4be0e90f4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fe960ec84830ce76095577f7d8ee2f0c9c4ccbe8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="evaluate-statement-command"></a>“计算语句”命令
计算并显示给定的语句。  
  
## <a name="syntax"></a>语法  
  
```  
Debug.EvaluateStatement text   
```  
  
## <a name="arguments"></a>自变量  
 `text`  
 必须的。 要评估的语句。  
  
## <a name="remarks"></a>备注  
 用于输入 EvaluateStatement 命令的窗口确定是将等号 (=) 解释为比较运算符还是赋值运算符。  
  
 在“命令”窗口中，将等号 (=) 解释为比较运算符。 例如，如果变量 `a` 和 `b` 的值不同，则命令  
  
```  
>Debug.EvaluateStatement(a=b)  
```  
  
 将返回 `false` 的值。  
  
 与此相反，在“即时”窗口中，将等号 (=) 解释为赋值运算符。 例如，命令  
  
```  
>Debug.EvaluateStatement(a=b)  
```  
  
 将为变量 `a` 赋予变量 `b` 的值。  
  
## <a name="example"></a>示例  
  
```  
>Debug.EvaluateStatement(a+b)  
```  
  
## <a name="see-also"></a>请参阅  
 [“打印”命令](../../ide/reference/print-command.md)   
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [“查找/命令”框](../../ide/find-command-box.md)   
 [Visual Studio 命令别名](../../ide/reference/visual-studio-command-aliases.md)