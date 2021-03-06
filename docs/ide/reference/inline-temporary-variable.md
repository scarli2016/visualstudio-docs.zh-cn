---
title: 在 Visual Studio 中将临时变量替换为其值 | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 12cce111e3c66018cd10e7e50e9018dc9dbfc4d1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="inline-a-temporary-variable-refactoring"></a>“内联临时变量”重构

此重构适用于：

- C#

- Visual Basic

功能：删除临时变量并将其替换为其值。

时机：使用临时变量会使代码难以理解时。

原因：删除临时变量可使代码更易于理解。

## <a name="how-to"></a>操作说明

1. 突出显示要内联的临时变量，或将文本光标置于其中：

   - C#：

    ![突出显示的代码 - C#](media/inline-highlight-cs.png)

   - Visual Basic：

    ![突出显示的代码 - Visual Basic](media/inline-highlight-vb.png)

1. 接下来，执行以下操作之一：

   - **键盘**
     - 按“Ctrl”+**。** 触发“快速操作和重构”菜单。
   - **鼠标**
     - 右键单击代码，然后选择“快速操作和重构”菜单。

1. 从“预览”弹出窗口选择“内联临时变量”。

   将删除此变量，且在使用它的位置改用变量的值。

   - C#：

    ![内联结果 - C#](media/inline-result-cs.png)

   - Visual Basic：

    ![内联结果 - Visual Basic](media/inline-result-vb.png)

## <a name="see-also"></a>请参阅

[重构](../refactoring-in-visual-studio.md)