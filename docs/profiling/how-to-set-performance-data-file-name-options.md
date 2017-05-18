---
title: "如何：设置分析数据文件名选项 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d7a8d6b9-ab23-46fb-98ed-774781157860
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 如何：设置分析数据文件名选项
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

默认情况下，将使用以下语法保存分析数据 \(.vsp\) 文件：  
  
 *路径\\VSP 文件\\YYMMDD\(N\)* **.vsp**  
  
 在性能会话属性对话框的“常规”页上，可以更改任意命名参数。  
  
 **要求**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
|||  
|-|-|  
|*路径*|包含报告的目录。  默认位置为解决方案文件夹或用户项目和解决方案的默认位置。|  
|*VSP 文件*|分析数据文件的名称。  默认名称是分析的解决方案或可执行文件的名称。|  
|*YYMMDD*|显示收集分析数据的年、月、日的日期戳。|  
|*\(N\)*|如果存在多个分析数据文件，文件名后会用括号加上递增的数字。|  
  
### 更改性能会话分析数据文件的命名语法  
  
1.  在**“性能资源管理器”**中，右击性能会话名称，然后单击**“属性”**。  
  
2.  单击**“常规”**。  
  
3.  在**“报告”**下更改下列任何设置：  
  
    |||  
    |-|-|  
    |**报告位置**|指定用于存储分析数据文件的目录。|  
    |**报告名称**|指定文件的基名称。|  
    |**自动向会话添加新报告**|选中该复选框会自动将数据文件添加到性能会话中。|  
    |**将一个递增的数字附加到生成的报告**|选中该复选框后，如果存在多个同名文件，文件名后会加上递增的数字。  清除该复选框会覆盖现有文件。|  
    |**在数字中使用时间戳**|选中该复选框会为文件名添加日期戳。|