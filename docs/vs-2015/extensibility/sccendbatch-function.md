---
title: SccEndBatch 함수 | Microsoft Docs
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
- SccEndBatch
helpviewer_keywords:
- SccEndBatch function
ms.assetid: 100e7833-fe0a-45c0-9fca-3e61fd1165b7
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 075e661976062d2de985fa52110ea87840c2ab21
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543658"
---
# <a name="sccendbatch-function"></a>SccEndBatch 함수
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [SccEndBatch 함수](https://docs.microsoft.com/visualstudio/extensibility/sccendbatch-function)합니다.  
  
이 기능으로 소스 제어 작업의 일괄 처리를 마칩니다. 이러한 일괄 처리를 중첩할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
SCCRTN SccEndBatch(void);  
```  
  
#### <a name="parameters"></a>매개 변수  
 없음  
  
## <a name="return-value"></a>반환 값  
 원본 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환 하:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|일괄 처리 작업을 성공적으로 완료 합니다.|  
|SCC_E_UNKNOWNERROR|알 수 없는 오류가 발생 했습니다.|  
  
## <a name="remarks"></a>설명  
 원본 제어 일괄 처리는 여러 프로젝트 또는 여러 컨텍스트 간에 동일한 소스 제어 작업을 실행 하는 데 사용 됩니다. 일괄 처리 작업 중 사용자 환경에서 중복 대화 상자를 제거 하기 위해 일괄 처리를 사용할 수 있습니다. 합니다 [SccBeginBatch](../extensibility/sccbeginbatch-function.md) 하며 `SccEndBatch` 함수는 작업의 시작과 끝을 나타내는 데 쌍으로 사용 됩니다. 이러한 중첩 될 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [원본 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccBeginBatch](../extensibility/sccbeginbatch-function.md)
