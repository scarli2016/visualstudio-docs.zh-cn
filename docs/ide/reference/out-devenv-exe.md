---
title: -Out (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- errors [Visual Studio], builds
- Devenv, /out switch
- builds [Visual Studio], logs
- error logs [Visual Studio], command-line build errors
- error logs [Visual Studio]
- /out Devenv switch
- out Devenv switch
- builds [Visual Studio], errors
- output files, build errors
ms.assetid: 9002d8c2-36d4-451c-b489-8f01932f31f7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: af8d41a8a401e3087845e6d698163626f120a52e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="out-devenvexe"></a>/Out (devenv.exe)
指定一个文件，用于在运行、生成、重新生成或部署解决方案时存储和显示错误。  
  
## <a name="syntax"></a>语法  
  
```  
devenv /out FileName  
```  
  
## <a name="arguments"></a>自变量  
 `FileName`  
 必须的。 用于在生成可执行文件时接收错误的文件的路径和名称。  
  
## <a name="remarks"></a>备注  
 如果指定的文件名不存在，则会自动创建该文件。 如果该文件已存在，则结果会附加到该文件的现有内容中。  
  
 “命令”窗口中以及“输出”窗口的“解决方案生成器”视图中会显示命令行生成错误。 如果你正在运行无人参与的生成，并需要查看结果，则此选项非常有用。  
  
## <a name="example"></a>示例  
 此示例会运行 `MySolution`，并将错误写入文件 `MyErrorLog.txt` 中。  
  
```  
devenv /run "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /out "C:\MyErrorLog.txt"  
```  
  
## <a name="see-also"></a>请参阅  
 [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)   
 [/Run (devenv.exe)](../../ide/reference/run-devenv-exe.md)   
 [/Build (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/Deploy (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)