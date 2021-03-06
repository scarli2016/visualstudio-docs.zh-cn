---
title: Visual Studio 中的负载测试 API | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- code, load tests
- plug-ins, load test
- APIs, load tests
ms.assetid: e15567bc-1f21-4feb-b81d-f17ba35cfde5
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 7623063ab83495ee5e458cc62f786c2e2cbafbd7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-the-load-test-api"></a>如何：使用负载测试 API

Visual Studio 支持可以控制或增强负载测试的负载测试插件。 负载测试插件是用户定义的类，可实现在 <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin> 命名空间中找到的 <xref:Microsoft.VisualStudio.TestTools.LoadTesting> 接口。 负载测试插件允许使用自定义负载测试控件，如在达到计数器或错误阈值时中止负载测试。 使用 <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest> 类的属性获取或设置用户定义代码中的负载测试参数。 使用 <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest> 类的事件在负载测试运行时附加通知委托。

> [!TIP]
> 可使用对象浏览器来检查 <xref:Microsoft.VisualStudio.TestTools.LoadTesting> 命名空间。 Visual C# 和 Visual Basic 编辑器均为使用此命名空间中的类编写代码提供了 IntelliSense 支持。

还可以创建 Web 性能测试插件。 有关详细信息，请参阅[如何：创建 Web 性能测试插件](../test/how-to-create-a-web-performance-test-plug-in.md)和[如何：创建请求级插件](../test/how-to-create-a-request-level-plug-in.md)。

## <a name="to-use-the-loadtesting-namespace"></a>使用 LoadTesting 命名空间

1.  打开一个包含负载测试的 Web 性能和负载测试项目。

2.  向测试解决方案添加一个 Visual C# 或 Visual Basic 类库项目。

3.  在 Web 性能和负载测试项目中添加对类库项目的引用。

4.  在类库项目中添加对 Microsoft.VisualStudio.QualityTools.LoadTestFramework DLL 的引用。

5.  在位于类库项目的类文件中，为 `using` 命名空间添加 <xref:Microsoft.VisualStudio.TestTools.LoadTesting> 语句。

6.  创建实现 <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin> 接口的公共类。

7.  生成项目。

8.  使用负载测试编辑器添加新负载测试插件：

    1.  右键单击负载测试的根节点，然后选择“添加负载测试插件”。

    2.  随即显示“添加负载测试插件”对话框。

    3.  在“选定插件的属性”窗格中，设置要在运行时使用的插件初始值。

        > [!NOTE]
        > 可以在插件中公开所需数量的属性。只需将其设置为公共、可设置并属于 Integer、Boolean 或 String 等基本类型。 以后，还可以使用“属性”窗口编辑负载测试插件属性。

9. 运行负载测试。

     有关实现 <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin> 的详细信息，请参阅[如何：创建负载测试插件](../test/how-to-create-a-load-test-plug-in.md)。

## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualStudio.TestTools.LoadTesting>
- [为负载测试创建自定义代码和插件](../test/create-custom-code-and-plug-ins-for-load-tests.md)
- [如何：使用 Web 性能测试 API](../test/how-to-use-the-web-performance-test-api.md)
- [如何：创建负载测试插件](../test/how-to-create-a-load-test-plug-in.md)