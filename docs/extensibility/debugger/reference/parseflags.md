---
title: PARSEFLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PARSEFLAGS
helpviewer_keywords: PARSEFLAGS enumeration
ms.assetid: 47943f0a-54cb-4493-a62e-5dba97bd4c35
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ae1237efe578bdd51c6ed148a1dab7a7617fee30
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="parseflags"></a>PARSEFLAGS
식의 구문을 분석 하는 방법을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_PARSEFLAGS {   
   PARSE_EXPRESSION            = 0x0001,  
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,  
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000  
};  
typedef DWORD PARSEFLAGS;  
```  
  
```csharp  
public enum enum_PARSEFLAGS {   
   PARSE_EXPRESSION            = 0x0001,  
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,  
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000  
};  
```  
  
## <a name="members"></a>멤버  
 PARSE_EXPRESSION  
 식 문 임을 나타냅니다.  
  
 PARSE_FUNCTION_AS_ADDRESS  
 식을 구문 분석 (하 고 나중에 평가) 주소로 임을 나타냅니다.  
  
 PARSE_DESIGN_TIME_EXPR_EVAL  
 식이 디자인 타임 동안 구문 분석 되는 나타냅니다 (즉, 디자이너를 열 때).  
  
## <a name="remarks"></a>설명  
 에 대 한 매개 변수로 전달 되는 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 및 [구문 분석](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)   
 [구문 분석](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)