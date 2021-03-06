---
title: 重构类和类型（类设计器）| Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.ClassDesigner.OverrideMembersDialog
helpviewer_keywords:
- members, overriding
- overriding members
- classes [Visual Studio], refactoring
- type members, overriding
- refactoring, types
- types [Visual Studio], refactoring
- Class Designer [Visual Studio], refactoring classes
- refactoring, classes
ms.assetid: dcf07bb4-fa3b-4224-9dec-566fd924a8ce
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d9f84c0b6fe661b480f13f03221360c8f7bc6583
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="refactoring-classes-and-types-class-designer"></a>重构类和类型（类设计器）

重构代码时，通过更改它的内部结构和它的对象的设计方式，而不是更改它的外部行为，你可以让它变得更易理解、维护以及更加高效。 在 Visual Studio 项目中重构 C#、Visual Basic 或 C++ 代码时，可以通过使用类设计器和类详细信息窗口来减少必要的工作量，并降低引入 bug 的几率。

> [!NOTE]
> 项目文件可能为只读类型，原因是这个项目受源代码管理且还未签出；它是一个引用项目；或它的文件在磁盘上被标记为只读。 当正在处理的项目处于这些状态中的某一状态时，可通过多种方式保存工作，具体取决于项目的状态。 这种情况适用于重构代码，也适用于通过其他方法（如直接编辑代码）更改的代码。

## <a name="common-tasks"></a>常规任务  
  
|任务|支持内容|  
|----------|------------------------|  
|**重构类：** 可以通过重构操作将类拆分为分部类或实现抽象基类。|-   [如何：将类拆分为分部类](how-to-split-a-class-into-partial-classes.md)|  
|**使用接口：** 在类设计器中，可以在类图上实现接口，方法是将它连接到为接口方法提供代码的类。|-   [如何：实现接口](how-to-implement-an-interface.md)|  
|**重构类型、类型成员和参数：** 通过使用类设计器，可以重命名类型、重写类型成员，或将它们从一种类型移动到另一种类型。 此外还可创建可以为 null 的类型。|-   [重命名类型和类型成员](refactoring-classes-and-types.md#RenamingTypesAndMembers)<br />-   [将类型成员从一个类型移到另一个类型](refactoring-classes-and-types.md#MovingTypeMembers)<br />-   [如何：创建可以为 Null 的类型](how-to-create-a-nullable-type.md)|  
  
###  <a name="RenamingTypesAndMembers"></a>重命名类型和类型成员  
在类设计器中，你可以在类图上或在属性窗口中重命名类型或类型成员。 在类详细信息窗口中，你可以更改成员名称但不能更改类型名称。 类型或类型成员的重命名将传播到所有的窗口和旧名称出现的代码位置。  
  
##### <a name="to-rename-a-name-in-the-class-designer"></a>在类设计器中重新命名  
  
1.  在类图上选择类型或成员，并单击名称。  
  
     成员名称变为可编辑状态。  
  
2.  为类型或类型成员键入新名称  
  
##### <a name="to-rename-a-name-in-the-class-details-window"></a>在类详细信息窗口中重新命名  
  
1.  如果要显示类详细信息窗口，右键单击类型或类型成员，然后单击“类详细信息” 。  
  
     这时将出现类详细信息窗口。  
  
2.  在“名称”  列中，更改类型成员名  
  
3.  如果要将焦点从单元格中移开，按 **“ENTER”** 键或单击该单元格即可。  
  
    > [!NOTE]
    >  在类详细信息窗口中，你可以更改成员名称但不能更改类型名称。  
  
##### <a name="to-rename-a-name-in-the-properties-window"></a>在属性窗口中进行重命名  
  
1.  在类图或类详细信息窗口上，右键单击类型或成员，然后单击“属性” 。  
  
     这时会出现属性窗口，并显示这一类型或类型成员的属性。  
  
2.  在“名称”  属性中，更改类型或类型成员的名称。  
  
     新名称将传播到所有的窗口和当前项目中旧名称出现的代码位置。  
  
###  <a name="MovingTypeMembers"></a> 将类型成员从一个类型移到另一个  
使用“类设计器” 可以将类型成员从一个类型移到另一个类型，前提是两个类型均在当前类图中可见。  
  
##### <a name="to-move-a-type-member-from-one-type-to-another"></a>将类型成员从一个类型移到另一个类型  
  
1.  在设计图面上可见的一个类型中，右键单击要移到另一个类型的成员，然后单击“剪切” 。  
  
2.  右键单击目标类型，然后单击“粘贴” 。  
  
     属性将从源类型中被移除，并出现在目标类型中。  
  
## <a name="see-also"></a>请参阅
[查看类型和关系](viewing-types-and-relationships.md)  
[设计类和类型](designing-classes-and-types.md)