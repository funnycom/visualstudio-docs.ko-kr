---
title: IDiaSession::findInlineeLinesByLinenum | Microsoft Docs
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
ms.assetid: cf32ae7c-a0c8-4800-bc8f-d64fdd15fb06
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4a47197653b8bcbe81ff961e3b82f7578b104e0b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idiasessionfindinlineelinesbylinenum"></a>IDiaSession::findInlineeLinesByLinenum
클라이언트가 없는 인라인 직접 또는 간접적으로 지정 된 소스 파일과 줄 번호에 모든 함수의 줄 번호 정보를 반복 하는 데 사용 하는 열거형을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findInlineeLinesByVA (   
   IDiaSymbol*           compiland,  
   IDiaSourceFile*       file,  
   DWORD                 linenum,  
   DWORD                 column,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `compiland`  
 [in] [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 줄 번호에 대 한 검색 하려는 compiland를 나타내는 개체입니다. 이 매개 변수 여야 `NULL`합니다.  
  
 `file`  
 [in] [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) 검색 하려는 소스 파일을 나타내는 개체입니다. 이 매개 변수 여야 `NULL`합니다.  
  
 `linenum`  
 [in] 1부터 시작 줄 번호를 지정합니다.  
  
> [!NOTE]
>  모든 선을 지정 하려면 0을 사용할 수 없습니다 (사용 하 여는 [idiasession:: Findlines](../../debugger/debug-interface-access/idiasession-findlines.md) 을 모든 줄을 찾는 방법).  
  
 `column`  
 [in] 열 번호를 지정합니다. 모든 열을 지정 하려면 0을 사용 합니다. 열이 줄에 대 한 바이트 오프셋입니다.  
  
 `ppResult`  
 [out] 반환 된 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) 검색 된 줄 번호의 목록을 포함 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)