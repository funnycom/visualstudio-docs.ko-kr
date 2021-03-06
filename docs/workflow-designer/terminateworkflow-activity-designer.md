---
title: "TerminateWorkflow 활동 디자이너 | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.TerminateWorkflow.UI
ms.assetid: 08e632ed-0724-4fb4-9df1-f8d443eaf0ac
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 683c482436e968ff9d2a1bd4ce0bbb8e173a5520
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="terminateworkflow-activity-designer"></a>TerminateWorkflow 활동 디자이너
**TerminateWorkflow** 활동 디자이너는 만들고 구성 하는 데 사용 되는 <xref:System.Activities.Statements.TerminateWorkflow> 활동입니다.

## <a name="the-terminateworkflow-activity"></a>TerminateWorkflow 활동
 <xref:System.Activities.Statements.TerminateWorkflow> 활동은 워크플로의 실행을 종료합니다.

### <a name="using-the-terminateworkflow-activity-designer"></a>TerminateWorkflow 활동 디자이너 사용
 **TerminateWorkflow** 활동 디자이너에서 확인할 수 있습니다는 **런타임** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구상자** 탭 (또는 선택 **도구 상자** 에서 **보기** 메뉴나 CTRL + ALT + X.)

 **TerminateWorkflow** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 끌어다는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에 나 활동은 일반적으로, 등 배치는 <xref:System.Activities.Statements.Sequence>합니다. 그렇기 때문에 <xref:System.Activities.Statements.TerminateWorkflow> 기본값 활동 **DisplayName** TerminateWorkflow입니다. <xref:System.Activities.Activity.DisplayName%2A> 의 헤더에서 편집할 수는 **TerminateWorkflow** 활동 디자이너 또는 **DisplayName** 속성 표의 상자입니다.

### <a name="the-terminateworkflow-properties"></a>TerminateWorkflow 속성
 다음 표에서는 <xref:System.Activities.Statements.TerminateWorkflow> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 이러한 속성은 속성 표에서 편집할 수 있으며 일부 속성은 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면에서 편집할 수 있습니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.TerminateWorkflow> 활동의 이름입니다. 기본값은 TerminateWorkflow입니다. 표시 이름이 꼭 필요하지 않더라도 표시 이름을 사용하는 것이 좋습니다.|
|<xref:System.Activities.Statements.TerminateWorkflow.Exception%2A>|False|워크플로가 종료될 때 throw할 예외입니다. 이 속성은 속성 표에서 설정합니다.|
|<xref:System.Activities.Statements.TerminateWorkflow.Reason%2A>|False|워크플로가 왜 종료되었는지 설명하는 이유입니다. 이 속성은 속성 표에서 설정합니다.|

## <a name="see-also"></a>참고 항목

- [런타임](../workflow-designer/runtime-activity-designers.md)
- [유지](../workflow-designer/persist-activity-designer.md)