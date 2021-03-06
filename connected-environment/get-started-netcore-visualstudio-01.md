---
title: 使用 Visual Studio 在云中创建 .NET Core 开发环境（使用 Kubernetes 管理其中的容器）- 第 1 步 - 安装工具 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 04/05/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: douge
ms.openlocfilehash: b2edc476ffd4648f9ddb0e3d076f8eb400458242
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>开始使用 .NET Core 和 Visual Studio 通连环境

本指南将介绍：

1. 如何在 Azure 中创建基于 Kubernetes 的环境并将该环境优化以便于开发。
1. 如何使用 Visual Studio 在容器中迭代开发代码。
1. 如何独立开发两个单独的服务，并使用 Kubernetes 的 DNS 服务发现调用另一个服务。
1. 如何在团队环境中高效开发和测试代码。

[!INCLUDE[](includes/see-troubleshooting.md)]

## <a name="install-the-connected-environment-cli"></a>安装通连环境 CLI
通连环境需要最少的本地计算机设置。 大部分开发环境配置都存储在云中，并可与其他用户共享。

1. 下载并运行[通连环境 CLI 安装程序](https://aka.ms/get-vsce-windows)。 

## <a name="get-kubernetes-debugging-tools"></a>获取 Kubernetes 调试工具
虽然可将通连环境 CLI 作为独立工具使用，但使用 VS Code 或 Visual Studio 的 .NET Core 开发者也可以使用 Kubernetes 调试等丰富功能。

### <a name="visual-studio-debugging"></a>Visual Studio 调试 
1. 安装最新版本的 [Visual Studio 2017](https://www.visualstudio.com/vs/)
1. 在 Visual Studio 安装程序中，确保选择了以下工作负载：
    * ASP.NET 和 Web 开发
1. 安装[适用于通连环境的 Visual Studio 扩展](https://aka.ms/get-vsce-visualstudio)

现已准备好使用 Visual Studio 创建 ASP.NET Web 应用。

> [!div class="nextstepaction"]
> [创建 ASP.NET Web 应用](get-started-netcore-visualstudio-02.md)
