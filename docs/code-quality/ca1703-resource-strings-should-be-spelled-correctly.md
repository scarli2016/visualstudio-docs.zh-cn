---
title: CA1703：资源字符串应正确拼写
ms.date: 03/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ResourceStringsShouldBeSpelledCorrectly
- CA1703
helpviewer_keywords:
- CA1703
- ResourceStringsShouldBeSpelledCorrectly
ms.assetid: 693f4970-f512-40cb-ae3b-a0f3a5c6d6f1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e8103353fc5d2e0d74b5355259f0e2bc77ddd974
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="ca1703-resource-strings-should-be-spelled-correctly"></a>CA1703：资源字符串应正确拼写

|||
|-|-|
|TypeName|ResourceStringsShouldBeSpelledCorrectly|
|CheckId|CA1703|
|类别|Microsoft.Naming|
|是否重大更改|非重大|

## <a name="cause"></a>原因

资源字符串包含一个或多个未被 Microsoft 拼写检查器库识别的单词。

## <a name="rule-description"></a>规则说明

此规则将资源字符串解析为单词 （词汇切分复合词），并检查每个单词/标记的拼写正确。 有关分析算法的信息，请参阅[CA1704： 标识符应正确拼写](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复与此规则的冲突，使用全字拼写正确，或将字添加到自定义词典。 有关如何使用自定义词典的信息，请参阅[CA1704： 标识符应正确拼写](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)。

## <a name="change-the-dictionary-language"></a>更改的字典语言

默认情况下，为使用拼写检查器的英语 (en) 版本。 如果你想要更改拼写检查器的语言，则可以执行以便通过添加以下一项特性来你*AssemblyInfo.cs*或*AssemblyInfo.vb*文件：

- 使用<xref:System.Reflection.AssemblyCultureAttribute>来指定的区域性，如果你的资源在附属程序集。
- 使用<xref:System.Resources.NeutralResourcesLanguageAttribute>指定*非特定区域性*的程序集，如果你的资源位于你的代码相同的程序集中。

> [!IMPORTANT]
> 如果你将区域性设置为基于英语区域性之外的任何内容时，会以无提示方式禁用此代码分析规则。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

不禁止显示此规则发出的警告。 正确的拼写的单词可以减少了解新的软件库所需的时间。

## <a name="related-rules"></a>相关的规则

- [CA1701：资源字符串复合词应采用正确的大小写](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)
- [CA1704：标识符应正确拼写](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)
- [CA2204：应正确拼写文本](../code-quality/ca2204-literals-should-be-spelled-correctly.md)