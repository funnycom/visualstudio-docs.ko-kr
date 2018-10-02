---
title: IDebugReference2::EnumChildren | Microsoft Docs
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
- IDebugReference2::EnumChildren
helpviewer_keywords:
- IDebugReference2::EnumChildren
ms.assetid: 35b3c2f3-69f4-4013-b555-f847221f62e8
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 760bad3e67d4ac2100dc0bfa68d319aae18a617d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47542172"
---
# <a name="idebugreference2enumchildren"></a>IDebugReference2::EnumChildren
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugReference2::EnumChildren](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugreference2-enumchildren)합니다.  
  
선택한 자식 참조의 목록을 가져옵니다. 나중에 사용하기 위해 예약되어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT EnumChildren (   
   DEBUGREF_INFO_FLAGS        dwFields,  
   DWORD                      dwRadix,  
   DBG_ATTRIB_FLAGS           dwAttribFilter,  
   LPCOLESTR                  pszNameFilter,  
   DWORD                      dwTimeout,  
   IEnumDebugReferenceInfo2** ppEnum  
);  
```  
  
```csharp  
int EnumChildren (   
   enum_DEBUGREF_INFO_FLAGS     dwFields,  
   uint                         dwRadix,  
   enum_DBG_ATTRIB_FLAGS        dwAttribFilter,  
   string                       pszNameFilter,  
   uint                         dwTimeout,  
   out IEnumDebugReferenceInfo2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwFields`  
 [in] 플래그의 조합을 합니다 [DEBUGREF_INFO_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md) 열거형의 열거 된 필드를 지정 하는 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) 채울 구조체가 합니다.  
  
 `dwRadix`  
 [in] 모든 숫자 정보를 서식 지정 하는 데 사용할 기 수입니다.  
  
 `dwAttribFilter`  
 [in] 플래그의 조합을 [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) 함께에서 필터로 사용 되는 열거형을 `pszNameFilter` 매개 변수를 열거할 수 있는 구조는 합니다.  
  
 `pszNameFilter`  
 [in] "MyX"을 함께 사용 하는 등 필터를 지정 하는 문자열을 `dwAttribFilter` 매개 변수를 열거할 구조를 선택 합니다.  
  
 `dwTimeout`  
 [in] 이 메서드에서 반환 되기 전에 대기할 밀리초에서는 최대 시간입니다. 사용 하 여 `INFINITE` 무기한 대기 합니다.  
  
 `ppEnum`  
 [out] 반환 된 [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md) 요청 된 자식 속성의 목록을 포함 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 항상 `E_NOTIMPL`를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [DEBUGREF_INFO_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md)   
 [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)   
 [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md)
