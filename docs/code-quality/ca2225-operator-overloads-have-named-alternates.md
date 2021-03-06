---
title: CA2225：运算符重载具有命名的备用项
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
helpviewer_keywords:
- OperatorOverloadsHaveNamedAlternates
- CA2225
ms.assetid: af8f7ab1-63ad-4861-afb9-b7a7a2be15e1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 991358ec361e414c9f5d335feb43eadde628a763
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="ca2225-operator-overloads-have-named-alternates"></a>CA2225：运算符重载具有命名的备用项
|||
|-|-|
|TypeName|OperatorOverloadsHaveNamedAlternates|
|CheckId|CA2225|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 检测到运算符重载，但未找到预期的指定备用方法。

## <a name="rule-description"></a>规则说明
 运算符重载允许使用的符号来表示类型的计算。 例如，添加重载加号 （+） 的类型通常具有名为 Add 的可选成员。 命名的备用成员提供对与运算符相同的功能的访问，并提供给开发人员的不支持重载的运算符的语言进行编程。

 此规则检查下表中列出的运算符。

|C#|Visual Basic|C++|备用名称|
|---------|------------------|-----------|--------------------|
|+ （二进制）|+|+ （二进制）|添加|
|+=|+=|+=|添加|
|&|And|&|BitwiseAnd|
|&=|和 =|&=|BitwiseAnd|
|&#124;|Or|&#124;|BitwiseOr|
|&#124;=|或 =|&#124;=|BitwiseOr|
|--|不可用|--|递减|
|/|/|/|除|
|/=|/=|/=|除|
|==|=|==|Equals|
|^|Xor|^|Xor|
|^=|Xor =|^=|Xor|
|>|>|>|比较|
|>=|>=|>=|比较|
|++|不可用|++|递增|
|<>|!=|Equals|
|<<|<<|<<|LeftShift|
|<<=|<<=|<<=|LeftShift|
|<|<|<|比较|
|<=|<=|\<=|比较|
|&&|不可用|&&|LogicalAnd|
|&#124;&#124;|不可用|&#124;&#124;|LogicalOr|
|!|不可用|!|LogicalNot|
|%|Mod|%|Mod 或余数|
|%=|不可用|%=|Mod|
|* （二进制）|*|*|相乘|
|*=|不可用|*=|相乘|
|~|不|~|OnesComplement|
|>>|>>|>>|RightShift|
=|不可用|>>=|RightShift|
|-（二进制）|-（二进制）|-（二进制）|减|
|-=|不可用|-=|减|
|true|IsTrue|不可用|IsTrue （属性）|
|-（一元）|不可用|-|要求反|
|+ （一元）|不可用|+|加号|
|False|IsFalse|False|IsTrue （属性）|

 不适用 = = 所选的语言不能重载。

 规则还检查类型中的隐式和显式强制转换运算符 (`SomeType`) 通过检查方法名为`ToSomeType`和`FromSomeType`。

 在 C# 中，在一个二元运算符重载时，相应的赋值运算符，如果有的话，也会隐式重载。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，可对运算符; 实现的替代方法将它使用建议的替代名称。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 如果你要实现共享的库不禁止显示此规则的警告。 应用程序可以忽略此规则的警告。

## <a name="example"></a>示例
 下面的示例定义一个结构，它与该规则冲突。 若要更正该示例，将添加一个公共`Add(int x, int y)`的结构的方法。

 [!code-csharp[FxCop.Usage.OperatorOverloadsHaveNamedAlternates#1](../code-quality/codesnippet/CSharp/ca2225-operator-overloads-have-named-alternates_1.cs)]

## <a name="related-rules"></a>相关的规则
 [CA1046：不要对引用类型重载相等运算符](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

 [CA2226：运算符应有对称重载](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

 [CA2224：重载相等运算符时重写 Equals 方法](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

 [CA2218：重写 Equals 时重写 GetHashCode](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

 [CA2231：重写 ValueType.Equals 时应重载相等运算符](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)