---
title: dwTYPE_KIND | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- dwTYPE_KIND
helpviewer_keywords:
- dwTYPE_KIND enumeration
ms.assetid: 6ff56b0f-c502-4e6c-9829-bfa05361b783
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 026cf5e3f26cc6faeb8e8829295c0875203d88d1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554308"
---
# <a name="dwtypekind"></a>dwTYPE_KIND
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [dwTYPE_KIND](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/dwtype-kind)합니다.  
  
형식의 해석 하는 방법을 지정는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
enum enum_dwTYPE_KIND {  
   TYPE_KIND_METADATA = 0x0001,  
   TYPE_KIND_PDB      = 0x0002,  
   TYPE_KIND_BUILT    = 0x0003,  
};  
  
typedef DWORD dwTYPE_KIND;  
```  
  
```csharp  
public enum enum_dwTYPE_KIND {  
   TYPE_KIND_METADATA = 0x0001,  
   TYPE_KIND_PDB      = 0x0002,  
   TYPE_KIND_BUILT    = 0x0003,  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 TYPE_KIND_METADATA  
 합니다 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) union으로 해석할지를 [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md) 구조입니다.  
  
 TYPE_KIND_PDB  
 합니다 `TYPE_INFO` union으로 해석할지를 [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md) 구조입니다.  
  
 TYPE_KIND_BUILT  
 합니다 `TYPE_INFO` union으로 해석할지를 [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md) 구조입니다.  
  
## <a name="remarks"></a>설명  
 이 열거형의 값이 나타나는 `dwKind` 필드를 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) 구조체이 고 해석 하는 방법을 결정 하는 데 사용 되는 `type` 공용 구조체 멤버입니다. 합니다 `TYPE_INFO` 구조에 대 한 호출에서 반환 되는 [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)   
 [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md)   
 [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md)   
 [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md)   
 [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md)
