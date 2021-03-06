---
title: 安装或使用 Visual Studio 时与网络相关错误的疑难解答 | Microsoft 文档
description: ''
ms.custom: ''
ms.date: 02/12/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
- list of domains, locations, URLs, Visual Studio
- proxy errors, Visual Studio
ms.assetid: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fc5f1c07f709c1cdb8e20704dbea9cb5550b14b3
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="troubleshooting-network-related-errors-when-you-install-or-use-visual-studio"></a>安装或使用 Visual Studio 时与网络相关错误的疑难解答
对于你在防火墙或代理服务器后面安装或使用 Visual Studio 时，可能会遇到的最典型的与网络或代理相关的错误，我们已经有了解决方案。

## <a name="error-proxy-authorization-required"></a>错误：“需要进行代理身份验证”

当用户通过代理服务器连接到 Internet，而代理服务器阻止 Visual Studio 对某些网络资源进行的调用时，通常会发生此错误。

### <a name="to-fix-this-error"></a>修复此错误的方法：

- 重新启动 Visual Studio。 这时会出现一个代理身份验证对话框。 出现提示时，在对话框中输入你的凭据。

- 如果重启 Visual Studio 未能解决问题，这可能是由于你的代理服务器不提示需要提供 http:&#47;&#47;go.microsoft.com 地址的凭据，而是提示需要 &#42;.visualStudio.com 地址的凭据。 对于这些服务器，请考虑将以下 URL 列入到允许列表，以取消对 Visual Studio 中所有登录场景的阻止：

    - &#42;.windows.net

    - &#42;.microsoftonline.com

    - &#42;.visualstudio.com

    - &#42;.microsoft.com

    - &#42;.live.com

- 否则，可以从允许列表中删除 http:&#47;&#47;go.microsoft.com 地址，以便在重启 Visual Studio 时出现代理身份验证对话框，以提供 http:&#47;&#47;go.microsoft.com 地址和服务器终结点。

    或

- 如果你想通过代理使用默认凭据，则可以执行以下操作：

    1. 查找 devenv.exe.config（devenv.exe 配置文件），查找位置为：%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE 或 %ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE。

    1. 在配置文件中查找 `<system.net>` 块，然后添加这个代码：

        ```xml
        <defaultProxy enabled="true" useDefaultCredentials="true">
            <proxy bypassonlocal="True" proxyaddress=" HYPERLINK "http://<yourproxy:port#" http://<yourproxy:port#>"/>
        </defaultProxy>
        ```

        你必须在 `proxyaddress="<http://<yourproxy:port#>`中为你的网络插入正确的代理地址。

    或

- 此外，也可以按照[如何通过经身份验证的 Web 代理进行连接](http://blogs.msdn.com/b/rido/archive/2010/05/06/how-to-connect-to-tfs-through-authenticated-web-proxy.aspx)博客文章中的说明，了解如何添加允许你使用代理的代码。

## <a name="error-the-underlying-connection-was-closed"></a>错误：“基础连接已关闭”

如果在有防火墙的专用网络中使用 Visual Studio，则 Visual Studio 可能无法连接到某些网络资源。 这些资源可能会包括用于登录和授权的 Visual Studio Team Services (VSTS)、NuGet 和 Azure 服务。 如果 Visual Studio 无法连接到上述某个资源，则可能出现以下错误消息：

  **基础连接已关闭：发送时出现意外错误**

Visual Studio 使用传输层安全性 (TLS) 1.2 协议连接到网络资源。 Visual Studio 使用 TLS 1.2 时，某些专用网络上的安全设备会阻止某些服务器连接。

### <a name="to-fix-this-error"></a>修复此错误的方法：

对以下 URL 启用连接：

- https:&#47;&#47;management.core.windows.net

- https:&#47;&#47;app.vssps.visualstudio.com

- https:&#47;&#47;login.microsoftonline.com

- https:&#47;&#47;login.live.com

- https:&#47;&#47;go.microsoft.com

- https:&#47;&#47;graph.windows.net

- https:&#47;&#47;app.vsspsext.visualstudio.com

- &#42;.azurewebsites.net（用于 Azure 连接）

- &#42;.visualstudio.com

- cdn.vsassets.io（主机内容传送网络或 CDN、内容）

- &#42;.gallerycdn.vsassets.io（主机 VSTS 扩展）

- static2.sharepointonline.com（Visual Studio 在字体等 Office UI Fabric 工具包中使用的主机资源）

- &#42;.nuget.org（用于 NuGet 连接）

 > [!NOTE]
 > 此列表可能未包含私人拥有的 NuGet 服务器 URL。 你可以检查在 %APPData%\Nuget\NuGet.Config 中使用的 NuGet 服务器。


## <a name="get-support"></a>获取支持
如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的安装疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://www.visualstudio.com/vs/support/#talktous)。

下面是另外几个支持选项：
* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题，并在其中提问和找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。  （此选项需要 [GitHub](https://github.com/) 帐户。）

## <a name="see-also"></a>请参阅
* [在防火墙或代理服务器后面安装和使用 Visual Studio](install-and-use-visual-studio-behind-a-firewall-or-proxy-server.md)
* [Visual Studio 管理员指南](visual-studio-administrator-guide.md)
* [安装 Visual Studio 2017](install-visual-studio.md)
