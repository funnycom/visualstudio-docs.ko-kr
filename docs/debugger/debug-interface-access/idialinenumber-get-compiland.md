---
title: 'Idialinenumber:: Get_compiland | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber::get_compiland method
ms.assetid: c476d0b8-c473-47eb-96f5-c4e8f577b1c9
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d4dd41975d65fe44f0fbe1f2ad361ceab71277b7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idialinenumbergetcompiland"></a>IDiaLineNumber::get_compiland
이미지 텍스트의 바이트를 관련 된 컴파일 대상에 대 한 기호에 대 한 참조를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_compiland (   
   IDiaSymbol** pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pRetVal  
 [out] 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 이미지 텍스트의 바이트를 관련 된 컴파일 대상에 대 한 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)