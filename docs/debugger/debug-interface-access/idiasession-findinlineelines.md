---
title: IDiaSession::findInlineeLines | Microsoft Docs
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
ms.assetid: b6822d8b-70d5-470b-8278-3aec4680326c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 83206c0c5f4aac76393e26c625c98bfbc28eb687
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasessionfindinlineelines"></a>IDiaSession::findInlineeLines
클라이언트가 모든 없는 함수를 인라인 처리, 직접 또는 간접적으로 지정 된 부모 기호는 줄 번호 정보를 반복 하는 데 사용 하는 열거형을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findInlineeLines (   
   IDiaSymbol*       parent,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `parent`  
 [in] `IDiaSymbol` 부모를 나타내는 개체입니다.  
  
 `ppResult`  
 [out] 보유 한 `IDiaEnumLineNumbers` 검색 되는 줄 번호의 목록을 포함 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)