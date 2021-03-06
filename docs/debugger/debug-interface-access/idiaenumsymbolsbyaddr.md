---
title: IDiaEnumSymbolsByAddr | Microsoft Docs
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
- IDiaEnumSymbolsbyAddr interface
ms.assetid: 37d3dcdf-e4fa-4354-b5e1-8843566b52ac
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c76c61f79b0a76d923f92084a1e1ccdca82b60c4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idiaenumsymbolsbyaddr"></a>IDiaEnumSymbolsByAddr
데이터 원본에 포함 된 다양 한 기호 주소로 열거 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDiaEnumSymbolsByAddr : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDiaEnumSymbolsByAddr`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IDiaEnumSymbolsByAddr::symbolByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyaddr.md)|섹션 및 오프셋 조회를 수행 하 여 열거자를 놓습니다.|  
|[IDiaEnumSymbolsByAddr::symbolByRVA](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyrva.md)|상대 가상 주소 (RVA) 하 여 조회를 수행 하 여 열거자를 놓습니다.|  
|[IDiaEnumSymbolsByAddr::symbolByVA](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyva.md)|가상 주소 (VA) 하 여 조회를 수행 하 여 열거자를 놓습니다.|  
|[IDiaEnumSymbolsByAddr::Next](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-next.md)|주소로 순서 대로 다음 기호를 검색합니다. 인출 된 요소의 수를 열거자 위치를 업데이트 합니다.|  
|[IDiaEnumSymbolsByAddr::Prev](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-prev.md)|주소로 순서로 이전 기호를 검색합니다. 인출 된 요소의 수를 열거자 위치를 업데이트 합니다.|  
|[IDiaEnumSymbolsByAddr::Clone](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-clone.md)|개체의 복사본을 만듭니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 주소로 그룹화 된 기호를 제공 합니다. 예를 들어을 유형별로 그룹화 하는 기호를 사용 하려면 `SymTagUDT` (사용자 정의 형식) 또는 `SymTagBaseClass`를 사용 하 여는 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 가져올는 [idiasession:: Getsymbolsbyaddr](../../debugger/debug-interface-access/idiasession-getsymbolsbyaddr.md) 메서드.  
  
## <a name="example"></a>예  
 이 함수는 이름 및 상대 가상 주소로 정렬 하는 모든 기호는 주소를 표시 합니다.  
  
```C++  
void ShowSymbolsByAddress(IDiaSession *pSession)  
{  
    CComPtr<IDiaEnumSymbolsByAddr> pEnumByAddr;  
    if ( FAILED( psession->getSymbolsByAddr( &pEnumByAddr ) ) )  
    {  
        Fatal( "getSymbolsByAddr" );  
    }  
    CComPtr<IDiaSymbol> pSym;  
    if ( FAILED( pEnumByAddr->symbolByAddr( 1, 0, &pSym ) ) )  
    {  
        Fatal( "symbolByAddr" );  
    }  
    DWORD rvaLast = 0;  
    if ( pSym->get_relativeVirtualAddress( &rvaLast ) == S_OK )  
    {  
        pSym = 0;  
        if ( FAILED( pEnumByAddr->symbolByRVA( rvaLast, &pSym ) ) )  
        {  
            Fatal( "symbolByAddr" );  
        }  
        printf( "Symbols in order\n" );  
        do  
        {   
            CDiaBSTR name;  
            if ( pSym->get_name( &name ) != S_OK )  
            {  
                printf( "\t0x%08X (%ws) <no name>\n", rvaLast );  
            }  
            else  
            {  
               printf( "\t0x%08X %ws\n", rvaLast, name );  
            }  
            pSym = 0;  
            celt = 0;  
            if ( FAILED( hr = pEnumByAddr->Next( 1, &pSym, &celt ) ) )  
            {  
                break;  
            }  
        } while ( celt == 1 );  
    }  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스 (디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiasession:: Getsymbolsbyaddr](../../debugger/debug-interface-access/idiasession-getsymbolsbyaddr.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)