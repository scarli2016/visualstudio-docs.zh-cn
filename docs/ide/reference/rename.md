---
title: 在 Visual Studio 中重构重命名 | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- vs.csharp.refactoring.rename
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 5735203131811b9423cd34f430665fb16a51ad34
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="rename-a-code-symbol-refactoring"></a>“重命名代码符号”重构

此重构适用于：

- C#

- Visual Basic

功能：重命名代码符号的标识符，例如字段、本地变量、方法、命名空间、属性和类型。

时机：想要安全地进行重命名（无需查找所有实例）并复制/粘贴新名称。

原因：复制和粘贴整个项目的新名称可能会导致错误。 此重构工具将准确地执行重命名操作。

## <a name="how-to"></a>操作说明

1. 突出显示要重命名的项，或将文本光标置于其中：

   - C#：

    ![突出显示的代码 - C#](media/rename-highlight-cs.png)

   - Visual Basic：

    ![突出显示的代码 - Visual Basic](media/rename-highlight-vb.png)

1. 接下来，执行以下操作之一：

   - **键盘**
     - 按“Ctrl+R”，然后按“Ctrl+R”。 （请注意，键盘快捷方式可能因所选的配置文件而有所不同。）
   - **鼠标**
     - 选择“编辑 > 重构 > 重命名”。
     - 右键单击代码并选择“重命名”。

1. 只需通过键入新名称即可重命名项。

   - C#：

    ![重命名动画 - C#](media/rename-animated-cs.gif)

   - Visual Basic：

    ![重命名 - VB](media/rename-rename-vb.png)

   > [!TIP]
   > 还可将注释和其他字符串更新为使用该新名称，也可在保存前使用“重命名”框（在编辑器的右上方）中的复选框[预览更改](../../ide/preview-changes.md)。

1. 对更改感到满意时，单击“应用”按钮或按 Enter 即可提交所做的更改。

> [!NOTE]
> 如果所用名称已存在（这可能导致冲突），“重命名”框将发出警告。
>
> ![重命名冲突](media/rename-conflict-cs.png)

## <a name="see-also"></a>请参阅

[重构](../refactoring-in-visual-studio.md)  
[预览更改](../../ide/preview-changes.md)
