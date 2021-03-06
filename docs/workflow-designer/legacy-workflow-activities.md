---
title: "레거시 워크플로 활동 | Microsoft Docs"
ms.date: 01/18/2017
ms.topic: reference
helpviewer_keywords:
- workflows, activities
- activities
- workflow activities
ms.assetid: 4af7a06b-1e82-43c8-aec8-0dc5fb63d08a
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 61c719725f3d4ebfffe291ff31115ddd0cc5f3d4
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="legacy-workflow-activities"></a>레거시 워크플로 활동

[!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]에는 제어 흐름, 조건, 이벤트 처리, 상태 관리, 응용 프로그램 및 서비스와의 통신을 위한 기능을 제공하는 일련의 기본 활동이 포함되어 있습니다. Windows 워크플로 디자이너에서 제공 되는 시스템 제공 활동을 사용 하 고 워크플로 디자인할 때 또는 사용자 지정 작업을 만들 수 있습니다.

 다음 표에서는 기본적으로 제공되는 [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)]프레임워크 활동 집합을 보여 줍니다. 아니지만 일부, 이러한 활동의 활동 디자이너에서 액세스할 수 있는으로 표시 됩니다는 **도구 상자** 의 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]합니다. 활동을 만들려면 해당 디자이너를 끌어는 **도구 상자** 디자인 화면에 놓습니다.

|활동|설명|
|--------------|-----------------|
|<xref:System.Workflow.Activities.CallExternalMethodActivity>|함께 사용 된 **HandleExternalEventActivity** 로컬 서비스와 입 / 출력 통신에 대 한 활동입니다. 자세한 내용은 참조 [CallExternalMethodActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65060)합니다.|
|**System.Workflow.Activities.CancellationHandlerActivity**|모든 복합 활동의 자식 활동이 실행을 완료하기 전에 취소된 복합 활동의 정리 논리를 포함시킬 때 사용합니다. 자세한 내용은 참조 [CancellationHandlerActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65061)합니다.|
|<xref:System.Workflow.Activities.CodeActivity>|워크플로에 Visual Basic 또는 C# 코드를 추가할 수 있도록 합니다. 자세한 내용은 참조 [CodeActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65062)합니다.|
|<xref:System.Workflow.Activities.CompensatableSequenceActivity>|<xref:System.Workflow.Activities.SequenceActivity>의 보정 가능한 버전입니다 자세한 내용은 참조 [CompensatableSequenceActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65002)합니다.|
|**System.Workflow.Activities.CompensatableTransactionScopeActivity**|보정 가능한 버전 **TransactionScopeActivity**합니다. 자세한 내용은 참조 [CompensatableTransactionScopeActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65063)합니다.|
|**System.Workflow.Activities.CompensateActivity**|오류가 발생하면 워크플로에서 이미 수행한 작업을 실행 취소하거나 보정하기 위해 코드를 호출할 수 있도록 합니다. 자세한 내용은 참조 [CompensateActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65064)합니다.|
|**System.Workflow.Activities.CompensationHandlerActivity**|자세한 내용은 완료 된 TransactionScopeActivity 활동에 대 한 보정을 수행 하는 하나 이상의 활동에 대 한 래퍼 참조 [CompensationHandlerActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65065)합니다.|
|<xref:System.Workflow.Activities.ConditionedActivityGroup>|<xref:System.Workflow.Activities.ConditionedActivityGroup> 활동 자체에 적용되는 조건과 각 자식에 별도로 적용되는 조건에 따라 자식 활동을 실행합니다. 자세한 내용은 참조 [ConditionedActivityGroup 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65066)합니다.|
|<xref:System.Workflow.Activities.DelayActivity>|시간 제한 간격을 기반으로 한 지연을 워크플로에 빌드할 수 있습니다. 자세한 내용은 참조 [DelayActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65067)합니다.|
|<xref:System.Workflow.Activities.EventDrivenActivity>|지정된 이벤트가 발생할 때 실행되는 활동을 하나 이상 래핑합니다. 자세한 내용은 참조 [EventDrivenActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65068)합니다.|
|<xref:System.Workflow.Activities.EventHandlersActivity>|이벤트와 활동을 연결하는 프레임워크를 제공합니다. 자세한 내용은 참조 [EventHandlersActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65069)합니다.|
|<xref:System.Workflow.Activities.EventHandlingScopeActivity>|와 동시에 기본 자식 활동을 실행 한 <xref:System.Workflow.Activities.EventHandlersActivity>합니다. 자세한 내용은 참조 [EventHandlingScopeActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65070)합니다.|
|**System.Workflow.Activities.FaultHandlerActivity**|지정하는 형식의 예외를 처리하는 데 사용합니다. 자세한 내용은 참조 [FaultHandlerActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65071)합니다.|
|**System.Workflow.Activities.FaultHandlersActivity**|순서가 지정 된 형식의 자식 활동 목록이 있는 복합 활동을 나타내는 **System.Workflow.Activities.FaultHandlerActivity**합니다. 자세한 내용은 참조 [FaultHandlersActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65072)합니다.|
|<xref:System.Workflow.Activities.HandleExternalEventActivity>|와 함께에서 사용 되는 <xref:System.Workflow.Activities.CallExternalMethodActivity> 로컬 서비스와 입 / 출력 통신에 대 한 활동입니다. 자세한 내용은 참조 [HandleExternalEventActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65073)합니다.|
|<xref:System.Workflow.Activities.IfElseActivity>|각 분기에서 조건을 테스트 하 고 고 조건이 있는 첫 번째 분기에서 활동을 수행 **true**합니다. 자세한 내용은 참조 [IfElseActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65074)합니다.|
|<xref:System.Workflow.Activities.IfElseBranchActivity>|<xref:System.Workflow.Activities.IfElseActivity>의 분기를 나타냅니다. 자세한 내용은 참조 [IfElseBranchActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65075)합니다.|
|<xref:System.Workflow.Activities.InvokeWebServiceActivity>|워크플로에서 웹 서비스를 호출할 수 있도록 합니다. 자세한 내용은 참조 [InvokeWebServiceActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65076)합니다.|
|<xref:System.Workflow.Activities.InvokeWorkflowActivity>|워크플로에서 다른 워크플로를 호출할 수 있도록 합니다. 자세한 내용은 참조 [InvokeWorkflowActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65077)합니다.|
|<xref:System.Workflow.Activities.ListenActivity>|<xref:System.Workflow.Activities.EventDrivenActivity> 자식 활동만 포함된 복합 활동입니다. 자세한 내용은 참조 [ListenActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65078)합니다.|
|<xref:System.Workflow.Activities.ParallelActivity>|둘 이상의 자식을 예약 하는 방법을 제공 **SequenceActivity** 활동 분기가 동시에 처리 합니다. 자세한 내용은 참조 [ParallelActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65079)합니다.|
|<xref:System.Workflow.Activities.PolicyActivity>|규칙 컬렉션을 나타낼 때 사용합니다. 규칙은 조건과 그 결과 작업으로 구성됩니다. 자세한 내용은 참조 [PolicyActivity 활동 사용](http://go.microsoft.com/fwlink?LinkID=65004)합니다.|
|<xref:System.Workflow.Activities.ReplicatorActivity>|단일 자식 활동의 여러 인스턴스를 만듭니다. 자세한 내용은 참조 [ReplicatorActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65080)합니다.|
|<xref:System.Workflow.Activities.SequenceActivity>|순차 실행을 위해 여러 활동을 함께 연결하는 간단한 방법을 제공합니다. 자세한 내용은 참조 [SequenceActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65081)합니다.|
|<xref:System.Workflow.Activities.SetStateActivity>|새 상태로의 전환을 지정합니다. 자세한 내용은 참조 [SetStateActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65082)합니다.|
|<xref:System.Workflow.Activities.StateActivity>|상태 시스템 워크플로의 상태를 나타냅니다. 자세한 내용은 참조 [StateActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65083)합니다.|
|<xref:System.Workflow.Activities.StateFinalizationActivity>|에 사용 되는 <xref:System.Workflow.Activities.StateActivity> 활동 종료 될 때 실행 되는 하위 작업에 대 한 컨테이너로 **StateActivity** 활동입니다. 자세한 내용은 참조 [StateFinalizationActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65008)합니다.|
|<xref:System.Workflow.Activities.StateInitializationActivity>|에 사용 되는 <xref:System.Workflow.Activities.StateActivity> 활동을 입력할 때 실행 되는 자식 작업에 대 한 컨테이너로 **StateActivity** 활동입니다. 자세한 내용은 참조 [StateInitializationActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65006)합니다.|
|**System.Workflow.Activities.SuspendActivity**|특별한 주의가 필요한 일부 오류 조건이 발생할 경우 개입할 수 있도록 워크플로 작업을 일시 중단합니다. 자세한 내용은 참조 [SuspendActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65084)합니다.|
|**System.Workflow.Activities.SynchronizationScopeActivity**|동기화된 도메인에서 포함된 활동을 순차적으로 실행합니다. 자세한 내용은 참조 [SynchronizationScopeActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65085)합니다.|
|**System.Workflow.Activities.TerminateActivity**|오류 조건이 발생할 경우 즉시 워크플로 작업을 중지할 수 있도록 합니다. 자세한 내용은 참조 [TerminateActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65086)합니다.|
|**System.Workflow.Activities.ThrowActivity**|워크플로에 대해 프로세스 메타데이터의 일부로 throw된 비즈니스 예외를 캡처할 수 있도록 합니다. 자세한 내용은 참조 [ThrowActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65087)합니다.|
|**System.Workflow.Activities.TransactionScopeActivity**|트랜잭션 및 예외 처리를 위한 프레임워크를 제공합니다. 자세한 내용은 참조 [TransactionScopeActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65088)합니다.|
|<xref:System.Workflow.Activities.WebServiceFaultActivity>|웹 서비스 오류 발생을 모델링할 수 있습니다. 자세한 내용은 참조 [WebServiceFaultActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65089)합니다.|
|<xref:System.Workflow.Activities.WebServiceInputActivity>|웹 서비스에서 데이터를 받습니다. 자세한 내용은 참조 [WebServiceInputActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65090)합니다.|
|<xref:System.Workflow.Activities.WebServiceOutputActivity>|워크플로에 대한 웹 서비스 요청에 응답합니다. 자세한 내용은 참조 [WebServiceOutputActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65092)합니다.|
|<xref:System.Workflow.Activities.WhileActivity>|조건이 충족될 때까지 워크플로가 반복될 수 있도록 합니다. 자세한 내용은 참조 [WhileActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65091)합니다.|

 사용자 지정 활동을 만드는 방법에 대 한 자세한 내용은 참조 [사용자 지정 활동 개발](http://go.microsoft.com/fwlink?LinkID=65023) 및 [레거시 활동 디자이너를 사용 하 여](../workflow-designer/using-the-legacy-activity-designer.md)합니다.

## <a name="see-also"></a>참고 항목

- [Windows Workflow Foundation 활동](http://go.microsoft.com/fwlink?LinkID=65005)
- [워크플로 개발](http://go.microsoft.com/fwlink?LinkID=65010)
- [워크플로 활동 개발](http://go.microsoft.com/fwlink?LinkID=65023)