---
title: "getFloat64 메서드 (DataView) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 347adeb6-b24c-4e7d-8b6b-8e36aacdcae1
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ab6d52fcaa82cc957ba47b5ef2acdfbef90152d7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="getfloat64-method-dataview"></a>getFloat64 메서드(DataView)
보기의 시작 부분부터 지정 된 바이트 오프셋에서 Float64 값을 가져옵니다. 맞춤 제약 조건이 없습니다. 모든 오프셋에서 멀티 바이트 값을 가져올 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
var testFloat = dataView.getFloat64(byteOffset, littleEndian);   
```  
  
## <a name="parameters"></a>매개 변수  
 `testFloat`  
 필수 요소. 메서드에서 반환 되는 Float64 값입니다.  
  
 `byteOffset`  
 값을 검색 해야 하는 버퍼의 위치입니다.  
  
 `littleEndian`  
 선택 사항입니다. False 또는 정의 되지 않은 끝이 더 큰 값을 읽을 경우 little endian 값 읽어야 하며 그렇지 않으면.  
  
## <a name="remarks"></a>설명  
 보기의 끝을 넘어 읽게 하는 경우 이러한 메서드는 예외를 발생 시킵니다.  
  
## <a name="example"></a>예제  
 다음 예제에 DataView의 첫 번째 Float64를 가져오는 방법을 보여 줍니다.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            alert(dataView.getFloat64(0));  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]