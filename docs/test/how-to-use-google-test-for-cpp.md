---
title: "Visual Studio에서 Google Test for C++를 사용하는 방법 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
author: mikeblome
ms.openlocfilehash: c7f7c9a4532175569fd32f964187eacab0a2017f
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2018
---
# <a name="how-to-use-google-test-for-c-in-visual-studio"></a>Visual Studio에서 Google Test for C++를 사용하는 방법
**Visual Studio 2017 버전 15.5** 이상에서는 Google 테스트가 **C++를 통한 데스크톱 개발** 워크로드의 기본 구성 요소로 Visual Studio IDE에 통합되어 있습니다. 사용자의 컴퓨터에 설치되었는지 확인하려면 Visual Studio 설치 관리자를 열고 워크로드 구성 요소 목록에서 Google Test를 찾습니다.

![Google Test 설치](media/cpp-google-component.png "Google Test for C++ 설치")

## <a name="add-a-google-test-project-to-the-solution"></a>Google Test 프로젝트를 솔루션에 추가
1. **솔루션 탐색기**에서 솔루션 노드를 마우스 오른쪽 단추로 클릭하고 **추가 | 새 프로젝트**를 선택합니다. 
2. 왼쪽 창에서 **Visual C++ | 테스트**를 선택하고 가운데 창에서 **Google Test 프로젝트**를 선택합니다. 
3. 테스트 프로젝트에 이름을 지정하고 **확인**을 클릭합니다. 

![새 Google Test 프로젝트](media/cpp-gtest-new-project.png "새 Google Test 프로젝트 추가")

## <a name="configure-the-test-project"></a>테스트 프로젝트 구성
나타나는 **테스트 프로젝트 구성** 대화 상자에서 테스트할 프로젝트를 선택할 수 있습니다. 프로젝트를 선택하면 Visual Studio가 선택한 프로젝트에 대한 참조를 추가합니다. 프로젝트를 선택하지 않으면 테스트할 프로젝트에 참조를 수동으로 추가해야 합니다. Google Test 바이너리에 대한 정적 및 동적 링크를 선택할 때는 다른 C++ 프로그램과 동일한 사항을 고려합니다. 자세한 내용은 [Visual C++의 DLL](/cpp/build/dlls-in-visual-cpp)을 참조하세요. 

 ![Google Test 프로젝트 구성](media/cpp-gtest-config.png "Google Test 프로젝트 구성")

## <a name="set-additional-options"></a>추가 옵션 설정
주 메뉴에서 **도구 | 옵션 | Google Test용 테스트 어댑터**를 선택하여 추가 옵션을 설정합니다. 이러한 설정에 대한 자세한 내용은 Google Test 설명서를 참조하세요.

 ![Google Test 프로젝트 설정](media/cpp-gtest-settings.png "Google Test 프로젝트 설정")

## <a name="add-include-directives"></a>include 지시문 추가
.cpp 테스트 파일에서 필요한 `#include` 지시문을 추가하여 프로그램의 형식과 함수를 테스트 코드에 표시되게 합니다. 일반적으로 프로그램은 폴더 계층 구조에서 한 수준 위에 있습니다. `#include "../"`를 입력하면 IntelliSense 창이 표시되어 헤더 파일에 대한 전체 경로를 선택할 수 있습니다.

![#include 지시문 추가](media/cpp-gtest-includes.png "test .cpp파일에 include 지시문 추가")

## <a name="write-and-run-tests"></a>테스트 작성 및 테스트
이제 Google Test를 작성하고 실행할 준비가 되었습니다. 테스트 매크로에 대한 자세한 내용은 [Google Test 입문](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md)을 참조하세요. **테스트 탐색기**를 사용한 테스트 검색, 실행 및 그룹화에 대한 내용은 [테스트 탐색기를 사용하여 단위 테스트 실행](run-unit-tests-with-test-explorer.md)을 참조하세요.

## <a name="see-also"></a>참고 항목
[C/C++에 대한 단위 테스트 작성](writing-unit-tests-for-c-cpp.md)


  







