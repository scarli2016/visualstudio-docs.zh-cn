---
title: '&lt;formRegion&gt;元素 （Visual Studio 中的 Office 开发） |Microsoft 文档'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <formRegion> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: af7dd4f3472692def9f05a937297d54d13c6f0d6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="ltformregiongt-element-office-development-in-visual-studio"></a>&lt;formRegion&gt;元素 （Visual Studio 中的 Office 开发）
  `formRegion` 命名空间的 `vstov4` 元素标识与 VSTO 外接程序关联的 Microsoft Office Outlook 窗体区域。  
  
## <a name="syntax"></a>语法  
  
```  
<formRegion  
  name>  
  <messageClass  
    name/>  
</formRegion>  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 `formRegion` 命名空间的 `vstov4` 元素标识与 Outlook VSTO 外接程序关联的窗体区域。 只有包括窗体区域的 Outlook VSTO 外接程序才需要该元素。  
  
 单个 VSTO 外接程序的一个 `formRegion` 元素中可以定义多个 `formRegions` 元素。  
  
 `formRegion` 元素具有以下属性。  
  
|特性|描述|  
|---------------|-----------------|  
|`name`|必须的。 标识窗体区域名称。|  
  
 `formRegion` 元素具有以下子元素。  
  
### <a name="messageclass"></a>messageClass  
 `messageClass` 元素标识与窗体区域关联的 Outlook 窗体。  
  
 `messageClass` 元素具有以下属性。  
  
|特性|描述|  
|---------------|-----------------|  
|`name`|必须的。 标识与窗体区域关联的窗体。|  
  
## <a name="example"></a>示例  
 下面的代码示例阐释 Outlook VSTO 外接程序的应用程序清单中的 `formRegion` 元素，该外接程序是使用 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]部署的。 其中有三个邮件类与这一个窗体区域关联。 此代码示例摘自 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)中提供的一个更大的示例。  
  
```  
<vstov4:formRegion  
    name="OutlookAddIn1.FormRegion1">  
  <vstov4:messageClass name="IPM.Note" />  
  <vstov4:messageClass name="IPM.Contact" />  
  <vstov4:messageClass name="IPM.Appointment" />  
</vstov4:formRegion>  
```  
  
## <a name="see-also"></a>请参阅  
 [创建 Outlook 窗体区域](../vsto/creating-outlook-form-regions.md)   
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Office 解决方案的部署清单](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 应用程序清单](/visualstudio/deployment/clickonce-application-manifest)  
  
  