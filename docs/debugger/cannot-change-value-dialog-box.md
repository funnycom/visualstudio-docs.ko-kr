---
title: "변경할 수 없음 대화 상자 값 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.variables.failededit
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Cannot Change Value dialog box
- variables [debugger], editing
ms.assetid: 19e930c2-5fbf-4c83-aae8-a1dc3f8fcae8
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7a6b5cc2c1a5317009225d8e86fd497dc4367787
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/04/2018
---
# <a name="cannot-change-value-dialog-box"></a>값을 변경할 수 없음 대화 상자
## <a name="error"></a>Error  
 `The value of this variable cannot be changed`&#124; `The name` *이름* `does not exist in the current context` &#124; *다른 다양 한 메시지*  
  
 이 메시지 상자는 디버거 창(자동, 조사식 또는 지역 창)이나 간략한 조사식 대화 상자에서 변수의 내용을 잘못된 값으로 변경하려고 할 때 나타납니다. 예를 들어 정수 변수의 값을 문자열로 설정하려고 하면 이 메시지 상자가 나타납니다.  
  
## <a name="solution"></a>솔루션  
 디버거 창이나 간략한 조사식 대화 상자에 입력한 값이 설정하려는 변수에 적합한 값인지 확인하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [디버거의 식](../debugger/expressions-in-the-debugger.md)