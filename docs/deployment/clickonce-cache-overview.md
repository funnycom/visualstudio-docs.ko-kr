---
title: "ClickOnce 캐시 개요 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Windows applications, ClickOnce deployemtn
- ClickOnce applications, cache
- ClickOnce deployment, cache
ms.assetid: e379921e-9ef1-4326-bbf3-53ba67925526
caps.latest.revision: "12"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 9ca3465aafc36af24f36f86edd5bf3dc5c69d576
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="clickonce-cache-overview"></a>ClickOnce 캐시 개요
모든 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 로컬로 설치 또는 온라인으로 호스팅되에 저장 된 클라이언트 컴퓨터에는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]응용 프로그램 *캐시*합니다. A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 캐시는 현재 사용자의 Documents and Settings 폴더의 로컬 설정 디렉터리 아래에 있는 숨겨진된 디렉터리의 집합입니다. 이 캐시는 어셈블리, 구성 파일, 응용 프로그램 및 사용자 설정 및 데이터 디렉터리를 포함 하 여 응용 프로그램의 모든 파일을 보유 합니다. 또한이 캐시는 응용 프로그램의 데이터 디렉터리를 최신 버전으로 마이그레이션하기 위한 합니다. 데이터 마이그레이션에 대 한 자세한 내용은 참조 [로컬 액세스 및 ClickOnce 응용 프로그램의 원격 데이터](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)합니다.  
  
 응용 프로그램 저장소에 대 한 단일 위치를 제공 하 여 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 사용자 로부터 응용 프로그램의 실제 설치 관리 작업을 수행 합니다. 캐시 ּ µ ֻ 어셈블리 및 모든 응용 프로그램에 대 한 데이터 파일을 유지 하 여 응용 프로그램을 격리 및 프로그램과 개별 버전 서로 분리 합니다. 예를 들어 업그레이드 하는 경우는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에서는, 버전 및 해당 데이터 리소스 캐시 자신의 디렉터리와 함께 제공 됩니다.  
  
## <a name="cache-storage-quota"></a>캐시 저장소 할당량  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]온라인으로 호스팅되는 응용 프로그램의 크기를 제한 하는 할당 공간을 차지할 수 제한 됩니다.는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 캐시 합니다. 모든 사용자의 온라인 응용 프로그램에 캐시 크기가 적용 됩니다. 단일 부분적으로 신뢰할 수 있는, 온라인 응용 프로그램의 할당량 공간 반만 사용 하도록 제한 됩니다. 설치 된 응용 프로그램 캐시 크기에 의해 제한 되지 않습니다 및 캐시 제한에 포함 되지 않습니다. 모든 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 이전에 설치 된 버전과 현재 버전에만 응용 프로그램의 경우 캐시를 유지 합니다.  
  
 클라이언트 컴퓨터 기본적으로 250MB의 사용에 대 한 저장소 온라인 적용 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램입니다. 데이터 파일이이 제한까지 계산 되지 않습니다. 시스템 관리자를 확대 하거나 레지스트리 키 DWORD 값 HKEY_CURRENT_USER\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment\OnlineAppQuotaInKB를 변경 하 여 특정 클라이언트 컴퓨터에이 할당량을 줄일 수 있습니다. 캐시 크기 (킬로바이트)을 표현합니다. 예를 들어 캐시 크기를 50MB을 줄이려면 51200로이 값을 변경 되 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램의 로컬 및 원격 데이터 액세스](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)