---
title: "호출 트리 뷰 - 경합 데이터 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Call Tree view
ms.assetid: 9bd4bde2-2ca3-446c-9ccc-7421522e03ae
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c829f11efd5eddda0ea819422856cb2bcc30c2ed
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="call-tree-view---contention-data"></a>호출 트리 뷰 - 경합 데이터
호출 트리 뷰에는 프로파일링 된 응용 프로그램에서 이동한 함수 실행 경로가 표시됩니다. 트리의 루트는 응용 프로그램 또는 구성 요소에 대한 진입점입니다. 각 함수 노드는 호출한 모든 함수, 다른 스레드 또는 프로세스와 리소스에 대해 경합하기 때문에 함수가 차단된 횟수 및 함수가 차단된 시간을 나열합니다.  
  
 호출 트리 뷰의 값은 호출 트리의 부모 함수가 호출한 함수 인스턴스에 대한 값입니다. 비율 값은 프로파일링 실행 시 총 경합 수와 함수 인스턴스 값을 비교하여 계산됩니다.  
  
## <a name="highlighting-the-execution-hot-path"></a>실행 부하 과다 경로 강조 표시  
 호출 트리 뷰에서는 가장 많은 경합을 만든 프로세스 또는 함수의 실행 경로를 확장하고 강조 표시할 수 있습니다.  
  
-   최대 활성 경로를 표시하려면 프로세스 또는 함수를 마우스 오른쪽 단추로 클릭한 후 **실행 부하 과다 경로 확장**을 클릭합니다.  
  
## <a name="setting-the-call-tree-root-node"></a>호출 트리 루트 노드 설정  
 프로파일링 실행 시 각 프로세스는 루트 노드로 표시됩니다. 호출 트리 뷰의 시작 노드를 설정하려면 시작 노드로 설정하려는 노드를 마우스 오른쪽 단추로 클릭하고 **루트 설정**을 클릭합니다.  
  
 루트 노드를 설정하면 선택한 노드의 하위 트리를 제외한 다른 모든 항목이 뷰에서 제거됩니다. 루트 노드를 원래 노드로 다시 설정하려면 호출 트리 뷰를 마우스 오른쪽 단추로 클릭하고 **루트 다시 설정**을 클릭합니다.  
  
|열|설명|  
|------------|-----------------|  
|**차단된 전용 시간**|프로파일링 실행 시 이 실행 경로에서 이 함수 인스턴스의 실행이 차단된 시간입니다. 이 시간에 함수가 호출한 자식 함수에서 차단된 시간은 포함되지 않습니다.|  
|**차단된 전용 시간 비율(%)**|프로파일링 실행의 모든 차단된 시간 중 이 실행 경로에서 이러한 함수에 대해 차단된 전용 시간의 백분율입니다.|  
|**전용 경합**|이 실행 경로의 이 함수 인스턴스에서 발생한 경합 수입니다. 이 경합 수에 함수에 의해 호출된 자식 함수의 경합은 포함되지 않습니다.|  
|**전용 경합 비율(%)**|호출 트리의 부모 함수가 호출한 이 함수 인스턴스의 전용 경합이었던 모든 경합의 비율입니다(프로파일링 실행 시).|  
|**함수 주소**|함수의 주소입니다.|  
|**함수 이름**|함수의 정규화된 이름입니다.|  
|**차단된 포괄 시간**|프로파일링 실행 시 이 실행 경로에서 이 함수 인스턴스의 실행이 차단된 총 시간입니다. 이 시간에 함수가 호출한 자식 함수의 차단된 시간이 포함됩니다.|  
|**차단된 포괄 시간 비율(%)**|프로파일링 실행의 모든 차단된 시간 중 이 실행 경로에서 이 함수 인스턴스에 대해 차단된 포괄 시간 백분율입니다.|  
|**포괄 경합**|이 실행 경로의 이 함수 인스턴스를 차단한 총 경합 수입니다. 이 경합 수에 함수에 의해 호출된 자식 함수의 경합이 포함됩니다.|  
|**포괄 경합 비율(%)**|프로파일링 실행의 경합 중 이 실행 경로에서 이 함수 인스턴스의 포괄 경합이었던 모든 경합의 백분율입니다.|  
|**수준**|호출 트리에서 함수의 수준입니다. VSReport 명령줄 보고서에서만 사용됩니다. 자세한 내용은 [VSPerfReport](../profiling/vsperfreport.md)를 참조하세요.|  
|**함수 줄 번호**|소스 파일에서 이 함수가 시작되는 줄 번호입니다.|  
|**모듈 이름**|함수가 포함된 모듈의 이름입니다.|  
|**모듈 경로**|함수가 포함된 모듈의 경로입니다.|  
|**프로세스 ID**|프로파일링 실행의 PID(프로세스 ID)입니다.|  
|**프로세스 이름**|프로세스의 이름입니다.|  
|**소스 파일**|이 함수의 정의가 포함된 소스 파일입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [방법: 보고서 뷰 열 사용자 지정](../profiling/how-to-customize-report-view-columns.md)   
 [호출 트리 뷰](../profiling/call-tree-view.md)   
 [호출 트리 뷰 - 계측](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)   
 [호출 트리 뷰 - 샘플링](../profiling/call-tree-view-dotnet-memory-sampling-data.md)   
 [호출 트리 뷰](../profiling/call-tree-view-instrumentation-data.md)   
 [호출 트리 뷰](../profiling/call-tree-view-sampling-data.md)