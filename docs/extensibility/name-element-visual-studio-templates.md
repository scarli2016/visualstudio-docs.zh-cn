---
title: "Name 元素（Visual Studio 模板） | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#Name"
helpviewer_keywords: 
  - "Name 元素 [Visual Studio 项目模板]"
ms.assetid: 48788dbf-7da0-4443-8061-aab966fc22c8
caps.latest.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 17
---
# Name 元素（Visual Studio 模板）
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

指定模板出现在**“新建项目”**或**“添加新项”**对话框中时此模板的名称。  
  
## 语法  
  
```  
<Name> Template Name </Name>  
```  
  
```  
<Name Package="{PackageID}" ID="ResourceID" />  
```  
  
## 特性和元素  
 以下几节描述了特性、子元素和父元素。  
  
### 特性  
  
|特性|描述|  
|--------|--------|  
|`Package`|可选特性，适用于高级用户情形。<br /><br /> 一个 GUID，它指定 Visual Studio 数据包 ID。|  
|`ID`|可选特性，适用于高级用户情形。<br /><br /> 指定 Visual Studio 资源 ID。|  
  
### 子元素  
 无。  
  
### 父元素  
  
|元素|描述|  
|--------|--------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|必需的元素。<br /><br /> 将此模板分类并定义此模板在**“新建项目”**或**“添加新项”**对话框中的显示方式。|  
  
## 文本值  
 除非使用了 `Package` 和 `ID` 特性，否则需要一个文本值。  
  
 此文本提供模板的名称。  
  
## 备注  
 `Name` 是 `TemplateData` 的一个必选子元素。  
  
## 示例  
 下面的示例演示针对 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 应用程序的某个项目模板的元数据。  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## 请参阅  
 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)   
 [创建自定义项目和项模板](../ide/creating-project-and-item-templates.md)