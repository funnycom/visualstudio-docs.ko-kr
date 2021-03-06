---
title: "레거시 워크플로 디자이너를 사용 하 여 | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Visual Studio 2005 Extensions for Windows Workflow Foundation, about
ms.assetid: 7af53077-afd7-465f-9c1d-b387e9d4f216
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: a042d98019b7f618792f7a9104d262362a4e6e3d
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="using-the-legacy-workflow-designer"></a>레거시 워크플로 디자이너 사용
[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 또는 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]를 대상으로 하려는 경우 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)]에서 제공하는 레거시 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 사용할 수 있습니다.

 선택 하 여 액세스 하는 것은 **.NET Framework 3.0** 옵션 또는 **.NET Framework 3.5** 목록 맨 위에 있는 드롭다운에서 **새 프로젝트** 창. 기본 옵션 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] 은 **.NET Framework 4** 만드는 데 사용 되는 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 대상으로 하는 응용 프로그램은 [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)]합니다.

 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]에서는 친숙한 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 사용자 인터페이스를 사용하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 응용 프로그램을 시각적으로 만들 수 있습니다. [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 응용 프로그램은 활동이라고 하는 워크플로 프로세스 단계로 구성됩니다. 해당 활동 디자이너를 디자이너를 끌어 디자인 화면에 활동을 작성 워크플로 만들려면 **도구 상자** 디자인 화면으로 합니다.

 다음 표에서는 Windows Workflow Foundation용 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 주요 기능을 보여 줍니다.

|기능|설명|
|-------------|-----------------|
|활동 끌어서 놓기|활동을 끌어는 **도구 상자** 워크플로를 만드는 디자인 화면으로 합니다.|
|속성 브라우저|표준 **속성** 창을 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 활동의 속성을 구성 하는 데 사용 됩니다.|
|확대/축소|쌍안경 모양의 **확대/축소 수준** 아이콘은 디자인 화면 오른쪽에 세로 스크롤 막대 아래에 있습니다. 워크플로 그래픽을 확대하거나 축소하려면 쌍안경을 클릭하고 확대/축소 백분율을 선택합니다. 사용할 수도 있습니다는 **팬** 확대 / 축소 아이콘 돋보기 커서 옵션입니다.|
|이동|**팬** 네 방향을 가리키는 네 개의 교차 화살표를 포함 하는 원 아이콘은 쌍안경 확대/축소 아이콘의 바로 아래 디자인 화면 오른쪽에 세로 스크롤 막대 아래에 있습니다. 팬 아이콘을 클릭하면 팝업 메뉴가 나타나 다음과 같은 커서 옵션을 제공합니다.<br /><br /> - **확대** 돋보기 커서로 디자인 화면을 클릭 하면 확대할 수 있습니다.<br />- **축소** 돋보기 커서로 디자인 화면을 클릭 하면 축소할 수 있습니다.<br />- **탐색 도구** 손 모양 커서를 사용 하면 "잡아" 디자인 화면에서 워크플로의 보기.<br />- **기본** 화살표 커서를 사용 하면 다른 커서에서 기본 화살표 커서로 전환할 수 있습니다.|
|자동 스크롤|워크플로가 큰 경우 디자인 화면의 가시 영역을 바깥으로 활동을 배치할 수 있습니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 활동을 배치할 위치와 가장 가까운 디자인 화면의 가장자리 쪽으로 활동을 끌 수 있습니다. 그러면 디자인 화면 뷰가 자동으로 그 방향으로 이동합니다.|
|스마트 태그|완전히 구성되지 않거나 올바르지 않게 구성된 활동은 느낌표 아이콘으로 표시됩니다. 이 아이콘을 클릭하면 해당 활동에 대한 구성 요구 사항 보여 주는 드롭다운 목록이 나타납니다. 그런 다음 사용할 수는 **속성** 창에서 작업을 적절 하 게 구성할 수 있습니다. 활동의 모든 속성이 올바르게 구성되면 느낌표 아이콘이 사라집니다.|

## <a name="see-also"></a>참고 항목

- [워크플로 개발](http://go.microsoft.com/fwlink?LinkID=65010)