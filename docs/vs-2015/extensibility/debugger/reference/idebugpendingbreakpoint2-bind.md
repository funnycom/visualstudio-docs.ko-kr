---
title: IDebugPendingBreakpoint2::Bind | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPendingBreakpoint2::Bind
helpviewer_keywords:
- Bind method
- IDebugPendingBreakpoint2::Bind method
ms.assetid: 46e3f307-219d-40cd-a929-d41399c60ecf
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cd8ab4846796e872cc7de97e82efa719405d99c4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554467"
---
# <a name="idebugpendingbreakpoint2bind"></a>IDebugPendingBreakpoint2::Bind
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugPendingBreakpoint2::Bind](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugpendingbreakpoint2-bind)합니다.  
  
하나 이상의 코드 위치로이 보류 중인 중단점에 바인딩합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT Bind(   
   void   
);  
```  
  
```csharp  
int Bind();  
```  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다. 반환 `E_BP_DELETED` 중단점 삭제 된 경우.  
  
## <a name="remarks"></a>설명  
 이 메서드를 호출 하는 경우 디버그 엔진 (DE)와 일치 하는 모든 코드 위치에이 보류 중인 중단점을 바인딩하지 하려고 해야 합니다.  
  
 호출자를 호출 하는 나타내거나 보류 중인 중단점에 바인딩된 가정 하기 전에 오류가 발생 하는 이벤트를 대기 해야이 메서드에서 반환 된 후의 [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md) 또는 [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)메서드와 모든 바인딩 또는 오류 중단점을 각각 열거 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)   
 [IDebugBreakpointErrorEvent2](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)   
 [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)   
 [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)
