---
title: IDebugProcess3::GetHostingProcessLanguage | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcess3::GetHostingProcessLanguage
helpviewer_keywords: IDebugProcess3::GetHostingProcessLanguage
ms.assetid: 52fca002-a9ef-43b1-9192-afbe7bb59ad4
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2fb22658c83cbdd33e9a2998e0f485dc38fda388
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprocess3gethostingprocesslanguage"></a>IDebugProcess3::GetHostingProcessLanguage
이 메서드는 반환 된 `GUID` 집합으로 호출 하 여이 프로세스의 언어를 나타내는 [SetHostingProcessLanguage](../../../extensibility/debugger/reference/idebugprocess3-sethostingprocesslanguage.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetHostingProcessLanguage(  
   GUID* pguidLang  
);  
```  
  
```csharp  
int GetHostingProcessLanguage(  
   out Guid pguidLang  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pguidLang`  
 [out] `GUID` 이 프로세스의 언어입니다. `GUID_NULL`(C + +) 또는 `Guid.Empty` (C#) 언어 설정 되어 있지 않음을 의미 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [SetHostingProcessLanguage](../../../extensibility/debugger/reference/idebugprocess3-sethostingprocesslanguage.md)