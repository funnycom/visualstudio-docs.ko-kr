---
title: "분석 아키텍처 및 모델링 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-modeling
ms.topic: get-started-article
helpviewer_keywords:
- Visual Studio Ultimate, exploring code
- Visual Studio Ultimate, visualizing code
- diagrams - modeling
- Visual Studio ALM, modeling
- application, design
- architecture
- code visualization
- application design
- applications, architecture
- code exploration
- Visual Studio ALM, exploring code
- modeling
- application architecture
- application, modeling
- applications, modeling
- architecture [Visual Studio ALM], modeling
- application modeling
- Visual Studio Ultimate, modeling
- architecture [Visual Studio Ultimate], modeling
- application, architecture
- Visual Studio ALM, visualizing code
- applications, designing
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d1bcac24b0d0a5b14cbfbc082d8272ea846a1d54
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="analyze-and-model-your-architecture"></a>아키텍처 분석 및 모델링
응용 프로그램 모델링 도구를 디자인 및 모델링 앱 및 Visual Studio 아키텍처를 사용 하 여 아키텍처 요구를 충족 하는지 확인 합니다. 

* Visual Studio를 사용하여 코드의 구조, 동작 및 관계를 시각화하는 방식으로 기존 프로그램 코드를 더 쉽게 이해할 수 있습니다. 

* 팀 아키텍처 종속성을 유지 하는 것에 대 한 필요 하 게 교육 합니다.  
  
* 개발 프로세스의 일부로 응용 프로그램 수명 주기 전체에 걸쳐 다양한 상세 수준으로 모델을 만듭니다.

참조 [시나리오: 모델링 및 시각화를 사용 하 여 디자인 변경](../modeling/scenario-change-your-design-using-visualization-and-modeling.md)합니다.  
  
## <a name="to"></a>대상  
  
|||  
|-|-|  
|**코드 시각화**:<br /><br /> -코드 맵을 만들어서 코드의 구조와 관계 참조 하십시오. 어셈블리, 네임스페이스, 클래스, 메서드 간의 종속성을 시각화합니다.<br />-코드에서 클래스 다이어그램을 만들어서 클래스 구조 및 특정 프로젝트에 대 한 멤버 참조 하십시오.<br />-코드 유효성을 검사 하는 종속성 다이어그램을 만들어서 코드와 디자인 간에 충돌을 확인 합니다.|-   [코드 시각화](../modeling/visualize-code.md)<br />-   [작업 클래스 및 다른 형식 (클래스 디자이너)](../ide/working-with-classes-and-other-types-class-designer.md)<br />-   [동영상: Visual Studio 2015 코드 맵 사용 하 여 코드에서 디자인 이해](https://channel9.msdn.com/Events/Visual-Studio/Connect-event-2015/502)<br />-   [비디오: 실시간으로 아키텍처 종속성 유효성 검사](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4)|  
|**아키텍처 정의**:<br /><br /> -정의 및 종속성 다이어그램을 만들어서 코드 구성 요소 간의 종속성에 대 한 제약 조건을 적용 합니다.|-   [동영상: Visual Studio (Channel 9)와 함께 아키텍처 종속성 유효성 검사](https://channel9.msdn.com/Events/Connect/2016/170)|  
|**요구 사항 및 의도한 디자인을 사용하여 시스템의 유효성을 검사합니다.**<br /><br /> -의도 한 아키텍처를 설명 하는 종속성 다이어그램 코드 종속성의 유효성을 검사 하 고 디자인과 충돌할 수 있는 변경을 차단 합니다.|-   [동영상: Visual Studio (Channel 9)와 함께 아키텍처 종속성 유효성 검사](https://channel9.msdn.com/Events/Connect/2016/170)|  
|**Team Foundation 버전 제어를 사용하여 모델, 다이어그램 및 코드 맵 공유**:<br /><br /> -코드 맵, 프로젝트 및 입력 deoendency 다이어그램에 Team Foundation 버전 제어 이들을 공유할 수 있습니다.| |  
|**모델 및 다이어그램 사용자 지정**:<br /><br /> -고유한 도메인 특정 언어를 만듭니다.|-   [Visual Studio-도메인 특정 언어에 대 한 SDK 모델링](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)|  
|**T4 템플릿을 사용하여 텍스트 생성**:<br /><br /> -텍스트 기반 파일을 생성 하도록 텍스트 블록 및 제어 논리 템플릿 안에 사용 합니다.<br /> -Visual Studio에 포함 하는 MSBuild 포함 하는 T4 템플릿 작성|-   [코드 생성 및 T4 텍스트 템플릿](../modeling/code-generation-and-t4-text-templates.md)|

각 기능을 지원하는 Visual Studio 버전을 확인하려면 [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)을 참조하세요.  
  
## <a name="types-of-models-and-their-uses"></a>모델 형식 및 해당 용도  
  
|**모델 형식 및 일반적인 용도**|  
|-------------------------------------|  
|**코드 맵**<br /><br /> 코드 맵을 통해 코드의 구성과 관계를 확인할 수 있습니다.<br /><br /> 일반적인 용도:<br /><br /> -프로그램 코드를 검사 합니다. 업데이트 및 비용을 예측 하는 방법을 제안 된 변경의 구조 및 해당 종속성이 알 수 있도록 합니다.<br /><br /> 참조<br /><br /> -   [솔루션 전체의 종속성 매핑](../modeling/map-dependencies-across-your-solutions.md)<br />-   [코드 맵을 사용 하 여 응용 프로그램 디버그](../modeling/use-code-maps-to-debug-your-applications.md)<br />-   [코드 맵 분석기를 사용 하 여 잠재적 문제 찾기](../modeling/find-potential-problems-using-code-map-analyzers.md)|  
|**종속성 다이어그램**<br /><br /> 종속성 다이어그램 레이어 또는 명시적 종속 관계를 사용 하 여 블록의 집합으로 응용 프로그램의 구조를 정의할 수 있습니다. 코드의 종속성과 종속성 다이어그램에 설명 된 종속 간 충돌을 검색 하는 유효성 검사를 실행할 수 있습니다.<br /><br /> 일반적인 용도:<br /><br /> -수명 동안 여러 변경 내용을 통해 응용 프로그램의 구조를 안정화 합니다.<br />-코드 변경 내용 체크 인 하기 전에 의도 하지 않은 종속성 충돌을 검색 합니다.<br /><br /> 참조<br /><br /> -   [코드에서 종속성 다이어그램 만들기](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [종속성 다이어그램: 참조](../modeling/layer-diagrams-reference.md)<br />-   [종속성 다이어그램으로 코드 유효성 검사](../modeling/validate-code-with-layer-diagrams.md)|  
|**DSL(도메인 특정 언어)**<br /><br /> DSL은 특정 용도에 맞게 디자인하는 표기법입니다. Visual Studio에서는 일반적으로 그래픽으로 표시됩니다.<br /><br /> 일반적인 용도:<br /><br /> -생성 하거나 응용 프로그램 부분을 구성 합니다. 표기법 및 도구를 개발하려면 작업이 필요합니다. 결과는 UML 사용자 지정보다 도메인에 더 적합할 수 있습니다.<br />-대형 프로젝트에 대 한 또는 제품 라인 둘 이상의 프로젝트에서 사용 하 여 DSL 및 도구 개발에 대 한 투자 반환 되는 위치입니다.<br /><br /> 참조<br /><br /> -   [Visual Studio-도메인 특정 언어에 대 한 SDK 모델링](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)|  
  
## <a name="where-can-i-get-more-information"></a>추가 정보는 어디서 확인할 수 있나요?  
  
[Visual Studio 시각화 및 모델링 도구 포럼](http://go.microsoft.com/fwlink/?LinkId=184720)  
  
## <a name="see-also"></a>참고 항목  
 [새로운 기능](../modeling/what-s-new-for-design-in-visual-studio.md)   
 [DevOps 및 애플리케이션 수명 주기 관리](http://msdn.microsoft.com/Library/74a1f71d-7f23-4c71-8fd7-89ede614fab6)
