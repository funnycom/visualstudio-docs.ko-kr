---
title: "레거시 상태 시스템 워크플로 디자이너를 사용 하 여 | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- StateFinalizationActivity activity
- StateActivity activity
- SetStateActivity activity
- EventDrivenActivity activity
- state machine workflow designer
- state machine workflows, designer
- state machine workflows, activities
- StateInitializationActivity activity
ms.assetid: 2cd21123-35c2-4eaf-82f6-86fce7a8f04d
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ebf214ce8e65ba65127d82686770b00cfd8d3f90
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="using-the-legacy-state-machine-workflow-designer"></a>레거시 상태 시스템 워크플로 디자이너 사용
새 상태 시스템 워크플로 프로젝트를 만드는 경우 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] 를 대상으로 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 사용 하 여 선택할 수 있습니다는 **상태 시스템 워크플로 콘솔 응용 프로그램** 또는  **상태 시스템 워크플로 라이브러리** 레거시 프로젝트 템플릿을 합니다. 이러한 상태 시스템 프로젝트 템플릿 중 하나를 선택하면 상태 시스템 디자이너가 레거시 워크플로 디자이너 사용자 인터페이스로 나타납니다. 레거시 상태 시스템 프로젝트 템플릿에 대 한 정보를 참조 하십시오. [하는 방법: 만들기 상태 시스템 워크플로 콘솔 응용 프로그램 (레거시)](../workflow-designer/how-to-create-state-machine-workflow-console-applications-legacy.md) 및 [하는 방법: 상태 시스템 워크플로 라이브러리 (레거시)만들기](../workflow-designer/how-to-create-a-state-machine-workflow-library-legacy.md).

 상태 시스템 워크플로는 상태 집합으로 구성됩니다. 하나의 상태가 초기 상태로 표시됩니다. 각 상태는 특정 이벤트 집합을 받을 수 있으며 이벤트에 따라 다른 상태로 전환될 수 있습니다. 상태 시스템 워크플로는 최종 상태를 가질 수 있으며, 최종 상태로 전환되면 워크플로가 완료됩니다.

## <a name="state-machine-designer-views"></a>상태 시스템 디자이너 뷰
 상태 시스템 디자이너는 자유형 디자이너로서, 디자인 화면에서 활동을 자유롭게 이동할 수 있습니다. 상태 시스템 디자이너에는 두 개의 보기가: *상태* 보기 및 *이벤트 구동* 보기.

 상태 뷰에서는 상태 활동 및 상태 활동에 포함할 수 있는 이벤트 구동 활동을 표시합니다. 이 뷰에서는 상태 전환이 한 상태의 이벤트 구동 활동에서 다른 상태로 이어지는 선으로 표현됩니다. 직접 선을 그려서 전환을 만들 수도 있습니다. 전환을 그리려면 이벤트 구동 활동을 선택한 다음 해당 활동의 핸들 중 하나를 선택하여 끕니다. 그러면 선이 그려집니다. 그려진 선은 대상 상태에 연결되어 상태 전환을 나타냅니다.

 이벤트 구동 뷰에 액세스하려면 이벤트 구동 활동을 두 번 클릭합니다. 순차 Workflow Designer와 매우 비슷한 디자이너가 나타납니다. 디자이너 맨 위의 탐색 모음은 활동의 계층 구조를 표시하며 이 계층 구조에는 이벤트 구동 활동까지 나타납니다. 표시된 계층 구조에서 임의의 요소를 클릭하면 상태 뷰로 돌아갈 수 있습니다. 상태 뷰에서 상태 전환을 그렸고 해당 활동의 이벤트 구동 뷰를 표시하려는 경우, 설정된 상태 활동이 이벤트 구동 활동에 추가됩니다. 설정된 상태 활동의 속성을 변경하면 이는 다시 상태 뷰에 반영됩니다.

## <a name="state-machine-workflow-activities"></a>상태 시스템 워크플로 활동
 다음 표에서는 상태 시스템 Workflow Designer에서 사용되는 핵심 활동에 대해 설명합니다.

|도구 상자 이름|동작|설명|
|------------------|--------------|-----------------|
|**상태**|[StateActivity](http://go.microsoft.com/fwlink?LinkID=65042)|상태 시스템;의 상태를 나타냅니다. 추가 포함 될 수 있습니다 **StateActivity** 활동입니다. 자세한 내용은 참조 [StateActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65083)합니다.|
|**SetState**|[SetStateActivity](http://go.microsoft.com/fwlink?LinkID=65041)|새 상태로의 전환을 지정합니다. 자세한 내용은 참조 [SetStateActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65082)합니다.|
|**StateInitialization**|[StateInitializationActivity](http://go.microsoft.com/fwlink?LinkID=65044)|상태가 시작되면 실행되며, 다른 활동을 포함할 수도 있습니다. 자세한 내용은 참조 [StateInitialization 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65006)합니다.|
|**StateFinalization**|[StateFinalizationActivity](http://go.microsoft.com/fwlink?LinkID=65043)|벗어날 때 포함 된 활동을 실행 한 [StateActivity](http://go.microsoft.com/fwlink?LinkID=65042) 활동입니다. 자세한 내용은 참조 [StateFinalizationActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65008)합니다.|
|**EventDriven**|[EventDrivenActivity](http://go.microsoft.com/fwlink?LinkID=65029)|실행 시작 여부가 외부 이벤트에 따라 달라지는 상태에 사용됩니다. **EventDrivenActivity** 활동 구현 하는 활동이 있어야 합니다.는 [IEventActivity](http://go.microsoft.com/fwlink?LinkID=65032) 첫 번째 자식 활동으로 인터페이스입니다. 자세한 내용은 참조 [EventDrivenActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65068)합니다.|

 상태 시스템 워크플로의 기본 구성 요소는 [StateActivity](http://go.microsoft.com/fwlink?LinkID=65042) 활동입니다. 상태 시스템 워크플로의 여러 지점에서 이벤트가 캡처되므로 이벤트와 연결된 작업을 처리하기 위해 여러 상태가 시작됩니다. 워크플로 수명 중에 워크플로가 여러 상태를 끝내고 시작할 수 있습니다. 사용 하 여 서로 연결 하는 이러한 상태는 [SetStateActivity](http://go.microsoft.com/fwlink?LinkID=65041) 활동입니다.

 새 끌어 오면 **StateActivity** 워크플로 디자인 화면에 추가할 수 있습니다 [EventDrivenActivity](http://go.microsoft.com/fwlink?LinkID=65029), [StateInitializationActivity](http://go.microsoft.com/fwlink?LinkID=65044), [ StateFinalizationActivity](http://go.microsoft.com/fwlink?LinkID=65043), 추가 또는 **StateActivity** 자식 활동으로 작업 합니다.

> [!CAUTION]
> 상태 시스템 워크플로 디자이너를 사용 하 여 워크플로 만들 때와 디자인 중인 워크플로의 구조를 모니터링 해야는 **문서 개요** 뷰 창. 에 상태 시스템 워크플로의 구조 뷰는 **문서 개요** 보기 창 워크플로 마크업 파일의 활동에에서 대 한 논리 레이아웃을 미러링합니다. 디자인 화면에 나타나는 워크플로 활동의 실제 레이아웃은 워크플로 마크업 파일의 활동에 대한 논리 레이아웃을 미러링하지 않을 수도 있습니다.
>
> 열려는 **문서 개요** 창에는 **보기** 메뉴에서 **다른 창**를 선택한 후 **문서 개요**합니다.

## <a name="see-also"></a>참고 항목

- [방법: 상태 시스템 워크플로 콘솔 응용 프로그램 만들기(레거시)](../workflow-designer/how-to-create-state-machine-workflow-console-applications-legacy.md)
- [방법: 상태 시스템 워크플로 라이브러리 만들기(레거시)](../workflow-designer/how-to-create-a-state-machine-workflow-library-legacy.md)
- [상태 시스템 워크플로](http://go.microsoft.com/fwlink?LinkID=65016)
- [StateActivity 활동 사용](http://go.microsoft.com/fwlink?LinkID=65083)
- [StateInitializationActivity 활동 사용](http://go.microsoft.com/fwlink?LinkID=65006)
- [StateFinalizationActivity 활동 사용](http://go.microsoft.com/fwlink?LinkID=65008)
- [SetStateActivity 활동 사용](http://go.microsoft.com/fwlink?LinkID=65082)
- [EventDrivenActivity 활동 사용](http://go.microsoft.com/fwlink?LinkID=65068)