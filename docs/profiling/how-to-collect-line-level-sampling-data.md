---
title: "방법: 줄 수준 샘플링 데이터 수집 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance tools, line-level sampling
ms.assetid: 44803aad-dd39-4c2e-9209-d35185d44983
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 56115f2605cfc2c5f9dc1c4a42062208056b172c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-collect-line-level-sampling-data"></a>방법: 줄 수준 샘플링 데이터 수집
줄 수준 샘플링은 전용 샘플 수가 많은 함수와 같이 프로세서를 많이 사용하는 함수의 코드에서 프로세서가 대부분의 시간을 사용하는 위치를 확인하는 프로파일러 기능입니다.  
  
## <a name="overview"></a>개요  
 줄 수준 샘플링의 경우 프로파일러는 설정된 간격으로 프로그램 호출 스택을 처리하고 해당 결과를 집계합니다. 이러한 결과는 샘플이 사용될 때 프로세서에서 실행하고 있던 명령을 보여 줍니다. 그런 다음 전용 샘플에 대한 수집된 데이터를 분석하여 코드 줄과 IP(명령 포인터)를 확인합니다.  
  
 줄 수준 샘플링은 관리 코드 및 네이티브 코드에서 사용됩니다. 이 데이터를 표시하는 성능 보고서에는 줄 뷰 및 모듈 뷰가 포함됩니다.  
  
 문자 시작/끝 정보는 네이티브 코드에 사용할 수 없습니다. 여러 줄 문의 경우 줄 시작 정보는 네이티브 코드에 사용할 수 없고 줄 끝 정보만 사용할 수 있습니다.  
  
### <a name="available-data"></a>사용 가능한 데이터  
 사용 가능한 줄 수준 샘플링 데이터에는 다음 정보가 포함됩니다.  
  
-   함수 이름.  
  
-   함수 주소.  
  
-   줄 시작 - 샘플링된 코드의 줄 번호.  
  
-   줄 끝 – 소스 줄 끝 번호. 단일 프로그램 문이 여러 소스 코드 줄에 걸쳐 있는 경우를 제외하고 이는 일반적으로 "줄 시작" 데이터와 동일합니다.  
  
-   문자 시작 – 집계 샘플의 시작 열. 단일 줄에 여러 프로그램 문이 포함된 경우를 제외하고 이는 일반적으로 0입니다.  
  
-   문자 끝 – 집계 샘플의 끝 열.  
  
-   IP – 집계 샘플이 사용된 주소(IP 뷰 전용).  
  
 **모듈** 뷰에서 함수에 줄 수준 통계가 있으면 통계가 각 함수 아래에 중첩됩니다. 또한 각 줄 아래에 중첩된 IP 수준 통계가 제공됩니다.  
  
### <a name="turn-off-line-level-sampling-for-managed-code"></a>관리 코드의 줄 수준 샘플링 끄기  
 줄 수준 샘플링은 기본적으로 켜집니다. 다음 중 하나를 수행하여 관리 코드의 줄 수준 데이터 수집을 끌 수 있습니다.  
  
-   프로파일링하기 전에 **VSPerfCLREnv /samplelineoff**를 입력합니다. 이는 응용 프로그램 및 서비스에 모두 영향을 미칩니다.  
  
     — 또는 —  
  
-   응용 프로그램을 시작할 때 **VSPerfCmd /lineoff \<기타 인수>**를 입력합니다.  
  
## <a name="see-also"></a>참고 항목  
 [성능 세션 구성](../profiling/configuring-performance-sessions.md)   
 [성능 도구 데이터 분석](../profiling/analyzing-performance-tools-data.md)