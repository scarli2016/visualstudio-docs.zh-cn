---
title: "保存和导出性能工具数据 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "性能工具, 保存和导出报告"
ms.assetid: 2e9b28fe-3ed2-4e1d-b9cb-0a5e384380b0
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 保存和导出性能工具数据
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

本主题介绍如何保存和导出性能数据文件。  
  
##  <a name="BKMK_Save_Profiler_Data_Files_As_Analyzed_Report_Files"></a> 如何：将性能数据文件另存为已分析的报告文件  
 可将分析数据 \(.vsp\) 文件的筛选后\/未筛选视图另存为已分析的报告 \(.vsps\) 文件。 已分析的报告文件可在报表视图窗口中查看，远远小于原始的 .vsp 文件。 但是，不能对 .vsps 文件的数据应用筛选器。 可以在性能资源管理器中创建已分析的报告文件，而无需在集成开发环境 \(IDE\) 中打开该文件，或者可打开并筛选 .vsp 文件再保存结果。  
  
#### 保存性能资源管理器中已分析的性能报告  
  
1.  在“报表”下，右键单击要分析的分析数据文件，然后单击“保存分析结果”。  
  
2.  在“保存分析数据”对话框中，指定目录，然后键入文件名。  
  
3.  单击“保存”。  
  
#### 保存报表视图窗口中已分析的性能报告  
  
1.  在报表视图窗口中打开分析数据 \(.vsp\) 文件。  
  
2.  （可选）对数据应用筛选器。 有关详细信息，请参阅[分析工具报告视图筛选器](../profiling/performance-report-view-filter.md)。  
  
3.  单击报表视图窗口工具栏上的“保存分析结果”。  
  
4.  在“保存分析数据”对话框中，指定目录，然后键入文件名。  
  
5.  单击“保存”。  
  
## 如何：将分析工具报告导出到 Xml 或 Csv 文件  
 可以将 .vsp 文件或 .vsps 分析数据文件中的一个或多个报表视图导出为逗号分隔的文件或 XML 文件。 导出前，可在报表视图窗口中筛选数据，或者可从“性能资源管理器”窗口导出整个数据文件的报表视图。  
  
> [!NOTE]
>  还可将报表视图窗口内选中的行复制粘贴为制表符分隔值。  
  
#### 导出性能资源管理器窗口中的性能报告  
  
1.  在“性能资源管理器”中，选择报表，然后右键单击并选择“导出”。  
  
     将显示“导出报表”对话框。  
  
2.  选择想要导出的报表视图。  
  
3.  在“报告前缀为”下，指定想要添加到报告名称的前缀。  
  
4.  在“报告导出位置”下，指定目录。  
  
5.  在“报告导出格式”下，选择（逗号分隔）\(\*.csv\) 或 XML 数据 \(\*.xml\)。  
  
6.  单击“导出”。  
  
     每个报表视图都保存到名为 \<前缀\>\_\<报表视图名称\>.\<csv&#124;xml\> 的单独文件中  
  
#### 导出从报表视图窗口中的性能报告  
  
1.  在报表视图窗口中打开 .vsp 文件。  
  
2.  （可选）对数据应用筛选器。 有关详细信息，请参阅[分析工具报告视图筛选器](../profiling/performance-report-view-filter.md)。  
  
3.  单击报表视图窗口工具栏上的“导出报告”。  
  
4.  选择想要导出的报表视图。  
  
5.  在“报告前缀为”下，指定想要添加到报告名称的前缀。  
  
6.  在“报告导出位置”下，指定目录。  
  
7.  在“报告导出格式”下，选择（逗号分隔）\(\*.csv\) 或 XML 数据 \(\*.xml\)。  
  
8.  单击“导出”。  
  
     每个报表视图都保存到名为 \<前缀\>\_\<报表视图名称\>.\<csv&#124;xml\> 的单独文件中  
  
## 请参阅  
 [使用分析工具](../profiling/performance-explorer.md)   
 [对分析工具数据进行分析](../profiling/analyzing-performance-tools-data.md)   
 [比较分析工具数据文件](../profiling/comparing-performance-data-files.md)   
 [VSPerfReport](../profiling/vsperfreport.md)