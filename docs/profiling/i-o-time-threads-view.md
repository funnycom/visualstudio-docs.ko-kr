---
title: "I/O 시간(스레드 뷰) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.io
helpviewer_keywords:
- Concurrency Visualizer, I/O time (Threads View)
ms.assetid: 0c4ec14d-d8dd-49c1-999c-dcbf4e8e1dc8
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: abea2c5ed246fe3463205894326a7f9611b56043
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="io-time-threads-view"></a>I/O 시간(스레드 뷰)
타임라인의 이러한 세그먼트는 I/O로 분류되는 차단 시간과 관련이 있습니다. 즉, 스레드는 I/O 작업이 끝나기를 대기하고 있습니다. 스레드는 API에서 차단되거나 동시성 시각화 도우미가 I/O로 계산하는 I/O 관련 커널 대기에 의해 차단되었을 수 있습니다. `CreateFile()`, `ReadFile()` 및 `WSARecv()` 등의 API는 이 그룹에 속합니다.  
  
## <a name="see-also"></a>참고 항목  
 [스레드 뷰](../profiling/threads-view-parallel-performance.md)