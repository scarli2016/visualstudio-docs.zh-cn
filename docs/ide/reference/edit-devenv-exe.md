---
title: -/Edit (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Devenv, /edit switch
- /Edit Devenv swtich
ms.assetid: 02b3d6e7-a2b1-4d83-a747-aa8c2fb758b7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 47db943d60abc23447aa579e85377a00cf551cae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="edit-devenvexe"></a>/Edit (devenv.exe)
在 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 的现有实例中打开指定文件。  
  
## <a name="syntax"></a>语法  
  
```  
Devenv /edit [file1[ file2]]  
```  
  
## <a name="arguments"></a>自变量  
 `file1`  
 可选。 要在 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 的现有实例中打开的文件。 如果不存在 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 的实例，使用简化窗口布局创建新实例，并在新实例中打开 `file1`。  
  
 `file2`  
 可选。 要在 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 的现有实例中打开的一个或多个其他文件。  
  
## <a name="remarks"></a>备注  
 如果未指定文件但存在 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 的现有实例，[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 的现有实例会接收焦点。 如果未指定文件但存在 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 的现有实例，会通过简化窗口布局创建 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 的新实例。  
  
 如果 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 的现有实例处于模式状态，例如，如果[选项对话框](../../ide/reference/options-dialog-box-visual-studio.md)是打开状态，文件将在 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 退出模式状态时在现有实例中打开。  
  
## <a name="example"></a>示例  
 此示例在 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 的现有实例中打开文件 `MyFile.cs` 或在 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 的新实例中打开文件（如果没有现有实例）。  
  
```  
devenv /edit MyFile.cs  
```  
  
## <a name="see-also"></a>请参阅  
 [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)