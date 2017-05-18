---
title: "选项，文本编辑器，所有语言，选项卡 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.ToolsOptionsPages.Text_Editor.ResJSON.Tabs"
  - "VS.ToolsOptionsPages.Text_Editor.JavaScript.Tabs"
  - "VS.ToolsOptionsPages.Text_Editor.All_Languages.Tabs"
helpviewer_keywords: 
  - "缩进，代码编辑器"
  - "代码编辑器，默认行为"
  - "选项卡，在代码编辑器中设置"
  - "“所有语言文本编辑器选项”对话框"
  - "编辑器，代码编辑器"
  - "代码编辑器，缩进"
  - "代码编辑器，选项卡"
ms.assetid: 7e208e1d-5e3a-4bf7-a27b-4417e3e049c7
caps.latest.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# 选项，文本编辑器，所有语言，选项卡
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

使用此对话框可以更改代码编辑器的默认行为。  这些设置也适用于其他基于代码编辑器的编辑器，如 HTML 设计器的“源”视图。  若要显示这些选项，请从**“工具”**菜单中选择**“选项”**。  在**“文本编辑器”**文件夹中展开**“所有语言”**子文件夹，再选择**“制表符”**。  
  
> [!CAUTION]
>  此页面设置所有开发语言的默认选项。  请注意，重置此对话框中的一个选项会将所有语言的“制表符”选项重置为在此处选择的任何选项。  若要只为一种语言更改文本编辑器选项，请展开该语言的子文件夹并选择其选项页。  
  
 如果在“制表符”选项页上为特定的编程语言选择了不同的设置，则对于不同的**“缩进”**选项，将显示消息“各种文本格式的缩进设置相互冲突”；对于不同的**“制表符”**选项，将显示消息“各种文本格式的制表符设置相互冲突”。  例如，如果为 Visual Basic 选择了**“智能缩进”**选项，但为 Visual C\+\+ 选择了**“块缩进”**，则会显示此提醒。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于您现用的设置或版本。  若要更改设置，请在**“工具”**菜单上选择**“导入和导出设置”**。  有关更多信息，请参见 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/zh-cn/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
## 缩进  
 无  
 选定后，新行不缩进。  插入点被置于一个新行的第一列。  
  
 块  
 选定后，新行自动缩进。  插入点被置于与上一行相同的起始点处。  
  
 智能  
 选定后，新行的放置依据开发语言的其他代码格式设置和 IntelliSense 约定以适应代码上下文。  此选项并不是对所有开发语言都可用。  
  
 例如，括在左括号 \({\) 和右括号 \(}\) 之间的行可能从对齐括号的位置自动缩进一个额外的制表位。  
  
## 制表符  
 制表符大小  
 设置制表位之间的距离（以空格数表示）。  默认值为四个空格。  
  
 缩进大小  
 设置自动缩进的大小（以空格数表示）。  默认值为四个空格。  插入制表符、空格字符或同时插入二者以填充指定的大小。  
  
 插入空格  
 选定后，缩进操作只插入空格字符，而不插入制表符。  例如，如果**“缩进大小”**设置为 5，则无论是按 Tab 还是按**“格式”**工具栏上的**“增加缩进”**按钮，都会插入五个空格字符。  
  
 保留制表符  
 选定后，缩进操作会尽可能多地插入制表符。  每个制表符都会填充在“制表符大小”中指定的空格数。  如果**“缩进大小”**不是**“制表符大小”**的偶数倍，则会添加空格字符以填充差额。  
  
## 请参阅  
 [选项、文本编辑器、所有语言](../../ide/reference/options-text-editor-all-languages.md)   
 [“选项”对话框 \-\>“环境”\-\>“常规”](../../ide/reference/general-environment-options-dialog-box.md)