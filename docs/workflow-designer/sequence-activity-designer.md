---
title: "활동 디자이너를 시퀀스 | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Sequence.UI
ms.assetid: 51c8d3cb-4d43-458f-9631-b63755f9ac94
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 64ec037433ca4ff984628994ba2bf353ad8e365c
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="sequence-activity-designer"></a>Sequence 활동 디자이너
<xref:System.Activities.Statements.Sequence> 활동에는 순서대로 실행되는 정렬된 자식 활동 컬렉션이 들어 있습니다.

 활동 집합을 순서대로 실행하는 또 다른 방법은 <xref:System.Activities.Statements.Flowchart> 활동을 사용하는 것입니다. 사용 하는 것이 좋습니다는 [순서도](../workflow-designer/flowchart-activity-designer.md) 설치한 경우 간단한 분기 또는 diagrammatically 모델링 하려는 프로그램 흐름을 반복 합니다.

## <a name="using-the-sequence-activity-designer"></a>Sequence 활동 디자이너 사용
 추가 하는 <xref:System.Activities.Statements.Sequence> 활동을 끌어는 **시퀀스** 활동 디자이너를는 **도구 상자** Windows 워크플로 디자이너 화면에 놓습니다. 이 자식 활동을 추가 하려면 <xref:System.Activities.Statements.Sequence> 활동, 다른 활동을 끌어는 **도구 상자** 를 "여기에 작업 놓기" 힌트 텍스트가 표시 된 상자의 삼각형 놓습니다.

### <a name="sequence-activity-properties-in-the-workflow-designer"></a>워크플로 디자이너의 Sequence 활동 속성
 다음 표에서는 <xref:System.Activities.Statements.Sequence> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 이러한 속성은 속성 표 또는 디자이너 화면에서 편집할 수 있습니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|머리글에 <xref:System.Activities.Statements.Sequence> 활동 디자이너의 이름을 지정합니다. 기본값은 Sequence입니다. 속성 표에서 또는 활동 디자이너의 머리글에서 직접 값을 편집할 수 있습니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|

## <a name="see-also"></a>참고 항목

- [워크플로](../workflow-designer/flowchart-activity-designer.md)
- [제어 흐름](../workflow-designer/control-flow-activity-designers.md)