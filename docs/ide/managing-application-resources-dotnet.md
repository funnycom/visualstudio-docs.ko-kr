---
title: "응용 프로그램 리소스 관리(.NET) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- msvse_resedit.dlg.SetCustomTool
- msvse_settingsdesigner.err.formatvalue
- msvse_resedit.err.nameblank
- msvse_resedit.err.duplicatename
helpviewer_keywords:
- Resource Designer
- resources [Visual Studio]
- Resources page in Project Designer
- application resources [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2006f565edbca8a859cd2c155645e47e083b5528
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="managing-application-resources-net"></a>응용 프로그램 리소스 관리(.NET)

리소스 파일은 응용 프로그램의 일부이지만 컴파일되지 않는 파일입니다(예: 아이콘 파일 또는 오디오 파일). 이러한 파일은 컴파일 프로세스에 포함되지 않으므로 이진 파일을 다시 컴파일할 필요 없이 변경할 수 있습니다. 응용 프로그램을 지역화할 계획인 경우 모든 문자열 및 응용 프로그램을 지역화할 때 변경해야 하는 다른 리소스에 대해 리소스 파일을 사용해야 합니다.

.NET 데스크톱 앱의 리소스에 대한 자세한 내용은 [Resources in Desktop Apps](/dotnet/framework/resources/index)를 참조하세요.

## <a name="working-with-resources"></a>리소스 작업

관리 코드 프로젝트에서 프로젝트 속성 창을 엽니다. 다음 방법 중 하나로 속성 창을 열 수 있습니다.

- **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성** 선택
- **빠른 실행** 창에 "프로젝트 속성" 입력
- **솔루션 탐색기** 창에서 **Alt**+**Enter** 선택

**리소스** 탭을 선택합니다. 프로젝트에 .resx 파일이 포함되지 않은 경우 하나를 추가하고, 다른 종류의 리소스를 추가 및 삭제하고, 기존 리소스를 수정할 수 있습니다.

## <a name="resources-in-other-project-types"></a>다른 프로젝트 형식의 리소스

.NET 프로젝트의 리소스는 다른 프로젝트 형식과 다른 방식으로 관리됩니다. 리소스에 대한 자세한 내용은 다음을 참조하세요.

- UWP(유니버설 Windows 플랫폼) 앱은 [앱 리소스 및 리소스 관리 시스템](/windows/uwp/app-resources/) 참조
- C++ 프로젝트는 [리소스 파일에 대한 작업](/cpp/windows/working-with-resource-files) 및 [방법: 리소스 파일 만들기](/cpp/windows/how-to-create-a-resource) 참조

## <a name="see-also"></a>참고 항목

[데스크톱 앱의 리소스(.NET Framework)](/dotnet/framework/resources/index)