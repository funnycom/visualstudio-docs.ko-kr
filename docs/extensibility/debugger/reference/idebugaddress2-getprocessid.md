---
title: IDebugAddress2::GetProcessID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugAddress2::GetProcessID
helpviewer_keywords: IDebugAddress2::GetProcessID method
ms.assetid: 2c18889d-074a-4b95-87b4-bf1a067f44ed
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: bcc83bf3fd83a0c84fa73e11fc9c25f990bd769b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugaddress2getprocessid"></a>IDebugAddress2::GetProcessID
이 나타내는 개체를 소유 하는 프로세스의 ID를 검색 [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md) 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetProcessID (  
   DWORD* pProcID  
);  
```  
  
```csharp  
int GetProcessID (  
   out uint pProcID  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pProcID`  
 [out] 프로세스 id입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md)