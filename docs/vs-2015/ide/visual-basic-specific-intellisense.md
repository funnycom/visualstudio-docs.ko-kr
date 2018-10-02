---
title: Visual Basic 관련 IntelliSense | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IntelliSense [Visual Basic]
- IntelliSense [Visual Studio], Visual Basic
ms.assetid: 4dec8753-05e5-4f74-b304-5f8c4ed8723b
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9bae55b10695ba73fec86d7ab63943e3440e3f05
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47556959"
---
# <a name="visual-basic-specific-intellisense"></a>Visual Basic 관련 IntelliSense
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [Visual Basic 관련 IntelliSense](https://docs.microsoft.com/visualstudio/ide/visual-basic-specific-intellisense)합니다.  
  
Visual Basic 소스 코드 편집기는 다음과 같은 IntelliSense 기능을 제공합니다.  
  
-   구문 팁  
  
     구문 팁은 입력하는 문의 구문을 표시합니다. [선언](http://msdn.microsoft.com/library/d3f21fb0-b804-4c99-97ed-583b23894cf1)과 같은 문에 유용합니다.  
  
## <a name="automatic-completion"></a>자동 완성  
  
-   다양한 키워드에 대한 완성  
  
     예를 들어 `goto` 및 공백을 입력하는 경우 IntelliSense는 드롭다운 메뉴에서 정의된 레이블 목록을 표시합니다. 지원되는 다른 키워드에는 `Exit`, `Implements`, `Option` 및 `Declare`가 포함됩니다.  
  
-   `Enum` 및 `Boolean` 완료  
  
     문이 열거형의 멤버를 참조하는 경우 IntelliSense는 `Enum`의 멤버 목록을 표시합니다. 문이 `Boolean`을 참조하는 경우 IntelliSense는 true-false 드롭다운 메뉴를 표시합니다.  
  
 **Visual Basic** 폴더의 **일반** 속성 페이지에서 **멤버 목록 자동 표시**의 선택을 해제하여 완료를 기본적으로 끌 수 있습니다.  
  
 멤버 목록, 단어 자동 완성 또는 ALT+오른쪽 화살표를 호출하여 완료를 수동으로 실행할 수 있습니다. 자세한 내용은 [IntelliSense 사용](../ide/using-intellisense.md)을 참조하세요.  
  
## <a name="intellisense-in-zone"></a>영역 내 IntelliSense  
 영역 내 IntelliSense는 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]를 통해 응용 프로그램을 배포해야 하는 Visual Basic 개발자에게 도움을 주며 부분 신뢰 설정으로 제한됩니다. 이 기능:  
  
-   응용 프로그램을 실행할 사용 권한을 선택할 수 있습니다.  
  
-   선택한 영역의 API를 멤버 목록에서 사용할 수 있는 상태로 표시하고, 추가 사용 권한이 필요한 API를 사용할 수 없는 상태로 표시합니다.  
  
 자세한 내용은 [ClickOnce 응용 프로그램의 코드 액세스 보안](../deployment/code-access-security-for-clickonce-applications.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IntelliSense 사용](../ide/using-intellisense.md)


