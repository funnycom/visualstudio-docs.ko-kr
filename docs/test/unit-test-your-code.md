---
title: "코드 단위 테스트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio, unit tests
- unit tests, verifying code with
- testing code, automated tests
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: bafabb6755a5d3c8cf8f2b60b67a9dc0d7af9792
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="unit-test-your-code"></a>코드 단위 테스트
개발자와 테스터는 단위 테스트를 통해 [!INCLUDE[csharp_current_short](../misc/includes/csharp_current_short_md.md)], [!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)] 및 [!INCLUDE[cpp_current_short](../misc/includes/cpp_current_short_md.md)] 프로젝트에서 클래스의 메서드에 있는 논리 오류를 빠르게 찾을 수 있습니다.  
  
 단위 테스트 도구는 다음과 같습니다.  
  
1.  **테스트 탐색기.** 테스트 탐색기에서는 단위 테스트를 실행하고 그 결과를 볼 수 있습니다. 테스트 탐색기에서는 타사 프레임워크를 비롯하여 탐색기용 어댑터가 있는 모든 단위 테스트 프레임워크를 사용할 수 있습니다.  
  
2.  **관리 코드용 Microsoft 단위 테스트 프레임워크.** 관리 코드용 Microsoft 단위 테스트 프레임워크는 Visual Studio와 함께 설치되며 .NET 코드 테스트용 프레임워크를 제공합니다.  
  
3.  **C++용 Microsoft 단위 테스트 프레임워크.** C++용 Microsoft 단위 테스트 프레임워크는 Visual Studio와 함께 설치되며 네이티브 코드 테스트용 프레임워크를 제공합니다.  Google Test, Boost.Test 및 CTest 프레임워크 역시 Visual Studio에 포함되어 있으며 타사 어댑터를 추가 테스트 프레임 워크에서 사용할 수 있습니다. 자세한 내용은 [C/C++에 대한 단위 테스트 작성](writing-unit-tests-for-c-cpp.md)을 참조하세요. 
  
4.  **코드 검사 도구.** 단위 테스트가 테스트 탐색기의 명령 하나에서 실행하는 제품 코드의 양을 결정할 수 있습니다.  
  
5.  **Microsoft Fakes 격리 프레임워크.** Microsoft Fakes 격리 프레임워크는 테스트 중인 코드에서 종속성을 만드는 프로덕션 및 시스템 코드에 대한 대체 클래스 및 메서드를 만들 수 있습니다. 함수에 대한 모조 위임을 구현하여 종속성 개체의 동작과 출력을 제어할 수 있습니다.  
  
 [IntelliTest](../test/generate-unit-tests-for-your-code-with-intellitest.md)를 사용하면 .NET 코드를 탐색하여 테스트 데이터 및 단위 테스트 도구 모음을 생성할 수도 있습니다. 코드의 모든 문에 대해 해당 문을 실행할 테스트 입력이 생성됩니다. 코드의 모든 조건부 분기에 대해 사례 분석이 수행됩니다.  
  
## <a name="key-tasks"></a>주요 작업  
 다음 항목은 단위 테스트를 이해하고 만드는 데 유용합니다.  
  
|작업|관련 항목|  
|-----------|-----------------------|  
|**빠른 시작 및 연습:** 다음 항목을 사용하여 코드 예제에서 Visual Studio의 단위 테스트에 대해 알아봅니다.|-   [연습: 관리 코드에 대한 단위 테스트 만들기 및 실행](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)<br />-   [빠른 시작: 테스트 탐색기를 사용한 테스트 기반 개발](../test/quick-start-test-driven-development-with-test-explorer.md)<br />-   [기존 C++ 응용 프로그램에 단위 테스트 추가](../test/unit-testing-existing-cpp-applications-with-test-explorer.md)|  
|**테스트 탐색기를 사용한 단위 테스트:** 테스트 탐색기를 통해 보다 다 생산적이고 효율적인 단위 테스트를 만드는 방법에 대해 알아봅니다.|-   [단위 테스트 기본 사항](../test/unit-test-basics.md)<br />-   [단위 테스트 프로젝트 만들기](../test/create-a-unit-test-project.md)<br />-   [테스트 탐색기를 사용하여 단위 테스트 실행](../test/run-unit-tests-with-test-explorer.md)<br />-   [타사 단위 테스트 프레임워크 설치](../test/install-third-party-unit-test-frameworks.md)<br />-   [Visual Studio 2010에서 코딩된 UI 테스트 업그레이드](../test/upgrading-coded-ui-tests-from-visual-studio-2010.md)|  
|**관리 코드 단위 테스트:**|-   [관리 코드용 Microsoft 단위 테스트 프레임워크를 사용하여 .NET Framework용 단위 테스트 작성](../test/writing-unit-tests-for-the-dotnet-framework-with-the-microsoft-unit-test-framework-for-managed-code.md)|  
|**C++ 코드 단위 테스트**|-   [C++용 Microsoft 단위 테스트 프레임워크를 사용하여 C/C++용 단위 테스트 작성](../test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp.md)|  
|**단위 테스트 격리**|-   [Microsoft Fakes를 사용하여 테스트 중인 코드 격리](../test/isolating-code-under-test-with-microsoft-fakes.md)|  
|**코드 검사를 사용하여 프로젝트의 코드 중 단위 테스트로 테스트되는 부분 식별:** [!INCLUDE[vsprvsts](../code-quality/includes/vsprvsts_md.md)]테스트 도구의 코드 검사 기능에 대해 알아보세요.|-   [코드 검사를 사용하여 테스트할 코드 범위 결정](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)|  
|**단위 테스트에 대한 부하 테스트를 사용하여 스트레스 및 성능 분석 수행:** 응용 프로그램에서 성능 및 스트레스 문제를 격리하기 위해 부하 테스트를 만들고 여기에 단위 테스트를 추가할 수 있습니다.|-   [부하 테스트(VSTS 및 TFS)](/vsts/load-test/)|  
|**품질 게이트 설정 및 적용:** 코드의 품질을 확인하기 위해 코드를 체크 인하기 전에 테스트가 실행되도록 품질 게이트를 만들 수 있습니다.|-   [품질 게이트 설정 및 적용](http://msdn.microsoft.com/Library/bdc5666e-6cf0-45b2-a0a1-133c3f61e852)|  
|**단위 테스트 형식 확장:** 단위 테스트 프레임워크에 없을 수도 있는 테스트에 기능을 추가할 수 있습니다. 예를 들어 테스트를 일반 사용자로 실행할지 여부를 지정하는 테스트 속성을 추가할 수 있습니다. 또는 프레임워크를 확장하여 메서드에 행 특성을 추가하고 테스트에서 이 행의 데이터를 사용할 수 있습니다.|단위 테스트 프레임워크를 확장하는 방법에 대한 예제 코드는 다음 [Microsoft 웹 사이트](http://go.microsoft.com/fwlink/?LinkId=185591)를 참조하세요.|  
|**테스트 옵션 설정:** 예를 들면 테스트 결과가 저장되는 위치를 지정할 수 있습니다.|[.runsettings 파일을 사용하여 단위 테스트 구성](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md)|  
  
## <a name="reference"></a>참조  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting>  
 유닛 테스트를 지원하는 특성, 예외, 어설션 및 기타 클래스를 제공하는 UnitTesting 네임스페이스에 대해 설명합니다.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Web>  
 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 및 웹 서비스 단위 테스트를 지원하여 UnitTesting 네임스페이스를 확장하는 UnitTesting.Web 네임스페이스에 대해 설명합니다.  
  
## <a name="external-resources"></a>외부 리소스  
  
### <a name="videos"></a>비디오  
 [채널 9: XAML을 사용하여 빌드한 UWP 앱 유닛 테스트](http://go.microsoft.com/fwlink/?LinkId=226285)  
  
### <a name="forums"></a>포럼  
 [Visual Studio 단위 테스트](http://go.microsoft.com/fwlink/?LinkId=224477)  
  
### <a name="guidance"></a>지침  
 [Visual Studio 2012를 사용한 지속적인 업데이트 테스트 - 2장: 유닛 테스트: 내부 테스트](http://go.microsoft.com/fwlink/?LinkID=255188)  
  
### <a name="reference"></a>참조  
 [단위 테스트에 대한 콘텐츠 인덱스](http://go.microsoft.com/fwlink/?LinkID=254719)  
  
## <a name="see-also"></a>참고 항목

[코드 품질 향상](/visualstudio/test/improve-code-quality)
