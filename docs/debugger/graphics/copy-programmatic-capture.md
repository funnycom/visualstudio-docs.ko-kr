---
title: "복사 (프로그램 방식 캡처) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7f8fce1893363ac6df0e6d22320f718833a1114e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="copy-programmatic-capture"></a>복사(프로그램 방식 캡처)
활성 그래픽 로그(.vsglog) 파일 내용을 새 파일에 복사합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
void Copy(  
  wchar_t const * szNewVSGLog  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `szNewVSGLog`  
 새 그래픽 로그 파일 이름입니다.  
  
## <a name="remarks"></a>설명  
 그래픽 정보를 새 파일에 복사하려면 이미 캡처한 일부 그래픽 정보가 있어야 합니다. 그렇지 않으면 아무 것도 실행되지 않습니다.