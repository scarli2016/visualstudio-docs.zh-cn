---
title: 使用 Python - 第 5 步：安装包 | Microsoft Docs
description: 在 Visual Studio 中使用 Python 的核心教程的第 5 步，展示了用于在 Python 环境中管理包的 Visual Studio 功能。
ms.custom: mvc
ms.date: 03/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: ''
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 509c601c6f3cf31cb7772182e0ecb771c232b8a6
ms.sourcegitcommit: 29ef88fc7d1511f05e32e9c6e7433e184514330d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="step-5-installing-packages-in-your-python-environment"></a>步骤 5：在 Python 环境中安装程序包

**上一步：[在调试器中运行代码](tutorial-working-with-python-in-visual-studio-step-04-debugging.md)**

Python 开发者社区制作了数千个有用的程序包，用户可以将它们合并到自己的项目中。 Visual Studio 提供一个 UI，用于管理 Python 环境中的程序包。

1. 选择“查看”>“其他窗口”>“Python 环境”菜单命令。 “Python 环境”窗口作为解决方案资源管理器的同级打开，并向用户显示各种可用的环境。 列表中包含使用 Visual Studio 安装程序安装的环境以及单独安装的环境。 粗体显示的环境是用于新项目的默认环境。

  ![“Python 环境”窗口](media/environments-default-view-blue.png)

1. 通过环境的“概述”选项卡，可以快速访问该环境的交互窗口以及安装文件夹和解释器。 例如，选择“打开交互窗口”，会在 Visual Studio 中显示该特定环境的交互窗口。

1. 选择“程序包”选项卡，会显示环境中当前安装的程序包列表。

  ![环境中安装的程序包](media/environments-installed-packages-blue.png)

1. 安装 `matplotlib`，方法如下：在搜索字段中输入其名称，然后选择 `pip install`

  ![在环境中安装 matplotlib](media/environments-add-matplotlib1.png)

1. 如果系统提示同意提升，请同意。

1. 安装程序包后，它会显示在“Python 环境”窗口中。 单击程序包右侧的 **X** 可卸载它。

  ![在环境中完成 matplotlib 的安装](media/environments-add-matplotlib2.png)

  环境下方的小进度条指示 Visual Studio 正在为新安装的程序包生成 IntelliSense 数据库。 “IntelliSense”选项卡也显示了更多详细信息。 请注意，完成该数据库之前，编辑器中的自动完成和语法检查等 IntelliSense 功能针对该程序包处于非活动状态。

  请注意，Visual Studio 2017 版本 15.6 及更高版本采用不同且更快的方法来使用 IntelliSense，并在“IntelliSense”选项卡上显示一条大意如此的消息。

1. 通过选择“文件”>“新建”>“项目”创建新项目，然后选择“Python 应用程序”模板。 在随即出现的代码文件中，粘贴以下代码，以创建像之前的教程步骤一样的余弦波，只不过这次以图形方式绘制：

    ```python
    from math import radians
    import numpy as np     # installed with matplotlib
    import matplotlib.pyplot as plt

    def main():
        x = np.arange(0, radians(1800), radians(12))
        plt.plot(x, np.cos(x), 'b')
        plt.show()

    main()
    ```

1. 按 (F5)（有调试器）或 (Ctrl+F5)（没有调试器）运行程序以查看输出：

  ![matplotlib 示例的输出](media/environments-add-matplotlib3.png)

## <a name="next-steps"></a>后续步骤

> [!div class="nextstepaction"]
> [使用 Git](tutorial-working-with-python-in-visual-studio-step-06-working-with-git.md)

### <a name="going-deeper"></a>深入了解

- [Python 环境](managing-python-environments-in-visual-studio.md)
