---
title: "방법: 시작할 이진 파일 지정 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.property.itemlaunch
helpviewer_keywords:
- profiling tools, launching
- performance tools, launching
- performance sessions, launching
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 94dbedfaa008b83ac45cea9afaa6bac2a254e77e
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2018
---
# <a name="how-to-specify-the-binary-to-start"></a>방법: 시작할 이진 파일 지정

DLL 같은 이진 파일을 프로파일링하려면 **\<Target> 속성 페이지** 대화 상자에 정보를 입력해야 합니다. 이 정보는 DLL 프로젝트가 호출 응용 프로그램을 찾을 수 있는 위치를 나타냅니다.

1. **성능 탐색기**에서 대상 이진 파일을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.

2. **속성 페이지** 대화 상자에서 **시작** 속성을 클릭합니다.

3. **프로젝트 속성 재정의** 확인란을 선택합니다.

4. **시작할 실행 파일** 텍스트 상자에 파일 위치를 지정합니다.

5. **인수** 텍스트 상자에 응용 프로그램 시작에 필요한 인수를 지정합니다.

6. **작업 디렉터리** 텍스트 상자에 디렉터리 위치를 지정합니다.

7. **확인**을 클릭합니다.

## <a name="see-also"></a>참고 항목

[성능 세션 구성](../profiling/configuring-performance-sessions.md)