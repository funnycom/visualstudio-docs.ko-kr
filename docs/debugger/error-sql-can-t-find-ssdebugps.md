---
title: "오류: SQL 수 &#39; t 찾기 SSDEBUGPS | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.error.sqlde_cant_find_ssdebugps
dev_langs:
- CSharp
- VB
- FSharp
- C++
- SQL
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 69a82222fe1a4a2cd643f9f84127c3674f8078fd
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2018
---
# <a name="error-sql-can39t-find-ssdebugps"></a>T 찾기 SSDEBUGPS SQL 수 &#39; 오류:

SSDEBUGPS.dll은 SQL Server 디버깅 호스트 구성 요소입니다.

이 오류는 디버깅을 시작하려고 할 때 발생하며 지정한 파일이 [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] 컴퓨터에 없음을 나타냅니다. 원격 디버깅 설치를 실행하지 않았거나 어떤 이유로든지 이 파일이 삭제된 경우 이 오류가 발생할 수 있습니다.

이 오류를 해결 하는 방법은 두 가지가: 원격 디버깅 설치를 다시 실행 하 여 및에 해당 파일을 복사 하 여는 [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] 컴퓨터입니다.

지침에 따라 원격 디버깅 설치를 다시 실행 하려면 [원격 디버깅](../debugger/remote-debugging.md)합니다.

Ssdebugps.dll의 복사본을 찾을 수 있습니다에 복사는 [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] 컴퓨터입니다. 이 파일이 있는 경우 위치는 \Program Files\Common Files\Microsoft Shared\SQL Debugging 디렉터리입니다. 것이 다른 [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] 컴퓨터나 Visual Studio 2005가 설치 된 컴퓨터.

에 SQL Server 2005 컴퓨터에 SSDEBUGPS.dll을 복사 합니다.

1. 에 동일한 이름 및 경로 사용 하 여 디렉터리에 파일 복사는 [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] 컴퓨터입니다.

2. 열어 등록는 **명령 프롬프트**, 다음 명령을 실행 하 고 있습니다.

    ```
    regsrv32 ssdebugps.dll
    ```