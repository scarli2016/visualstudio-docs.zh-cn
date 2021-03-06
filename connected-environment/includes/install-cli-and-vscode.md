---
ms.topic: include
ms.openlocfilehash: 78de57178350d4317896c41a455efbeeb553c58d
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
## <a name="install-the-connected-environment-cli"></a>安装通连环境 CLI
通连环境需要最少的本地计算机设置。 大部分开发环境配置都存储在云中，并可与其他用户共享。

### <a name="install-on-mac"></a>在 Mac 上安装
下载并安装通连环境 CLI：
```cmd
curl -L https://aka.ms/get-vsce-mac | bash
```

### <a name="install-on-windows"></a>在 Windows 上安装
1. 下载并运行[通连环境 CLI 安装程序](https://aka.ms/get-vsce-windows)。 

### <a name="install-on-linux"></a>在 Linux 上安装
即将推出...

## <a name="get-kubernetes-debugging-for-vs-code"></a>获取适用于 VS Code 的 Kubernetes 调试
虽然可将通连环境 CLI 作为独立工具使用，但使用 VS Code 的 .NET Core 和 Node.js 开发者也可以使用 Kubernetes 调试等丰富功能。

1. 如果尚未安装，请安装 [VS Code](https://code.visualstudio.com/Download)。
1. 下载 [VS 通连环境扩展](https://aka.ms/get-vsce-code)。
1. 安装扩展： 

```cmd
code --install-extension path-to-downloaded-extension/vsce-0.1.1.vsix
```
