---
title: IDebugPort2::GetPortId | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPort2::GetPortId
helpviewer_keywords: IDebugPort2::GetPortId
ms.assetid: 837cb924-c113-4224-aa86-3e02b33dfa70
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 75f4d952ac1f4f9a3350eba973c5fac7d557f50b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugport2getportid"></a>IDebugPort2::GetPortId
포트 식별자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetPortId(   
   GUID* pguidPort  
);  
```  
  
```csharp  
int GetPortId(   
   out Guid pguidPort  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pguidPort`  
 [out] 포트를 식별 하는 GUID를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)