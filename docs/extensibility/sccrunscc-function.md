---
title: "SccRunScc 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccRunScc
helpviewer_keywords: SccRunScc function
ms.assetid: bbe7c931-b17a-4779-9cf6-59e5f9f0c172
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4ad179325c4f34cd206a3c5e6b0840a69dd46037
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sccrunscc-function"></a>SccRunScc 함수
이 함수는 소스 제어 관리 도구를 호출합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccRunScc(  
   LPVOID  pvContext,  
   HWND    hWnd,  
   LONG    nFiles,  
   LPCSTR* lpFileNames  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pvContext  
 [in] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 [in] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에를 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 nFiles  
 [in] 에 지정 된 파일의 수는 `lpFileNames` 배열입니다.  
  
 lpFileNames  
 [in] 선택한 파일 이름 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|소스 제어 관리 도구를 호출 했습니다.|  
|SCC_I_OPERATIONCANCELED|작업이 취소 되었습니다.|  
|SCC_E_INITIALIZEFAILED|소스 제어 시스템을 초기화 하지 못했습니다.|  
|SCC_E_ACCESSFAILURE|소스 제어 시스템에 네트워크 또는 경합 문제 때문에 액세스 하는 문제가 발생 했습니다.|  
|SCC_E_CONNECTIONFAILURE|소스 제어 시스템에 연결 하지 못했습니다.|  
|SCC_E_FILENOTCONTROLLED|선택한 파일은 소스 제어 하지 않습니다.|  
|SCC_E_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다.|  
  
## <a name="remarks"></a>설명  
 이 함수는 호출자가 외부 관리 도구를 통해 소스 제어 시스템의 기능을 전부에 액세스할 수 있도록 합니다. 소스 제어 시스템에 사용자 인터페이스가 없는 경우 소스 제어 플러그 인 필요한 관리 기능을 수행 하려면 인터페이스를 구현할 수 있습니다.  
  
 이 함수는 개수 및 현재 선택 된 파일에 대 한 파일 이름 배열을 사용 하 여 호출 됩니다. 관리 도구에서 지원 가능한 경우 파일 목록이 데 사용할 수는 관리 인터페이스에서 파일을 미리 선택 그렇지 않으면 목록 무시할 수 있습니다.  
  
 이 함수는 일반적으로 사용자가을 선택할 때 호출 됩니다는 **시작 \<소스 제어 서버 >** 에서 **파일** -> **소스 제어** 메뉴입니다. 이 **시작** 메뉴 옵션 항상 사용 하지 않도록 설정 하거나도 레지스트리 항목을 설정 하 여 숨길 수 있습니다. 참조 [하는 방법: 소스 제어 플러그 인 설치](../extensibility/internals/how-to-install-a-source-control-plug-in.md) 대 한 자세한 내용은 합니다. 경우에이 함수는 호출 [SccInitialize](../extensibility/sccinitialize-function.md) 반환 된 `SCC_CAP_RUNSCC` 기능 비트 (참조 [기능 플래그](../extensibility/capability-flags.md) 이 및 다른 기능 비트에 대 한 자세한 내용은).  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [방법: 소스 제어 플러그 인 설치](../extensibility/internals/how-to-install-a-source-control-plug-in.md)   
 [기능 플래그](../extensibility/capability-flags.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)