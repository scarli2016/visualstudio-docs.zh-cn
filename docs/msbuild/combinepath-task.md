---
title: "CombinePath 任务 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CombinePath task
- CombinePath task [MSBuild]
ms.assetid: c20edbf4-3d4f-4f66-b1d5-753a0d858ed8
caps.latest.revision: 7
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: a6fb322adceef7947cbb671d04e72169e06f74a7
ms.lasthandoff: 02/22/2017

---
# <a name="combinepath-task"></a>CombinePath 任务
将指定路径合并到单个路径。  
  
## <a name="task-parameters"></a>任务参数  
 下表描述了 [CombinePath 任务](../msbuild/combinepath-task.md)的参数。  
  
|参数|描述|  
|---------------|-----------------|  
|`BasePath`|必选 `String` 参数。<br /><br /> 与其他路径组合的基路径。 可以是相对路径、绝对路径或空白。|  
|`Paths`|所需的 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 参数。<br /><br /> 要与 BasePath 组合成组合路径的各个路径的列表。 路径可以是相对路径，也可以是绝对路径。|  
|`CombinedPaths`|可选的 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 输出参数。<br /><br /> 由此任务创建的组合路径。|  
  
## <a name="remarks"></a>备注  
 除了上面列出的参数，此任务还从 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数，此类本身继承自 <xref:Microsoft.Build.Utilities.Task> 类。 有关这些其他参数及其说明的列表，请参阅 [TaskExtension 基类](../msbuild/taskextension-base-class.md)。  
  
## <a name="see-also"></a>另请参阅  
 [任务](../msbuild/msbuild-tasks.md)   
 [任务参考](../msbuild/msbuild-task-reference.md)