---
title: "Visual Studio에서 유닛 테스트 실행 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- uwp
author: gewarren
ms.openlocfilehash: c06ad430664f1e6cd5010e4af5d8d28efa1f8d25
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="run-unit-tests-in-visual-studio"></a>Visual Studio에서 유닛 테스트 실행

이 항목에서는 Microsoft Visual Studio에서 테스트 탐색기를 사용하여 유닛 테스트를 실행하는 방법을 설명합니다.

##  <a name="BKMK_Unit_test_frameworks_and_test_projects"></a> 단위 테스트 프레임워크 및 테스트 프로젝트

Visual Studio에는 관리 코드 및 네이티브 C++ 코드에 대한 Microsoft 유닛 테스트 프레임워크가 있습니다. 테스트 탐색기는 솔루션의 여러 테스트 프로젝트 및 프로덕션 코드 프로젝트의 일부인 테스트 클래스에서 테스트를 실행할 수 있습니다. 테스트 프로젝트는 Visual C++ 또는 Visual C# 및 Visual Basic 단위 테스트 프레임워크의 조합일 수 있습니다. 테스트 중인 코드가 .NET Framework용으로 작성된 경우 테스트 프로젝트는 대상 코드의 언어에 관계없이 모든 .NET Framework 언어로 작성할 수 있습니다. 네이티브 C/C++ 코드 프로젝트는 C++ 단위 테스트 프레임워크를 사용하여 테스트해야 합니다.

##  <a name="BKMK_Running_tests_in_Test_Explorer"></a> 테스트 탐색기에서 테스트 실행  
 테스트 프로젝트를 빌드하면 테스트가 테스트 탐색기에 나타납니다. 테스트 탐색기가 표시되지 않는 경우 Visual Studio 메뉴에서 **테스트** 를 선택하고 **Windows**를 선택한 다음 **테스트 탐색기**를 선택합니다.  
  
 ![단위 테스트 탐색기](../test/media/ute_failedpassednotrunsummary.png "UTE_FailedPassedNotRunSummary")  
  
 테스트를 실행하고 작성하고 다시 실행하면 테스트 탐색기는 **실패한 테스트**, **통과한 테스트**, **건너뛴 테스트** 및 **실행하지 않은 테스트**의 기본 그룹에 결과를 표시합니다. 테스트 탐색기의 테스트 그룹화 방식을 변경할 수 있습니다.  
  
 테스트 탐색기 도구 모음에서 테스트를 찾고 구성하고 실행하는 작업 중 많은 부분을 수행할 수 있습니다.  
  
 ![테스트 탐색기 도구 모음에서 테스트 실행](../test/media/ute_toolbar.png "UTE_ToolBar")  
  
###  <a name="BKMK_Running_tests"></a> 테스트 실행  
 솔루션의 모든 테스트, 그룹의 모든 테스트 또는 선택한 테스트 집합을 실행할 수 있습니다. 다음 작업 중 하나를 수행합니다.  
  
-   솔루션의 모든 테스트를 실행하려면 **모두 실행**을 선택합니다.  
  
-   기본 그룹의 모든 테스트를 실행하려면 **실행...** 을 선택한 다음 메뉴에서 그룹을 선택합니다.  
  
-   실행할 개별 테스트를 선택하고 선택한 테스트에 대한 바로 가기 메뉴를 연 다음 **선택한 테스트 실행**을 선택합니다.  
  
 테스트가 실행되면 테스트 탐색기 창 위쪽의 통과/실패 표시줄에 애니메이션 효과가 적용됩니다. 테스트 실행이 끝날 때 통과/실패 표시줄은 모든 테스트가 통과했으면 녹색이 되고 실패한 테스트가 있으면 빨간색이 됩니다.  
  
##  <a name="BKMK_Viewing_test_results"></a> 테스트 결과 보기  
 테스트를 실행하고 작성하고 다시 실행하면 테스트 탐색기는 **실패한 테스트**, **통과한 테스트**, **건너뛴 테스트** 및 **실행하지 않은 테스트**의 그룹에 결과를 표시합니다. 테스트 탐색기 아래쪽의 세부 정보 창에 테스트 실행에 대한 요약이 표시됩니다.  
  
###  <a name="BKMK_Viewing_test_details"></a> 테스트 세부 정보 보기  
 개별 테스트의 정보를 보려면 해당 테스트를 선택합니다.  
  
 테스트 정보 창에는 다음 정보가 표시됩니다.  
  
-   테스트 메서드의 소스 파일 이름 및 줄 번호  
  
-   테스트의 상태입니다.  
  
-   테스트 메서드가 실행되는 데 걸린 시간  
  
 테스트가 실패할 경우 세부 정보 창에는 다음과 같은 정보도 표시됩니다.  
  
-   단위 테스트 프레임워크에서 테스트에 대해 반환된 메시지  
  
-   테스트 실패 시의 스택 추적  
  
###  <a name="BKMK_Viewing_the_source_code_of_a_test_method"></a> 테스트 메서드의 소스 코드 보기  
 Visual Studio 편집기에서 테스트 메서드의 소스 코드를 표시하려면 테스트를 선택한 다음 바로 가기 메뉴에서 **테스트 열기**(키보드: F12)를 선택합니다.  
  
##  <a name="BKMK_Organizing_the_test_list"></a> 테스트 목록 구성  
  
###  <a name="BKMK_Grouping_tests"></a> 테스트 그룹화  
 기본적으로 테스트 탐색기는 **실패한 테스트**, **통과한 테스트**, **건너뛴 테스트** 및 **실행하지 않은 테스트**의 자식 노드로 테스트를 표시합니다.  
  
|||  
|-|-|  
|![테스트 탐색기 그룹 단추](../test/media/ute_groupby_btn.png "UTE_GroupBy_btn")|테스트를 실행하는 데 걸리는 시간을 기준으로 테스트를 그룹화하려면 **그룹화 방법** 목록을 열고 **기간**을 선택합니다. **테스트 결과**를 선택하여 원래 그룹화로 전환합니다.|  
  
###  <a name="BKMK_Searching_and_filtering_the_test_list"></a> 테스트 목록 검색 및 필터링  
 테스트 수가 많은 경우 테스트 탐색기 검색 상자에 입력하여 지정된 문자열로 목록을 필터링할 수 있습니다. 검색 문자열을 입력하기 전에 필터 목록에서 선택하여 특정 형식의 문자열로 필터를 제한할 수 있습니다.  
  
 ![검색 필터 범주](../test/media/ute_searchfilter.png "UTE_SearchFilter")  
  
##  <a name="BKMK_Debugging_unit_tests"></a> 단위 테스트 디버그  
 테스트 탐색기를 사용하여 테스트에 대한 디버깅 세션을 시작할 수 있습니다. Visual Studio 디버거에서 코드를 단계별로 실행하면 단위 테스트 및 테스트 중인 프로젝트 간을 앞뒤로 매끄럽게 이동할 수 있습니다. 디버깅을 시작하려면  
  
1.  Visual Studio 편집기에서 디버그하려는 하나 이상의 테스트 메서드에서 중단점을 설정합니다.  
  
    > [!NOTE]
    > 테스트 메서드는 순서에 관계 없이 실행할 수 있기 때문에 디버그하려는 모든 테스트 메서드에 중단점을 설정합니다.  
  
2.  테스트 탐색기에서 테스트 메서드를 선택한 다음 바로 가기 메뉴에서 **선택한 테스트 디버그**를 선택합니다.  
  
 디버거에 대한 자세한 내용은 [Debugging in Visual Studio](../debugger/debugging-in-visual-studio.md)항목을 참조하세요.
