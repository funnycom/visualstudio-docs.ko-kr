---
title: IEnumDebugObjects::GetCount | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugObjects::GetCount
helpviewer_keywords: IEnumDebugObjects::GetCount method
ms.assetid: 9cbc5db4-03ae-479f-a664-13cad66ad210
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: eea93b33e82023f811e40ae706b87658dfebe6ae
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugobjectsgetcount"></a>IEnumDebugObjects::GetCount
이 메서드는 열거의 요소 수를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCount(  
   [out] ULONG* pcelt  
);  
```  
  
```csharp  
int GetCount(  
   out uint pcelt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pcelt`  
 [out] 열거의 요소 수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 구현 해야 다음, 복제, Skip 및 재설정 필요를 지정 하는 일반적인 COM 열거형 인터페이스의 일부가 아닙니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)