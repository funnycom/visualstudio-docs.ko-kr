---
title: Visual Studio에서 부하 테스트의 페이지 응답 시간 | Microsoft Docs
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, response times
- response times in load tests
- load test results, response times
ms.assetid: e61c49f3-3161-45b1-9220-08b5459065a2
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 055bb9b9ae369cd6b62741f7d23295c34b7d1d32
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-view-web-page-response-time-in-a-load-test-using-the-load-test-analyzer"></a>방법: 부하 테스트 분석기를 사용하여 부하 테스트의 웹 페이지 응답 시간 보기

각 웹 페이지가 로드되는 시간을 *응답 시간*이라고 합니다. 웹 성능 테스트를 만들 때 웹 성능 테스트의 각 웹 페이지 요청에 대한 응답 시간 목표를 설정할 수 있습니다.

부하 테스트의 스트레스 환경에서 웹 성능 테스트를 실행하면 각 페이지에서 다음과 같은 정보를 분석할 수 있습니다.

-   페이지의 평균 응답 시간

-   테스트 반복 중 페이지의 응답 시간 목표를 달성한 백분율

-   부하 테스트 분석기의 테이블 뷰 또는 그래프 뷰를 사용하여 웹 페이지 응답 시간을 분석할 수 있습니다.

-   테이블 뷰의 웹 페이지 응답 시간 분석

-   그래프 뷰의 웹 페이지 응답 시간 분석

## <a name="view-response-time-data-in-a-table"></a>테이블의 응답 시간 데이터 보기

### <a name="to-view-response-time-data-in-a-table"></a>응답 시간 데이터를 표로 보려면

1.  부하 테스트 분석기에서 도구 모음의 **테이블**을 선택하여 테이블 눈금이 표시되어 있는지 확인합니다.

2.  **테이블** 드롭다운 목록 상자에서 **페이지**를 선택합니다.

3.  각 페이지에 대한 데이터가 표로 표시됩니다. 다음 열이 일반적으로 표시됩니다.

    |||
    |-|-|
    |**페이지**|웹 페이지의 이름입니다.|
    |**시나리오**|시나리오 이름입니다. 웹 성능 테스트에 시나리오가 둘 이상인 경우 이 정보가 중요합니다.|
    |**테스트**|웹 성능 테스트의 이름입니다. 부하 테스트에 웹 성능 테스트가 둘 이상인 경우 이 정보가 중요합니다.|
    |**Network**|네트워크 형식입니다.<br /><br /> 기본적으로 이 데이터는 수집되지 않습니다. 이 데이터를 수집하려면 **부하 테스트 편집기**의 **실행 설정** 노드 아래에서 변경할 실행 설정 노드를 선택합니다. **속성** 창에서 **타이밍 정보 저장소** 속성으로 **AllIndividualDetails**를 선택합니다.|
    |**합계**|웹 페이지에 대한 요청의 총 개수입니다. 이는 부하 테스트의 모든 반복에 대한 합계입니다.|
    |**평균**|페이지의 평균 응답 시간입니다.<br /><br /> 기본적으로 이 데이터는 수집되지 않습니다. 이 데이터를 수집하려면 **부하 테스트 편집기**의 **실행 설정** 노드 아래에서 변경할 실행 설정 노드를 선택합니다. **속성** 창에서 **타이밍 정보 저장소** 속성으로 **AllIndividualDetails**를 선택합니다.|
    |**Min**|페이지의 최소 응답 시간입니다.<br /><br /> 기본적으로 이 데이터는 수집되지 않습니다. 이 데이터를 수집하려면 **부하 테스트 편집기**의 **실행 설정** 노드 아래에서 변경할 실행 설정 노드를 선택합니다. **속성** 창에서 **타이밍 정보 저장소** 속성으로 **AllIndividualDetails**를 선택합니다.|
    |**중앙값**|페이지 응답 시간의 중앙값입니다.<br /><br /> 기본적으로 이 데이터는 수집되지 않습니다. 이 데이터를 수집하려면 **부하 테스트 편집기**의 **실행 설정** 노드 아래에서 변경할 실행 설정 노드를 선택합니다. **속성** 창에서 **타이밍 정보 저장소** 속성으로 **AllIndividualDetails**를 선택합니다.|
    |**90%**|응답 시간의 90번째 백분위수입니다. 이 값은 페이지 중 90%는 이 시간보다 빨리 응답했고 10%는 늦게 응답했음을 나타냅니다.<br /><br /> 기본적으로 이 데이터는 수집되지 않습니다. 이 데이터를 수집하려면 **부하 테스트 편집기**의 **실행 설정** 노드 아래에서 변경할 실행 설정 노드를 선택합니다. **속성** 창에서 **타이밍 정보 저장소** 속성으로 **AllIndividualDetails**를 선택합니다.|
    |**95%**|응답 시간의 95번째 백분위수입니다. 이 값은 페이지 중 95%는 이 시간보다 빨리 응답했고 5%는 늦게 응답했음을 나타냅니다.|
    |**99%**|응답 시간의 99번째 백분위수입니다. 이 값은 페이지 중 99%는 이 시간보다 빨리 응답했고 1%는 늦게 응답했음을 나타냅니다.<br /><br /> 기본적으로 이 데이터는 수집되지 않습니다. 이 데이터를 수집하려면 **부하 테스트 편집기**의 **실행 설정** 노드 아래에서 변경할 실행 설정 노드를 선택합니다. **속성** 창에서 **타이밍 정보 저장소** 속성으로 **AllIndividualDetails**를 선택합니다.|
    |**Max**|페이지의 최대 응답 시간입니다.<br /><br /> 기본적으로 이 데이터는 수집되지 않습니다. 이 데이터를 수집하려면 **부하 테스트 편집기**의 **실행 설정** 노드 아래에서 변경할 실행 설정 노드를 선택합니다. **속성** 창에서 **타이밍 정보 저장소** 속성으로 **AllIndividualDetails**를 선택합니다.|
    |**표준 편차**|기본적으로 표준 편차 데이터는 수집되지 않습니다. 이 데이터를 수집하려면 **부하 테스트 편집기**의 **실행 설정** 노드 아래에서 변경할 실행 설정 노드를 선택합니다. **속성** 창에서 **타이밍 정보 저장소** 속성으로 **AllIndividualDetails**를 선택합니다.|
    |**페이지 시간**|웹 페이지에 대한 모든 요청의 평균 응답 시간입니다.|
    |**목표**|페이지 시간 목표입니다. 이는 페이지의 상수 값입니다. **참고:** 페이지 시간 목표는 웹 성능 테스트에서 요청에 목표가 정의된 경우에만 표시됩니다.|
    |**목표 만족 %**|웹 페이지에 대한 요청 중 응답 시간 목표를 충족한 백분율입니다.|

 자세한 내용은 [테이블 뷰에서 부하 테스트 결과 및 오류 분석](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)을 참조하세요.

## <a name="view-response-time-data-in-a-graph"></a>그래프에서 응답 시간 데이터 보기

응답 시간 데이터를 그래프로 표시하여 부하 테스트 도중 시간에 따라 값이 변화하는 모양을 확인할 수 있습니다. 이 방법은 단계 부하 패턴을 사용하는 경우와 같이 테스트 실행 도중 부하 패턴이 증가하는 경우에 특히 유용합니다. 자세한 내용은 [부하 패턴을 편집하여 가상 사용자 동작 모델링](../test/edit-load-patterns-to-model-virtual-user-activities.md)을 참조하세요.

### <a name="to-view-response-time-data-in-a-graph"></a>응답 시간 데이터를 그래프로 보려면

1.  부하 테스트 분석기의 도구 모음에서 **그래프**를 선택하여 그래프를 표시합니다.

2.  **카운터** 창에서 관심 있는 시나리오의 노드(예: `Scenario1`)를 확장합니다.

3.  관심 있는 웹 성능 테스트의 노드를 확장합니다.

4.  **페이지** 노드를 확장합니다.

5.  관심 있는 페이지의 노드를 확장합니다.

6.  **% Pages Meeting Goal**을 마우스 오른쪽 단추로 클릭한 다음, **그래프에 카운터 표시**를 선택합니다.

     그래프에 데이터가 추가됩니다.

7.  (선택 사항) Avg. Page Time, Page Response Time Goal 및 Total Pages에 대해 위의 단계를 반복합니다.

    > [!NOTE]
    > Page Response Time Goal은 상수입니다.

 자세한 내용은 [그래프 뷰에서 부하 테스트 결과 분석](../test/analyze-load-test-results-in-the-graphs-view.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [테이블 뷰에서 부하 테스트 결과 및 오류 분석](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)
- [방법: 분석을 위한 부하 테스트 결과 액세스](../test/how-to-access-load-test-results-for-analysis.md)
- [부하 테스트 결과 분석](../test/analyze-load-test-results-using-the-load-test-analyzer.md)