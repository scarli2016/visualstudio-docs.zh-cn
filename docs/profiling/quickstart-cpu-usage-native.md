---
title: 分析 CPU 使用率数据 (C++) | Microsoft Docs
ms.custom: ''
ms.date: 12/05/2017
ms.technology: vs-ide-debug
ms.topic: quickstart
f1_keywords:
- ''
helpviewer_keywords:
- Profiling Tools, quick start
- Diagnostics Tools, CPU Usage
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 52483a920d47b5728645ae195bc1837c7ccc565b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="analyze-cpu-usage-data-in-visual-studio-c"></a>在 Visual Studio 中分析 CPU 使用率数据 (C++)

Visual Studio 提供了许多强大的功能来帮助你分析应用程序中的性能问题。 本主题提供了一种快速了解部分基本功能的方法。 此处，我们将了解用来确定由于 CPU 使用率高而导致性能瓶颈的工具。 Visual Studio 中的 .NET 开发（包括 ASP.NET、和本机 /C++ 开发）支持此诊断工具。

诊断中心提供了大量其他选项来运行和管理诊断会话。 如果此处介绍的“CPU 使用率”工具未提供所需数据，[其他分析工具](../profiling/profiling-feature-tour.md)可提供可能有帮助的不同种类的信息。 在许多情况下，CPU 以外的因素可能会导致应用程序性能瓶颈，例如内存、呈现 UI 或网络请求时间。 诊断中心提供大量其他选项，可用于记录和分析此种数据。

## <a name="create-a-project"></a>创建项目

1. 在 Visual Studio 中，依次选择“文件”>“新建项目”。

2. 在“Visual C++”下，选择“Windows 桌面”，然后在中间窗格中选择“Windows 控制台应用程序”。

3. 键入名称（例如 Diagnostics_Get_Started_Native），单击“确定”。

    Visual Studio 随即创建项目。

4. 在 MyDbgApp.cpp 中，将以下代码

    ```c++
    int main()
    {
        return 0;
    }
    ```

    替换为此代码（请勿删除 `#include "stdafx.h"`）：

    ```c++
    #include <iostream>
    #include <limits>
    #include <mutex>
    #include <random>
    #include <functional>
    
    //.cpp file code:
    
    static constexpr int MIN_ITERATIONS = std::numeric_limits<int>::max() / 1000;
    static constexpr int MAX_ITERATIONS = MIN_ITERATIONS + 10000;
    
    long long m_totalIterations = 0;
    std::mutex m_totalItersLock;
    
    int getNumber()
    {
    
        std::uniform_int_distribution<int> num_distribution(MIN_ITERATIONS, MAX_ITERATIONS);
        std::mt19937 random_number_engine; // pseudorandom number generator
        auto get_num = std::bind(num_distribution, random_number_engine);
        int random_num = get_num();
    
        auto result = 0;
        {
            std::lock_guard<std::mutex> lock(m_totalItersLock);
            m_totalIterations += random_num;
        }
        // we're just spinning here  
        // to increase CPU usage 
        for (int i = 0; i < random_num; i++)
        {
            result = get_num();
        }
        return result;
    }
    
    void doWork()
    {
        std::wcout << L"The doWork function is running on another thread." << std::endl;
    
        auto x = getNumber();    
    }
    
    int main()
    {
        std::vector<std::thread> threads;
    
        for (int i = 0; i < 10; ++i) {
    
            threads.push_back(std::thread(doWork));
            std::cout << "The Main() thread calls this after starting the new thread" << std::endl;
        }
    
        for (auto& thread : threads) {
            thread.join();
        }
    
        return 0;
    }
    ```
  
##  <a name="BKMK_Quick_start__Collect_diagnostic_data"></a>步骤 1：收集分析数据 
  
1.  首先，在应用中在 `main` 函数的该代码行处设置一个断点：

    `for (int i = 0; i < 10; ++i) {`

    单击代码行左侧的装订线，设置断点。

2.  然后，在 `main` 函数末尾的右括号处设置第二个断点：

     ![设置断点以进行分析](../profiling/media/quickstart-cpu-usage-breakpoints-cplusplus.png "设置断点以进行分析")

    > [!TIP]
    > 通过设置两个断点，可将数据收集限制到想要分析的代码部分。
  
3.  已显示“诊断工具”窗口，除非已将其关闭。 若要再次显示该窗口，请依次单击“调试”、“Windows”、“显示诊断工具”。

4.  依次单击“调试”、“启动调试”或单击工具栏上的“启动”或按 **F5**。

     应用完成加载后，将显示诊断工具的“摘要”视图。

5.  调试器暂停时，选择“记录 CPU 配置文件”以启用 CPU 使用率数据的收集，然后打开“CPU 使用率”选项卡。

     ![诊断工具启用 CPU 分析](../profiling/media/quickstart-cpu-usage-summary.png "诊断工具启用 CPU 分析")

     启用数据收集时，记录按钮将显示一个红圈。

     选择“记录 CPU 配置文件”时，Visual Studio 将开始记录函数和执行函数所花的时间，还会提供一个时间线关系图，可使用此关系图专注于采样会话的特定分段。只有应用程序在断点处停止时，才可以查看该收集数据。

6.  按 F5 将应用运行到第二个断点。

     现在将拥有应用程序特定于在两个断点间运行的代码区域的性能数据。

     探查器开始准备线程数据。 等待其完成。
  
     CPU 使用率工具在“CPU 使用率”选项卡中显示报表。

     现在可以开始分析数据。

## <a name="Step2"></a>步骤 2：分析 CPU 使用率数据

建议通过检查 CPU 使用率下的函数列表开始分析数据，然后确定执行大部分工作的函数，最后仔细查看每一个函数。

1. 在函数列表中，检查执行大部分工作的函数。

     ![诊断工具“ CPU 使用率”选项卡](../profiling/media/quickstart-cpu-usage-cpu-cplusplus.png "DiagToolsCPUUsageTab")

    > [!TIP]
    > 函数将按执行工作量从多到少排列（不按调用顺序）。 这有助于快速标识运行时间最长的函数。

2. 在函数列表中，双击 `getNumber` 函数。

    双击该函数时，将在左侧窗格中打开“调用方/被调用方”视图。 

    ![诊断工具调用方和被调用方视图](../profiling/media/quickstart-cpu-usage-caller-callee-cplusplus.png "DiagToolsCallerCallee")

    在此视图中，所选函数显示在标题和“当前函数”框中（本例中为 `getNumber`）。 调用当前函数的函数显示在左侧的“调用函数”中，当前函数调用的任何函数均显示在右侧的“被调用函数”框中。 （可选择其中一个框来更改当前函数。）

    此视图显示总时间及函数完成执行所用的总体应用运行时间的百分比。

    **函数体**还显示函数体中所用的时间总量（及百分比），其中不包括调用和被调用函数中所用的时间。 （在此图中，共花费 43602 毫秒，函数体内花费 119 毫秒，其余时间花费在此函数调用的其他代码中）。 环境不同，实际值也大不相同。

    > [!TIP]
    > **函数体**中的较高值可能指示函数自身内部的性能瓶颈。

## <a name="next-steps"></a>后续步骤

- [分析内存使用量](../profiling/memory-usage.md)，确定性能瓶颈。
- [分析 CPU 使用情况](../profiling/cpu-usage.md)，更深入地了解 CPU 使用率工具。
- 在不附加调试程序的情况下，或通过将正在运行的应用作为目标来分析 CPU 使用率。有关详细信息，请参阅[在使用或不使用调试程序的情况下运行分析工具](../profiling/running-profiling-tools-with-or-without-the-debugger.md)中的[在不使用调试程序的情况下收集分析数据](../profiling/running-profiling-tools-with-or-without-the-debugger.md#collect-profiling-data-without-debugging)。

## <a name="see-also"></a>请参阅  

 [使用 Visual Studio 分析](../profiling/index.md)  
 [分析功能导览](../profiling/profiling-feature-tour.md)
