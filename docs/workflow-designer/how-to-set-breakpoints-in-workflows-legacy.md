---
title: "방법: (레거시) 워크플로에 중단점 설정 | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- breakpoints, setting in workflows
- debugging, setting breakpoints in workflows
- debugging workflows, setting breakpoints
- workflows, setting breakpoints
ms.assetid: 78e0be39-3e99-487c-bfef-19db0daf6f42
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 1e3da1fc5d16591140e59c30422e7ad087b5c7bd
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-set-breakpoints-in-workflows-legacy"></a>방법: 워크플로에 중단점 설정(레거시)
이 항목에서는에 중단점을 설정 하는 방법을 설명 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 레거시 Windows 워크플로 디자이너를 사용 하 여 응용 프로그램 작성. 레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] 응용 프로그램이 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 해야 하는 경우에 사용합니다.

 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]의 레거시 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]를 사용하여 [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] 응용 프로그램을 빌드할 경우 Visual Studio에서 중단점을 설정할 때와 같이 C# 및 Visual Basic 코드에 중단점을 설정할 수 있습니다. 예상대로 설정한 각 중단점에서 워크플로 실행이 중지됩니다.

 중단점에 3 상태가: *보류 중인*, *바인딩된*, 및 *오류*합니다. 중단점을 설정하면 중단점이 보류 중 상태가 되고 속이 빈 빨간색 아이콘으로 표시됩니다. 런타임 시 워크플로 유형을 로드했으면 중단점이 바인딩됨 상태가 되고 속이 찬 빨간색 아이콘으로 표시됩니다. 올바르지 않은 동작 이름처럼 잘못된 형식을 중단점에 대해 지정하면 오류 창이 나타납니다. 그래도 중단점 창에 중단점이 추가되기는 하지만 소문자 "x"로 표시됩니다.

 다음과 같은 방법으로 워크플로 디자인 화면에서 활동에 중단점을 설정할 수 있습니다.

-   활동을 마우스 오른쪽 단추로 클릭 하 고 선택 **중단점 \ 중단점 삽입**합니다.

-   활동을 선택하고 F9 키를 누릅니다.

-   선택 **새 중단점** 에서 **디버그** 메뉴.

     이 옵션을 사용하여 디버깅 중에 새 중단점을 설정할 수도 있습니다. 이렇게 하면 디버거가 중단점에서 중지됩니다.

    > [!NOTE]
    > 호출된 워크플로에는 중단점을 설정할 수 없습니다.

### <a name="to-set-a-breakpoint-using-the-new-breakpoint-option-on-the-debug-menu"></a>디버그 메뉴의 새 중단점 옵션을 사용하여 중단점을 설정하려면

1.  에 **디버그** 메뉴 선택 **새 중단점**합니다.

2.  클릭 **함수에서 중단**합니다.

     **새 중단점** 대화 상자가 열립니다.

3.  에 있는 활동의 이름을 지정는 **함수** 이 구문을 사용 하 여 텍스트 상자: `QualifiedActivityId[:[FullClassName][:InstanceId]]`합니다.

    > [!NOTE]
    > 에 활동 이름을 사용 하는 대신 필요에 따라는 **함수** 텍스트 상자 워크플로 동작의 절대 경로 지정 하 여 중단점을 설정할 수 있습니다. 예를 들어, 이라는 워크플로 솔루션이 있는 **WorkflowConsoleApplication1** 및 라는 솔루션에 워크플로 **Workflow1** 이라는 활동을 사용 하는 **Delay1**. 활동 이름을 사용할 수 있습니다 **Delay1** 으로 경로 지정 하거나 **delay1: workflowconsoleapplication1.workflow1** 또는 **delay1: workflowconsoleapplication1.workflow1: { 6614886A-608E-412B-BF98-99FF1559DDDF}**합니다.

4.  선택은 **IntelliSense 사용 하 여** 확인란 함수 이름을 확인할 수 있습니다.

     이 확인란을 선택하지 않으면 중단점 이름 확인이 수행되지 않습니다.

5.  선택 **워크플로** 에서 **언어** 목록입니다.

6.  **확인**을 클릭합니다.

## <a name="see-also"></a>참고 항목

- [레거시 워크플로 디버깅](../workflow-designer/debugging-legacy-workflows.md)
- [Visual Studio Debugger for Windows Workflow Foundation 호출(레거시)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)