---
title: "중단점 적중 횟수 대화 상자를가 하는 경우 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.whenbreakpointishit
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
ms.assetid: 476e3d98-cf35-4338-b124-cd0f3010d854
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c03e68315c8c0818d6b9cf6a102adde4ea4f8a10
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/04/2018
---
# <a name="when-breakpoint-is-hit-dialog-box"></a>중단점이 적중될 때 대화 상자
이 대화 상자는 중단점이 적중 될 때 발생 하는 동작을 사용자 지정할 수 있습니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **메시지를 인쇄 합니다.**  
 DebuggerDisplay 구문을 사용 하 여 메시지를 인쇄 합니다. 자세한 내용은 참조 [DebuggerDisplay 특성을 사용 하 여](../debugger/using-the-debuggerdisplay-attribute.md)합니다.  
  
 또한이 텍스트 상자 (예: $ADDRESS) 단독으로 또는 DebuggerDisplay 식의 중괄호 내에서 사용할 수 있는 특수 키워드를 지원 합니다. 사용할 수 있는 키워드는 대화 상자에 나열 됩니다.  
  
 **계속 실행**  
 이 컨트롤을 사용할 경우에만 **메시지를 출력** 을 선택 합니다. 이 컨트롤을 선택 하면 프로그램 실행을 추적 하는 추적점으로 중단점을 사용할 수 있습니다 위치 적중 될 때 중단 하는 대신 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [중단점 사용](../debugger/using-breakpoints.md)   
 [DebuggerDisplay 특성 사용](../debugger/using-the-debuggerdisplay-attribute.md)