---
title: UsingNameSpace | Microsoft Docs
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
- UsingNamespace symbol tag
ms.assetid: e8e1beb5-7cb9-43b4-9ff4-760d5f91ea2d
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dbedc0fa1c718bf45472fa29309fa5d460c1c001
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47556385"
---
# <a name="usingnamespace"></a>UsingNameSpace
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [UsingNameSpace](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/usingnamespace)합니다.  
  
일부 기호 네임 스페이스에 의해 참조 될 수 있습니다 및 이후에로 식별 되었을 것을 `SymTagUsingNameSpace` 태그입니다.  
  
> [!NOTE]
>  UsingNamespace 기호 태그는 관리 코드에만 나타납니다.  
  
## <a name="properties"></a>속성  
 다음 표에서이 기호 형식에 대 한 잘못 된 속성을 보여 줍니다.  
  
|속성|데이터 형식|설명|  
|--------------|---------------|-----------------|  
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|바깥쪽 compiland, 블록 또는 함수에 대 한 기호입니다.|  
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|어휘 부모 기호 ID입니다.|  
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Namespace 이름입니다.|  
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|기호 인덱스 ID입니다.|  
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagNameSpace` (중 하나는 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값).|  
  
## <a name="see-also"></a>참고 항목  
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)


