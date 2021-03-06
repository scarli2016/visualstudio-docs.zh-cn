---
title: Office 解决方案的应用程序清单 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e31eda8b1e3a1a0c311b35245f9b7690cc37aae0
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="application-manifests-for-office-solutions"></a>Office 解决方案的应用程序清单
  应用程序清单是一个 XML 文件，描述加载到 Microsoft Office 解决方案中的程序集。 Visual Studio 中的 Microsoft Office 开发工具使用 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 引用中定义的 [ndptecclick](/visualstudio/deployment/clickonce-application-manifest) 应用程序清单架构。  
  
 Office 解决方案的应用程序清单使用以下 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 元素和特性。  
  
|元素|描述|特性|  
|-------------|-----------------|----------------|  
|[&#60;程序集&#62;元素&#40;ClickOnce 应用程序&#41;](/visualstudio/deployment/assembly-element-clickonce-deployment)|必须的。 顶级元素。|`manifestVersion`|  
|[&#60;assemblyIdentity&#62;元素&#40;ClickOnce 应用程序&#41;](/visualstudio/deployment/assemblyidentity-element-clickonce-deployment)|必须的。 标识 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 应用程序的主程序集。|`name`<br /><br /> `version`<br /><br /> `publicKeyToken`<br /><br /> `processorArchitecture`<br /><br /> `language`|  
|[&#60;trustInfo&#62;元素&#40;ClickOnce 应用程序&#41;](/visualstudio/deployment/trustinfo-element-clickonce-application)|标识应用程序安全性要求。|无|  
|[&#60;入口点&#62;元素&#40;ClickOnce 应用程序&#41;](/visualstudio/deployment/entrypoint-element-clickonce-application)|必须的。 标识用于执行的应用程序代码入口点。|`name`<br /><br /> `dependencyName`<br /><br /> `customHostSpecified`|  
|[&#60;依赖项&#62;元素&#40;ClickOnce 应用程序&#41;](/visualstudio/deployment/dependency-element-clickonce-deployment)|必须的。 标识应用程序运行所需的每个依赖项。 （可选）标识需要进行预安装的程序集。|无|  
|[&#60;文件&#62;元素&#40;ClickOnce 应用程序&#41;](/visualstudio/deployment/file-element-clickonce-application)|必须的。 标识应用程序使用的每个非程序集文件。 可以包括与文件关联的组件对象模型 (COM) 隔离数据。|`name`<br /><br /> `size`|  
  
 Office 解决方案的应用程序清单具有 `co.v1` 命名空间中的以下元素。  
  
```  
<entryPoint>  
    <co.v1:customHostSpecified />  
</entryPoint>   
```  
  
 这些应用程序清单还具有 `vstav3` 命名空间中的以下元素和特性。  
  
```  
<addIn>  
  <entryPointsCollection>  
    <entryPoints>  
      <entryPoint>  
      </entryPoint>  
    </entryPoints>  
  </entryPointsCollection>  
  <update></update>  
  <postActions>  
    <postAction>  
      <postActionData>  
      </postActionData>  
    <postAction>  
  </postActions>  
  <application>  
    <customizations>  
      <customization>  
      </customization>  
    </customizations>  
  </application  
</addIn>  
```  
  
|元素|描述|特性|  
|-------------|-----------------|----------------|  
|[&#60;f i e d&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/customhostspecified-element-office-development-in-visual-studio.md)|必须的。 将清单专门标记为 Office 解决方案。|无|  
|[&#60;外接程序&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/addin-element-office-development-in-visual-studio.md)|必须的。 将入口点存储到单个命名空间。|无|  
|[&#60;entryPointsCollection&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/entrypointscollection-element-office-development-in-visual-studio.md)|必须的。 针对一个或多个 Office 解决方案对所有程序集进行分组。|`id`|  
|[&#60;入口点&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/entrypoints-element-office-development-in-visual-studio.md)|必须的。 对要运行 Office 解决方案的所有程序集进行分组。|无|  
|[&#60;入口点&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/entrypoint-element-office-development-in-visual-studio.md)|必须的。 标识要在 Office 解决方案中运行的程序集。|`class`<br /><br /> `contract`|  
|[&#60;更新&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/update-element-office-development-in-visual-studio.md)|必须的。 配置解决方案的更新。|`enabled`<br /><br /> `expiration`|  
|[&#60;postActions&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/postactions-element-office-development-in-visual-studio.md)|可选。 对在 Office 解决方案安装后运行的部署后操作进行分组。|无|  
|[&#60;o n&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/postaction-element-office-development-in-visual-studio.md)|可选。 标识部署后操作。|无|  
|[&#60;a t a&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/postactiondata-element-office-development-in-visual-studio.md)|可选。 配置部署后操作的数据。|无|  
|[&#60;应用程序&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/application-element-office-development-in-visual-studio.md)|必须的。 将特定于应用程序的信息包装到单个节点内。|无|  
|[&#60;自定义项&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/customizations-element-office-development-in-visual-studio.md)|必须的。 将所有的应用程序特定于宿主的信息存储在单独的命名空间内。|无|  
|[&#60;自定义&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/customization-element-office-development-in-visual-studio.md)|必须的。 将应用程序特定于宿主的信息存储在单独的命名空间内。|`xmlns`|  
|[&#60;文档&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/document-element-office-development-in-visual-studio.md)|仅针对文档级解决方案为必需。 存储特定于自定义的信息。|`solutionId`|  
|[&#60;appAddin&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/appaddin-element-office-development-in-visual-studio.md)|仅针对应用程序级解决方案为必需。 存储特定于自定义的信息。|`application`<br /><br /> `loadBehavior`<br /><br /> `keyName`|  
|[&#60;friendlyName&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/friendlyname-element-office-development-in-visual-studio.md)|可选。 存储显示在已安装的 VSTO 外接程序的列表中的 VSTO 外接程序的名称。|无|  
|[&#60;说明&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/description-element-office-development-in-visual-studio.md)|仅针对 VSTO 外接程序为必需。存储在已安装的程序的列表中出现的描述。|无|  
|[&#60;formRegions&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/formregions-element-office-development-in-visual-studio.md)|仅为包含窗体区域的 Outlook VSTO 外接程序所需。|无|  
|[&#60;formRegion&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/formregion-element-office-development-in-visual-studio.md)|仅为包含窗体区域的 Outlook VSTO 外接程序所需。|`Name`|  
|[&#60;vstoRuntime&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/vstoruntime-element-office-development-in-visual-studio.md)|必须的。 介绍 Office 解决方案支持的特定版本的 Visual Studio Tools for Office Runtime。|`release`<br /><br /> `version`<br /><br /> `supportUrl`|  
  
## <a name="remarks"></a>备注  
 可以在 Office 解决方案中手动编辑应用程序和部署清单。 此后，必须通过使用清单生成和编辑工具 (mage.exe 和 mageui.exe) 对应用程序和部署清单重新签名。 有关详细信息，请参阅 [How to: Re-sign Application and Deployment Manifests](/visualstudio/deployment/how-to-re-sign-application-and-deployment-manifests)。  
  
## <a name="file-location"></a>文件位置  
 应用程序清单特定于单一版本的解决方案。 为此，应用程序清单应与部署清单分开存储。 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 将特定于版本的文件放置在一个子目录中，该子目录以发布文件夹中 **应用程序文件** 子目录中的关联版本命名。  
  
## <a name="file-name-syntax"></a>文件名语法  
 应用程序清单文件的名称应为应用程序的完整名称和扩展名，如 `assemblyIdentity` 元素中所标识的那样，后跟 extension.manifest。 例如，引用 OutlookAddIn1.dll 自定义的应用程序清单将使用以下文件名语法。  
  
 `OutlookAddIn1.dll.manifest`  
  
## <a name="see-also"></a>请参阅  
 [Office 解决方案的部署清单](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 应用程序清单](/visualstudio/deployment/clickonce-application-manifest)  
  
  