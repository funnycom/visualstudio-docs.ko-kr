---
title: IDebugBeforeSymbolSearchEvent2 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugBeforeSymbolSearchEvent2 interface
ms.assetid: 679fd7b1-765a-41a8-a046-63240c09a499
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d6ac247054a5048a7e2354f29415e203e03c7aaa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47542171"
---
# <a name="idebugbeforesymbolsearchevent2"></a>IDebugBeforeSymbolSearchEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugBeforeSymbolSearchEvent2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbeforesymbolsearchevent2)합니다.  
  
기호 로드 하는 동안 메시지 표시줄 (SDM) 상태를 설정 하려면 세션 디버그 관리자에 게이 인터페이스를 전송 하는 디버그 엔진 (DE).  
  
## <a name="syntax"></a>구문  
  
```  
IDebugBeforeSymbolSearchEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE 상태 표시줄 메시지 기호 로드 하는 동안 설정 해야 하는 경우이 인터페이스를 구현 합니다. 이 인터페이스를 사용 하거나 스크립트 인터프리터의 일부인 디버그 엔진에 의해서만 구현 됩니다. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 동일한 개체에서 인터페이스를 구현 해야 (SDM 사용 **QueryInterface** 액세스 하는 **IDebugEvent2** 인터페이스).  
  
## <a name="notes-for-callers"></a>호출자에 대 한 정보  
 DE을 만들어 상태 표시줄 메시지 기호 로드 하는 동안 설정 해야 하는 경우이 이벤트 개체를 보냅니다. 이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) SDM를 디버깅 중인 프로그램에 연결할 때 제공한 콜백 함수.  
  
## <a name="methods"></a>메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugBeforeSymbolSearchEvent2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetModuleName](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2-getmodulename.md)|현재 디버깅 중인 모듈의 이름을 검색 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll
