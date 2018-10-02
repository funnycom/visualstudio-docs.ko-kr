---
title: 'Idiasession:: Findchildren | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findChildren method
ms.assetid: 5d19046f-f668-4aa9-8788-95cda9a98997
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 97fed0f8ce7ff0712054b2aa3408217efe39f706
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47542153"
---
# <a name="idiasessionfindchildren"></a>IDiaSession::findChildren
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [idiasession:: Findchildren](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasession-findchildren)합니다.  
  
지정한 부모 식별자의 이름 및 기호 형식과 일치 하는 모든 자식을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT findChildren (   
   IDiaSymbol*       parent,  
   SymTagEnum        symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `parent`  
 [in] [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 부모를 나타내는 개체입니다. 이 부모 기호는 함수, 모듈 또는 블록 경우 어휘 자식을 반환 됩니다 `ppResult`합니다. 부모 기호 형식이 면 클래스 자식은 반환 됩니다. 이 매개 변수가 `NULL`, 한 다음 `symtag` 로 설정 해야 `SymTagExe` 또는 `SymTagNull`, 전역 범위 (.exe 파일)를 반환 하는 합니다.  
  
 `symtag`  
 [in] 검색할 자식 기호 태그를 지정 합니다. 값에서 수행 되는 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 열거형입니다. 로 `SymTagNull` 모든 자식을 검색할 수 있습니다.  
  
 `name`  
 [in] 검색할 자식 컨트롤의 이름을 지정 합니다. 로 `NULL` 검색할 모든 자식에 대 한 합니다.  
  
 `compareFlags`  
 [in] 이름 일치에 적용할 비교 옵션을 지정 합니다. 값을 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md) 열거형 따로 또는 함께 사용할 수 있습니다.  
  
 `ppResult`  
 [out] 반환 된 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) 자식 기호 목록을 포함 하는 개체 검색 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에는 함수의 로컬 변수를 찾는 방법을 보여 줍니다 `pFunc` 는 일치 하는 이름 `szVarName`합니다.  
  
```cpp#  
IDiaEnumSymbols* pEnum;  
pSession->findChildren( pFunc, SymTagData, szVarName, nsCaseSensitive, &pEnum );  
```  
  
## <a name="see-also"></a>참고 항목  
 [개요](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)


