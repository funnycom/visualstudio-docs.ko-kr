---
title: "데이터 (디버그 인터페이스 액세스 SDK) | Microsoft Docs"
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
- global variables [C++], as symbols
- local variables [C++], as symbols
- class members [C++], as symbols
- Data symbol
ms.assetid: 0f17e96a-2e06-42c9-a877-3e5e670ee0ef
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 1f50ae8c40da9c895773330f488e63850013d35b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="data-debug-interface-access-sdk"></a>데이터(디버그 인터페이스 액세스 SDK)
모든 변수, 매개 변수, 지역 변수, 전역 변수, 클래스 멤버 등으로 식별 됩니다 `SymTagData` 기호입니다. 상수 값 (`LocIsConstant`)이이 형식으로 구분 됩니다.  
  
## <a name="properties"></a>속성  
 다음 표에서이 기호 형식에 대해 사용할 수 있는 속성을 보여 줍니다.  
  
|속성|데이터 형식|설명|  
|--------------|---------------|-----------------|  
|[IDiaSymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|값 중 하나는 필드는 [CV_access_e 열거형](../../debugger/debug-interface-access/cv-access-e.md)합니다.|  
|[IDiaSymbol::get_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|`DWORD`|오프셋된 부분의 location; 자세한 내용은 참조는 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)합니다.|  
|[IDiaSymbol::get_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|`DWORD`|섹션 부분의 location; 자세한 내용은 참조는 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)합니다.|  
|[IDiaSymbol::get_addressTaken](../../debugger/debug-interface-access/idiasymbol-get-addresstaken.md)|`BOOL`|`TRUE`이러한 데이터의이 주소는 다른 기호에 의해 참조 되는 경우.|  
|[IDiaSymbol::get_bitPosition](../../debugger/debug-interface-access/idiasymbol-get-bitposition.md)|`DWORD`|위치의; 비트 위치 자세한 내용은 참조는 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md) (DIA SDK v 8.0에서 지원 되지 않음).|  
|[IDiaSymbol::get_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|클래스, 구조체, 공용 구조체 또는 클래스 필드 이것이 대 한 기호입니다.|  
|[IDiaSymbol::get_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|ID 클래스 부모 기호입니다.|  
|[IDiaSymbol::get_compilerGenerated](../../debugger/debug-interface-access/idiasymbol-get-compilergenerated.md)|`BOOL`|`TRUE`데이터는 컴파일러에 의해 생성 되었습니다 하는 경우.|  
|[IDiaSymbol::get_constType](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE`경우 상수 행사로 데이터를 표시 합니다.|  
|[IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)|`DWORD`|중 하나는 [DataKind 열거형](../../debugger/debug-interface-access/datakind.md) 값입니다.|  
|[IDiaSymbol::get_isAggregated](../../debugger/debug-interface-access/idiasymbol-get-isaggregated.md)|`BOOL`|`TRUE`데이터는 집계 된 데이터 형식 (만 DIA SDK v 8.0 이상)의 일부 이면 합니다.|  
|[IDiaSymbol::get_isSplitted](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md)|`BOOL`|`TRUE`데이터를 여러 기호 (만 DIA SDK v 8.0 이상)에 대 한 집계로 분할 되어 있습니다.|  
|[IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`ULONGLONG`|비트 필드;의 길이 자세한 내용은 참조는 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)합니다.|  
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|바깥쪽 컴파일 대상, 함수 또는 블록에 대 한 기호입니다.|  
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|어휘 부모 기호의 ID입니다.|  
|[IDiaSymbol::get_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|`DWORD`|허용 가능한 위치 형식입니다. 자세한 내용은 참조 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md)|  
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|변수의 이름입니다.|  
|[IDiaSymbol::get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|`LONG`|레지스터의 내용을;에서 5 만큼 오프셋 자세한 내용은 참조는 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)합니다.|  
|[IDiaSymbol::get_registerId](../../debugger/debug-interface-access/idiasymbol-get-registerid.md)|`DWORD`|위치의; 지정자를 등록 합니다. 자세한 내용은 참조는 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)합니다.|  
|[IDiaSymbol::get_relativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|`DWORD`|해당 블록 내에서 데이터의 상대 위치입니다.|  
|[IDiaSymbol::get_slot](../../debugger/debug-interface-access/idiasymbol-get-slot.md)|`DWORD`|데이터의 슬롯 번호를 가져옵니다.|  
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|기호 인덱스 ID입니다.|  
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagData` (중 하나는 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값).|  
|[IDiaSymbol::get_token](../../debugger/debug-interface-access/idiasymbol-get-token.md)|`DWORD`|데이터를 나타내는 메타 데이터 토큰입니다.|  
|[IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|변수 형식에 대 한 기호입니다.|  
|[IDiaSymbol::get_typeId](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|변수 형식 기호의 ID입니다.|  
|[IDiaSymbol::get_unalignedType](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`데이터는 정렬 되지 않습니다.|  
|[IDiaSymbol::get_value](../../debugger/debug-interface-access/idiasymbol-get-value.md)|`VARIANT`|상수 데이터의 값입니다.|  
|[IDiaSymbol::get_virtualAddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|`ULONGLONG`|실행 파일 내에서 데이터의 위치입니다.|  
|[IDiaSymbol::get_volatileType](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`경우 데이터를 volatile로 표시 됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [CV_access_e 열거형](../../debugger/debug-interface-access/cv-access-e.md)   
 [DataKind 열거형](../../debugger/debug-interface-access/datakind.md)   
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)   
 [기호 위치](../../debugger/debug-interface-access/symbol-locations.md)