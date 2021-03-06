---
title: IDebugDocumentTextExternalAuthor::GetPathName | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugDocumentTextExternalAuthor.GetPathName
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentTextExternalAuthor::GetPathName
ms.assetid: 445152a1-9cf8-402e-93d6-3d4bf2b81d17
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 93e5c27422d6b348d8c961d1555bfce07183e9e4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenttextexternalauthorgetpathname"></a>IDebugDocumentTextExternalAuthor::GetPathName
문서의 전체 경로 파일 이름을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetPathName(  
   BSTR*  pbstrLongName,  
   BOOL*  pfIsOriginalFile  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrLongName`  
 [out] 전체 경로 파일 이름을 포함 하는 문자열입니다.  
  
 `pfIsOriginalFile`  
 [out] 경로 파일 이름을 참조 하는 경우를 나타내는 부울 원본 문서에 있습니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_FAIL`|소스 파일을 생성 또는 확인할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 문서의 전체 경로 파일 이름을 반환합니다.  
  
 경우 `pfIsOriginalFile` FALSE, 경로 및 파일 이름에는 `pbstrLongName` 새로 만든된 임시 파일을 참조 하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentTextExternalAuthor 인터페이스](../../winscript/reference/idebugdocumenttextexternalauthor-interface.md)