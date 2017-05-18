---
title: "对函数参数和返回值进行批注 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_Outptr_opt_result_bytebuffer_to_"
  - "_Inout_updates_all_opt_"
  - "_Post_equal_to_"
  - "_Outptr_opt_result_maybenull_"
  - "_Out_writes_bytes_all_"
  - "_Out_writes_all_opt_"
  - "_In_opt_"
  - "_Outptr_"
  - "_Outptr_result_maybenull_"
  - "_Outref_result_bytebuffer_all_maybenull_"
  - "_Inout_updates_opt_z_"
  - "_Inout_updates_z_"
  - "_Out_writes_"
  - "_Out_writes_to_ptr_opt_z_"
  - "_In_reads_to_ptr_opt_"
  - "_Ret_writes_to_maybenull_"
  - "_Outref_result_maybenull_"
  - "_Ret_writes_bytes_"
  - "_Outptr_result_bytebuffer_"
  - "_Out_writes_opt_"
  - "_Inout_updates_bytes_opt_"
  - "_In_z_"
  - "_Inout_updates_to_"
  - "_Ret_maybenull_"
  - "_Ret_writes_bytes_to_"
  - "_Ret_z_"
  - "_COM_Outptr_"
  - "_Ret_maybenull_z_"
  - "_Out_opt_"
  - "_In_reads_opt_z_"
  - "_Outptr_result_bytebuffer_to_"
  - "_Ret_notnull_"
  - "_COM_Outptr_opt_result_maybenull_"
  - "_Inout_updates_to_opt_"
  - "_Inout_updates_"
  - "_Outptr_opt_result_buffer_"
  - "_Outptr_result_buffer_to_"
  - "_Out_writes_to_ptr_opt_"
  - "_Out_writes_bytes_all_opt_"
  - "_Inout_updates_all_"
  - "_Deref_inout_range_"
  - "_Ret_writes_"
  - "_Out_writes_z_"
  - "_Ret_writes_to_"
  - "_Out_writes_to_ptr_z_"
  - "_Out_writes_bytes_to_opt_"
  - "_In_reads_or_z_"
  - "_Inout_updates_bytes_to_"
  - "_In_reads_z_"
  - "_In_opt_z_"
  - "_Outref_result_buffer_maybenull_"
  - "_Ret_range_"
  - "_COM_Outptr_opt_"
  - "_Ouptr_opt_result_maybenull_z_"
  - "_In_reads_opt_"
  - "_Inout_"
  - "_Field_range_"
  - "_Ret_writes_z_"
  - "_Out_writes_to_"
  - "_Out_writes_to_ptr_"
  - "_Inout_opt_z_"
  - "_Outref_"
  - "_Deref_out_range_"
  - "_Outref_result_buffer_"
  - "_Outref_result_buffer_to_"
  - "_Outref_result_bytebuffer_to_maybenull_"
  - "_In_reads_bytes_"
  - "_Outptr_opt_result_buffer_to_"
  - "_Outref_result_buffer_all_"
  - "_Out_writes_bytes_to_"
  - "_Result_zeroonfailure_"
  - "_In_reads_bytes_opt_"
  - "_Outref_result_buffer_to_maybenull_"
  - "_Outref_result_bytebuffer_all_"
  - "_Outref_result_buffer_all_maybenull_"
  - "_Ret_writes_maybenull_z_"
  - "_In_range_"
  - "_Inout_updates_bytes_all_opt_"
  - "_Outref_result_bytebuffer_to_"
  - "_Inout_updates_bytes_to_opt_"
  - "_Pre_equal_to_"
  - "_Ret_writes_bytes_maybenull_"
  - "_COM_Outptr_result_maybenull_"
  - "_Ret_writes_maybenull_"
  - "_Out_writes_bytes_"
  - "_Outptr_opt_"
  - "_Out_writes_opt_z_"
  - "_Outref_result_nullonfailure_"
  - "_Outptr_opt_result_z_"
  - "_Inout_opt_"
  - "_Deref_in_range_"
  - "_Outptr_result_z_"
  - "_In_reads_to_ptr_opt_z_"
  - "_Struct_size_bytes_"
  - "_Outptr_result_nullonfailure_"
  - "_In_"
  - "_Inout_updates_bytes_"
  - "_In_reads_to_ptr_z_"
  - "_Ret_writes_bytes_to_maybenull"
  - "_Outptr_opt_result_nullonfailure_"
  - "_In_reads_to_ptr_"
  - "_Outptr_result_buffer_"
  - "_Out_"
  - "_Outref_result_bytebuffer_maybenull_"
  - "_Outptr_result_maybenull_z_"
  - "_In_reads_"
  - "_Inout_updates_opt_"
  - "_Out_writes_to_opt_"
  - "_Outptr_opt_result_bytebuffer_"
  - "_Out_writes_all_"
  - "_Out_range_"
  - "_Inout_updates_bytes_all_"
  - "_Inout_z_"
  - "_Outref_result_bytebuffer_"
  - "_Result_nullonfailure_"
  - "_Ret_null_"
ms.assetid: 82826a3d-0c81-421c-8ffe-4072555dca3a
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 对函数参数和返回值进行批注
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

本指南介绍了简单的函数参数的批注的典型用途 — 标量和指向结构和类的指针，以及大多数类型的缓冲区。  本文章还介绍对批注的常见使用模式。 与功能相关的其他批注，请参阅 [批注函数行为](../code-quality/annotating-function-behavior.md)  
  
## <a name="pointer-parameters"></a>指针参数  
 下表中的批注，当指针参数要批注，则分析器将报告错误如果指针为 null。  这适用于指针和指向任何数据项。  
  
 **批注和说明**  
  
-   `_In_`  
  
     批注是标量、 结构、 指向结构的指针和类似的输入的参数。  显式可基于简单的标量。  该参数前的状态必须是有效，并且不会被修改。  
  
-   `_Out_`  
  
     批注是标量、 结构、 指向结构的指针和类似的输出参数。  不适用于此无法返回值的对象-例如，通过值传递的标量。  参数而不必在前的状态下无法有效，但在后的状态必须是有效。  
  
-   `_Inout_`  
  
     批注的函数将更改的参数。  它在前的状态和后状态时，必须是有效，但假定可以具有不同的值之前和之后调用。 必须将应用于可修改的值。  
  
-   `_In_z_`  
  
     指向用作输入以 null 结尾的字符串的指针。  字符串前的状态必须是有效的。  变体 `PSTR`, ，已具有正确的批注，首选分发点。  
  
-   `_Inout_z_`  
  
     指向将被修改的 null 终止字符数组的指针。  之前和之后调用，它必须是有效，但值被认为已发生了更改。  可能移动 null 终止符，但可能会访问仅元素，直到原始 null 终止符。  
  
-   `_In_reads_(s)`  
  
     `_In_reads_bytes_(s)`  
  
     指向数组中，为可读取由该函数的指针。  该数组的大小是 `s` 元素，它们都必须有效。  
  
      `_bytes_` Variant 类型的值提供以字节为单位，而不是元素的大小。 仅在大小不能表示为元素时，请使用此选项。  例如， `char` 字符串将使用 `_bytes_` 变体类似的功能时，才使用 `wchar_t` 将。  
  
-   `_In_reads_z_(s)`  
  
     指向以 null 结尾并具有已知的大小的数组的指针。 元素，直到 null 终止符 — 或 `s` 是否不包含 null 终止符前的状态必须是有效。  如果以字节为单位已知大小，可以缩放 `s` 按元素大小。  
  
-   `_In_reads_or_z_(s)`  
  
     指向以 null 结尾的或具有已知的大小，和 / 或数组的指针。 元素，直到 null 终止符 — 或 `s` 是否不包含 null 终止符前的状态必须是有效。  如果以字节为单位已知大小，可以缩放 `s` 按元素大小。  (用于 `strn` 系列。)  
  
-   `_Out_writes_(s)`  
  
     `_Out_writes_bytes_(s)`  
  
     指向数组的指针 `s` 元素 （分别 字节为单位），将通过函数进行编写。  数组元素并不一定前的状态，才能有效后状态中都有效的元素的数目是未指定。  如果有批注的参数类型，它们将应用处于后的状态。 例如，考虑下面的代码。  
  
     `typedef _Null_terminated_ wchar_t *PWSTR; void MyStringCopy(_Out_writes_ (size) PWSTR p1,    _In_ size_t size,    _In_ PWSTR p2);`  
  
     在此示例中，调用方提供的缓冲区 `size` 元素 `p1`。  `MyStringCopy` 使这些元素的某些有效。 更重要的是， `_Null_terminated_` 上的批注 `PWSTR` 意味着 `p1` 后的状态是以 null 结尾。  这种方式，有效元素数目仍完善定义的但不需要特定的元素数。  
  
      `_bytes_` Variant 类型的值提供以字节为单位，而不是元素的大小。 仅在大小不能表示为元素时，请使用此选项。  例如， `char` 字符串将使用 `_bytes_` 变体类似的功能时，才使用 `wchar_t` 将。  
  
-   `_Out_writes_z_(s)`  
  
     指向数组的指针 `s` 元素。  元素不需要在前的状态下无法有效。  在后状态下，通过将 null 结束符向上元素 — 必须存在，必须是有效的。  如果以字节为单位已知大小，可以缩放 `s` 按元素大小。  
  
-   `_Inout_updates_(s)`  
  
     `_Inout_updates_bytes_(s)`  
  
     指向一个数组，该读取并写入到函数中的数组的指针。  它是大小 `s` 元素，并在前的状态和后状态中有效。  
  
      `_bytes_` Variant 类型的值提供以字节为单位，而不是元素的大小。 仅在大小不能表示为元素时，请使用此选项。  例如， `char` 字符串将使用 `_bytes_` 变体类似的功能时，才使用 `wchar_t` 将。  
  
-   `_Inout_updates_z_(s)`  
  
     指向以 null 结尾并具有已知的大小的数组的指针。 通过将 null 结束符向上元素 — 必须存在 — 在前的状态和后状态中必须是有效。  假定后的状态中的值为不同于前的状态; 中的值这包括 null 终止符的位置。 如果以字节为单位已知大小，可以缩放 `s` 按元素大小。  
  
-   `_Out_writes_to_(s,c)`  
  
     `_Out_writes_bytes_to_(s,c)`  
  
     `_Out_writes_all_(s)`  
  
     `_Out_writes_bytes_all_(s)`  
  
     指向数组的指针 `s` 元素。  元素不需要在前的状态下无法有效。  在后状态下，之前的元素 `c`-th 元素必须是有效。  如果以字节为单位已知大小，可以缩放 `s` 和 `c` 按元素大小或使用 `_bytes_` 变体，它定义为︰  
  
     `_Out_writes_to_(_Old_(s), _Old_(s))    _Out_writes_bytes_to_(_Old_(s), _Old_(s))`  
  
     换而言之，最多存在缓冲区中的每个元素 `s` 前的状态处于有效后状态。  例如:   
  
     `void *memcpy(_Out_writes_bytes_all_(s) char *p1,    _In_reads_bytes_(s) char *p2,    _In_ int s); void * wordcpy(_Out_writes_all_(s) DWORD *p1,     _In_reads_(s) DWORD *p2,    _In_ int s);`  
  
-   `_Inout_updates_to_(s,c)`  
  
     `_Inout_updates_bytes_to_(s,c)`  
  
     指向一个数组，它是读取和写入由该函数的指针。  它是大小 `s` 元素，它们都必须是有效前的状态，并 `c` 元素后的状态必须是有效。  
  
      `_bytes_` Variant 类型的值提供以字节为单位，而不是元素的大小。 仅在大小不能表示为元素时，请使用此选项。  例如， `char` 字符串将使用 `_bytes_` 变体类似的功能时，才使用 `wchar_t` 将。  
  
-   `_Inout_updates_z_(s)`  
  
     指向以 null 结尾并具有已知的大小的数组的指针。 通过将 null 结束符向上元素 — 必须存在 — 在前的状态和后状态中必须是有效。  假定后的状态中的值为不同于前的状态; 中的值这包括 null 终止符的位置。 如果以字节为单位已知大小，可以缩放 `s` 按元素大小。  
  
-   `_Out_writes_to_(s,c)`  
  
     `_Out_writes_bytes_to_(s,c)`  
  
     `_Out_writes_all_(s)`  
  
     `_Out_writes_bytes_all_(s)`  
  
     指向数组的指针 `s` 元素。  元素不需要在前的状态下无法有效。  在后状态下，之前的元素 `c`-th 元素必须是有效。  如果以字节为单位已知大小，可以缩放 `s` 和 `c` 按元素大小或使用 `_bytes_` 变体，它定义为︰  
  
     `_Out_writes_to_(_Old_(s), _Old_(s))    _Out_writes_bytes_to_(_Old_(s), _Old_(s))`  
  
     换而言之，最多存在缓冲区中的每个元素 `s` 前的状态处于有效后状态。  例如:   
  
     `void *memcpy(_Out_writes_bytes_all_(s) char *p1,    _In_reads_bytes_(s) char *p2,    _In_ int s); void * wordcpy(_Out_writes_all_(s) DWORD *p1,     _In_reads_(s) DWORD *p2,    _In_ int s);`  
  
-   `_Inout_updates_to_(s,c)`  
  
     `_Inout_updates_bytes_to_(s,c)`  
  
     指向一个数组，它是读取和写入由该函数的指针。  它是大小 `s` 元素，它们都必须是有效前的状态，并 `c` 元素后的状态必须是有效。  
  
      `_bytes_` Variant 类型的值提供以字节为单位，而不是元素的大小。 仅在大小不能表示为元素时，请使用此选项。  例如， `char` 字符串将使用 `_bytes_` 变体类似的功能时，才使用 `wchar_t` 将。  
  
-   `_Inout_updates_all_(s)`  
  
     `_Inout_updates_bytes_all_(s)`  
  
     指向数组，它是读取和写入大小的函数指针 `s` 元素。 定义为等效于︰  
  
     `_Inout_updates_to_(_Old_(s), _Old_(s))    _Inout_updates_bytes_to_(_Old_(s), _Old_(s))`  
  
     换而言之，最多存在缓冲区中的每个元素 `s` 前的状态处于有效前的状态和后的状态。  
  
      `_bytes_` Variant 类型的值提供以字节为单位，而不是元素的大小。 仅在大小不能表示为元素时，请使用此选项。  例如， `char` 字符串将使用 `_bytes_` 变体类似的功能时，才使用 `wchar_t` 将。  
  
-   `_In_reads_to_ptr_(p)`  
  
     指向数组的指针表达式 `p` – `_Curr_` (即， `p` 减去 `_Curr_`) 由相应的语言标准定义。  之前的元素 `p` 前的状态必须是有效。  
  
-   `_In_reads_to_ptr_z_(p)`  
  
     指向以 null 结尾的数组的指针表达式 `p` – `_Curr_` (即， `p` 减去 `_Curr_`) 由相应的语言标准定义。  之前的元素 `p` 前的状态必须是有效。  
  
-   `_Out_writes_to_ptr_(p)`  
  
     指向数组的指针表达式 `p` – `_Curr_` (即， `p` 减去 `_Curr_`) 由相应的语言标准定义。  之前的元素 `p` 无需在前的状态下无法有效并处于后的状态必须是有效。  
  
-   `_Out_writes_to_ptr_z_(p)`  
  
     指向以 null 结尾的数组的指针表达式 `p` – `_Curr_` (即， `p` 减去 `_Curr_`) 由相应的语言标准定义。  之前的元素 `p` 无需在前的状态下无法有效并处于后的状态必须是有效。  
  
## <a name="optional-pointer-parameters"></a>可选指针参数  
 当指针参数批注中包括 `_opt_`, ，它指示该参数可能为 null。 否则，该批注将执行不包括的版本相同 `_opt_`。 下面是一份 `_opt_` 指针参数批注的变体︰  
  
||||  
|-|-|-|  
|`_In_opt_`<br /><br /> `_Out_opt_`<br /><br /> `_Inout_opt_`<br /><br /> `_In_opt_z_`<br /><br /> `_Inout_opt_z_`<br /><br /> `_In_reads_opt_`<br /><br /> `_In_reads_bytes_opt_`<br /><br /> `_In_reads_opt_z_`|`_Out_writes_opt_`<br /><br /> `_Out_writes_opt_z_`<br /><br /> `_Inout_updates_opt_`<br /><br /> `_Inout_updates_bytes_opt_`<br /><br /> `_Inout_updates_opt_z_`<br /><br /> `_Out_writes_to_opt_`<br /><br /> `_Out_writes_bytes_to_opt_`<br /><br /> `_Out_writes_all_opt_`<br /><br /> `_Out_writes_bytes_all_opt_`|`_Inout_updates_to_opt_`<br /><br /> `_Inout_updates_bytes_to_opt_`<br /><br /> `_Inout_updates_all_opt_`<br /><br /> `_Inout_updates_bytes_all_opt_`<br /><br /> `_In_reads_to_ptr_opt_`<br /><br /> `_In_reads_to_ptr_opt_z_`<br /><br /> `_Out_writes_to_ptr_opt_`<br /><br /> `_Out_writes_to_ptr_opt_z_`|  
  
## <a name="output-pointer-parameters"></a>输出指针参数  
 输出指针参数需要特殊表示法来消除歧义空的参数和指向的位置上。  
  
 **批注和说明**  
  
-   `_Outptr_`  
  
     参数不能为 null，并后的状态在指向的位置不能为 null，并且必须有效。  
  
-   `_Outptr_opt_`  
  
     参数可以为 null，但在后期状态指向的位置不能为 null，并且必须有效。  
  
-   `_Outptr_result_maybenull_`  
  
     参数不能为 null，并在后期状态指向的位置可以为 null。  
  
-   `_Outptr_opt_result_maybenull_`  
  
     参数可以为 null，并在后期状态指向的位置可以为 null。  
  
 下表中其他的子字符串插入要进一步限定的含义的批注的批注名称。  各种子字符串 `_z`, ，`_COM_`, ，`_buffer_`, ，`_bytebuffer_`, ，和 `_to_`。  
  
> [!IMPORTANT]
>  如果您添加注释的接口，COM 使用这些批注 COM 窗体。 不要与任何其他类型的接口中使用 COM 批注。  
  
 **批注和说明**  
  
-   `_Outptr_result_z_`  
  
     `_Outptr_opt_result_z_`  
  
     `_Outptr_result_maybenull_z_`  
  
     `_Ouptr_opt_result_maybenull_z_`  
  
     返回的指针具有 `_Null_terminated_` 批注。  
  
-   `_COM_Outptr_`  
  
     `_COM_Outptr_opt_`  
  
     `_COM_Outptr_result_maybenull_`  
  
     `_COM_Outptr_opt_result_maybenull_`  
  
     返回的指针具有 COM 语义，并因此执行 `_On_failure_` 后置条件返回的指针为 null。  
  
-   `_Outptr_result_buffer_(s)`  
  
     `_Outptr_result_bytebuffer_(s)`  
  
     `_Outptr_opt_result_buffer_(s)`  
  
     `_Outptr_opt_result_bytebuffer_(s)`  
  
     返回的指针指向有效的缓冲区大小的 `s` 元素或字节数。  
  
-   `_Outptr_result_buffer_to_(s, c)`  
  
     `_Outptr_result_bytebuffer_to_(s, c)`  
  
     `_Outptr_opt_result_buffer_to_(s,c)`  
  
     `_Outptr_opt_result_bytebuffer_to_(s,c)`  
  
     返回的指针指向了大小的缓冲区 `s` 元素或字节数，其中第一个 `c` 都有效。  
  
 一些接口约定假设输出参数付之东流失败。  除显式 COM 代码下, 表中的窗体是首选项。  对于 COM 代码，请使用上一节中列出的相应 COM 窗体。  
  
 **批注和说明**  
  
-   `_Result_nullonfailure_`  
  
     修改其他批注。 结果集为 null，如果函数失败。  
  
-   `_Result_zeroonfailure_`  
  
     修改其他批注。 如果函数失败，结果设置为零。  
  
-   `_Outptr_result_nullonfailure_`  
  
     如果函数失败，返回的指针将指向有效的缓冲区，如果函数成功，或者为 null。 此批注是为非可选参数。  
  
-   `_Outptr_opt_result_nullonfailure_`  
  
     如果函数失败，返回的指针将指向有效的缓冲区，如果函数成功，或者为 null。 此批注是可选参数。  
  
-   `_Outref_result_nullonfailure_`  
  
     如果函数失败，返回的指针将指向有效的缓冲区，如果函数成功，或者为 null。 此批注是为引用参数。  
  
## <a name="output-reference-parameters"></a>输出引用参数  
 引用参数的一个常见用途是为 output 参数。  对于简单的输出引用参数 — 例如， `int&`—`_Out_` 提供了正确的语义。  但是，当输出值为指针 — 例如 `int *&`— 等效指针批注喜欢 `_Outptr_ int **` 未提供正确的语义。  为了简洁地表示指针类型的输出引用参数的语义，使用这些复合批注︰  
  
 **批注和说明**  
  
-   `_Outref_`  
  
     结果中后的状态必须是有效，并且不能为 null。  
  
-   `_Outref_result_maybenull_`  
  
     结果在后期状态下，必须是有效，但在后期状态可能为 null。  
  
-   `_Outref_result_buffer_(s)`  
  
     结果中后的状态必须是有效，并且不能为 null。 指向有效的缓冲区大小的 `s` 元素。  
  
-   `_Outref_result_bytebuffer_(s)`  
  
     结果中后的状态必须是有效，并且不能为 null。 指向有效的缓冲区大小的 `s` 字节。  
  
-   `_Outref_result_buffer_to_(s, c)`  
  
     结果中后的状态必须是有效，并且不能为 null。 指向缓冲区的 `s` 元素，其中第一个 `c` 都有效。  
  
-   `_Outref_result_bytebuffer_to_(s, c)`  
  
     结果中后的状态必须是有效，并且不能为 null。 指向缓冲区的 `s` 字节，其中第一个 `c` 都有效。  
  
-   `_Outref_result_buffer_all_(s)`  
  
     结果中后的状态必须是有效，并且不能为 null。 指向有效的缓冲区大小的 `s` 有效元素。  
  
-   `_Outref_result_bytebuffer_all_(s)`  
  
     结果中后的状态必须是有效，并且不能为 null。 指向有效的缓冲区的 `s` 有效元素的字节数。  
  
-   `_Outref_result_buffer_maybenull_(s)`  
  
     结果在后期状态下，必须是有效，但在后期状态可能为 null。 指向有效的缓冲区大小的 `s` 元素。  
  
-   `_Outref_result_bytebuffer_maybenull_(s)`  
  
     结果在后期状态下，必须是有效，但在后期状态可能为 null。 指向有效的缓冲区大小的 `s` 字节。  
  
-   `_Outref_result_buffer_to_maybenull_(s, c)`  
  
     结果在后期状态下，必须是有效，但在后期状态可能为 null。 指向缓冲区的 `s` 元素，其中第一个 `c` 都有效。  
  
-   `_Outref_result_bytebuffer_to_maybenull_(s,c)`  
  
     结果在后期状态下，必须是有效，但在开机自检状态可能为 null。 指向缓冲区的 `s` 字节，其中第一个 `c` 都有效。  
  
-   `_Outref_result_buffer_all_maybenull_(s)`  
  
     结果在后期状态下，必须是有效，但在开机自检状态可能为 null。 指向有效的缓冲区大小的 `s` 有效元素。  
  
-   `_Outref_result_bytebuffer_all_maybenull_(s)`  
  
     结果在后期状态下，必须是有效，但在开机自检状态可能为 null。 指向有效的缓冲区的 `s` 有效元素的字节数。  
  
## <a name="return-values"></a>返回值  
 一个函数的返回值类似于 `_Out_` 参数但不同级别的 de-reference，且无需考虑到结果指针的概念。  对于下列批注，则返回值是带批注的对象 — 标量、 指向一个结构的指针或指向的缓冲区的指针。 这些批注具有相同的语义与相应 `_Out_` 批注。  
  
|||  
|-|-|  
|`_Ret_z_`<br /><br /> `_Ret_writes_(s)`<br /><br /> `_Ret_writes_bytes_(s)`<br /><br /> `_Ret_writes_z_(s)`<br /><br /> `_Ret_writes_to_(s,c)`<br /><br /> `_Ret_writes_maybenull_(s)`<br /><br /> `_Ret_writes_to_maybenull_(s)`<br /><br /> `_Ret_writes_maybenull_z_(s)`|`_Ret_maybenull_`<br /><br /> `_Ret_maybenull_z_`<br /><br /> `_Ret_null_`<br /><br /> `_Ret_notnull_`<br /><br /> `_Ret_writes_bytes_to_`<br /><br /> `_Ret_writes_bytes_maybenull_`<br /><br /> `_Ret_writes_bytes_to_maybenull_`|  
  
## <a name="other-common-annotations"></a>其他常见批注  
 **批注和说明**  
  
-   `_In_range_(low, hi)`  
  
     `_Out_range_(low, hi)`  
  
     `_Ret_range_(low, hi)`  
  
     `_Deref_in_range_(low, hi)`  
  
     `_Deref_out_range_(low, hi)`  
  
     `_Deref_inout_range_(low, hi)`  
  
     `_Field_range_(low, hi)`  
  
     参数、 字段或结果处于范围内 （包括下限） 从 `low` 到 `hi`。  等效于 `_Satisfies_(_Curr_ >= low && _Curr_ <= hi)` 应用于该带批注的对象与相应的预状态或状态后条件。  
  
    > [!IMPORTANT]
    >  尽管名称包含"in"和"out"的语义 `_In_` 和 `_Out_` 执行 **不** 将应用于这些批注。  
  
-   `_Pre_equal_to_(expr)`  
  
     `_Post_equal_to_(expr)`  
  
     带批注的值是精确地 `expr`。  等效于 `_Satisfies_(_Curr_ == expr)` 应用于该带批注的对象与相应的预状态或状态后条件。  
  
-   `_Struct_size_bytes_(size)`  
  
     适用于结构或类声明。  指示该类型的有效对象，可能正在由给定的字节数会大于声明的类型， `size`。  例如：  
  
     `typedef _Struct_size_bytes_(nSize) struct MyStruct {    size_t nSize;    ... };`  
  
     以字节为单位的参数的缓冲区大小 `pM` 类型的 `MyStruct *` 则执行要︰  
  
     `min(pM->nSize, sizeof(MyStruct))`  
  
## <a name="related-resources"></a>相关资源  
 [代码分析团队博客](http://go.microsoft.com/fwlink/?LinkId=251197)  
  
## <a name="see-also"></a>另请参阅  
 [使用 SAL 批注以减少 C/c + + 代码缺陷](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)   
 [了解 SAL](../code-quality/understanding-sal.md)   
 [对函数行为进行批注](../code-quality/annotating-function-behavior.md)   
 [批注结构和类](../code-quality/annotating-structs-and-classes.md)   
 [对锁定行为进行批注](../code-quality/annotating-locking-behavior.md)   
 [指定何时以及在何处应用批注](../code-quality/specifying-when-and-where-an-annotation-applies.md)   
 [内部函数](../code-quality/intrinsic-functions.md)   
 [最佳做法和示例](../code-quality/best-practices-and-examples-sal.md)