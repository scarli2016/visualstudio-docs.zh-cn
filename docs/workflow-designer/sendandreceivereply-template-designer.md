---
title: 工作流设计器-SendAndReceiveReply 模板设计器
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.SendAndReceiveReply.UI
- System.ServiceModel.Activities.ReceiveReply.UI
ms.assetid: 818a8c84-6593-416d-b016-1d91b85ffb68
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4c6a4749ed138b22ac3d600befad01ef1776478e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="sendandreceivereply-template-designer"></a>SendAndReceiveReply 模板设计器

**SendAndReceiveReply**使用模板来创建一对预配置<xref:System.ServiceModel.Activities.Send>和<xref:System.ServiceModel.Activities.ReceiveReply>内的活动<xref:System.Activities.Statements.Sequence>作为请求/响应消息交换的一部分而关联的活动客户端上的模式。

## <a name="the-sendandreceivereply-template"></a>SendAndReceiveReply 模板

添加**SendAndReceiveReply**模板执行除了创建三个操作<xref:System.ServiceModel.Activities.Send>和<xref:System.ServiceModel.Activities.ReceiveReply>内的活动<xref:System.Activities.Statements.Sequence>活动：

1.  配置 <xref:System.ServiceModel.Activities.Send.OperationName%2A> 活动的 <xref:System.ServiceModel.Activities.Send.ServiceContractName%2A> 和 <xref:System.ServiceModel.Activities.Send> 属性。

2.  将 <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> 活动的 <xref:System.ServiceModel.Activities.ReceiveReply> 属性绑定到 <xref:System.ServiceModel.Activities.Send> 活动。

3.  创建一个 <xref:System.ServiceModel.Activities.CorrelationHandle> 作为父活动中的一个变量。

### <a name="using-the-sendandreceivereply-template-designer"></a>使用 SendAndReceiveReply 模板设计器
 **SendAndReceiveReply**在找不到活动设计器**消息**类别**工具箱**，通过单击访问的哪一**工具箱**工作流设计器上的选项卡 (或者，选择**工具栏**从**视图**菜单上或 CTRL + ALT + X。)

 **SendAndReceiveReply**活动设计器可以拖动从**工具箱**和放置到工作流设计器图面，只要通常放置活动的。 这将创建<xref:System.ServiceModel.Activities.Send>可以使用配置的活动**发送**活动设计器和相关<xref:System.ServiceModel.Activities.ReceiveReply>，可以使用配置**ReceiveReplyForSend**设计器。

 有关使用**发送**设计器配置<xref:System.ServiceModel.Activities.Send>活动，请参阅[发送](../workflow-designer/send-activity-designer.md)主题。

 有关使用**ReceiveReplyForSend**设计器配置<xref:System.ServiceModel.Activities.ReceiveReply>活动，请参阅以下部分。

### <a name="properties-of-receivereply"></a>ReceiveReply 的属性
 下表列出 <xref:System.ServiceModel.Activities.ReceiveReply> 属性并说明如何在设计器中使用它们。 可以在属性网格中编辑这些属性和一些可以在工作流 Designerdesigner 图面上编辑。

|属性名|必需|用法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.ServiceModel.Activities.ReceiveReply> 活动的可选友好名称。 默认值为 ReceiveReplyForSend。<br /><br /> 虽然对友好 <xref:System.Activities.Activity.DisplayName%2A> 使用非默认值不是绝对必需的，但最好使用非默认值。|
|<xref:System.ServiceModel.Activities.ReceiveReply.Request%2A>|True|对与此 <xref:System.ServiceModel.Activities.Send> 活动配对的 <xref:System.ServiceModel.Activities.ReceiveReply> 活动的引用。 此属性不得为**null**。 在客户端上将 <xref:System.ServiceModel.Activities.Send> 和 <xref:System.ServiceModel.Activities.ReceiveReply> 活动配合使用，可对请求/响应消息模式建模。 此属性指定配对的 <xref:System.ServiceModel.Activities.Send> 活动。 在该设计器中无法编辑此属性，因为它自动绑定到从中创建了 <xref:System.ServiceModel.Activities.Send> 活动的 <xref:System.ServiceModel.Activities.ReceiveReply> 活动。|
|<xref:System.ServiceModel.Activities.ReceiveReply.Content%2A>|False|指定要接收的消息或参数内容。 它可为 <xref:System.ServiceModel.Activities.ReceiveMessageContent> 活动或 <xref:System.ServiceModel.Activities.ReceiveParametersContent> 活动。 通过单击旁的省略号按钮来编辑此属性**内容**在属性网格或单击字段**定义...** 按钮旁边**内容**上的标签**接收**活动设计器图面。 两者都显示**内容定义**对话框。 有关如何使用此框的详细信息，请参阅[内容定义对话框](../workflow-designer/content-definition-dialog-box.md)主题。|
|<xref:System.ServiceModel.Activities.ReceiveReply.CorrelationInitializers%2A>|False|指定在工作流中对配置此 <xref:System.ServiceModel.Activities.CorrelationInitializer> 活动的多个 <xref:System.ServiceModel.Activities.CorrelationHandle> 对象进行初始化的 <xref:System.ServiceModel.Activities.Receive> 对象的集合。 单击省略号按钮旁边<xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>属性在属性网格中，若要打开**添加相关初始值设定项**对话框。 有关使用此框的详细信息，请参阅[添加 CorrelationInitializers 对话框](../workflow-designer/add-correlationinitializers-dialog-box.md)主题。|
|<xref:System.ServiceModel.Activities.ReceiveReply.Action%2A>|False|指定消息的操作标头。 如果未显式设置，则它的默认值为：<br /><br /> **https://tempuri.org/{service 协定命名空间} / {服务协定名称} / {操作名称}。**|

## <a name="see-also"></a>请参阅

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [接收](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [发送](../workflow-designer/send-activity-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)