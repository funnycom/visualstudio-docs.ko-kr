---
title: "레거시 언어 서비스 개요 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: language services [managed package framework], about language services
ms.assetid: bb44e27b-d228-463c-b2cf-cd5c24c7c1b5
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 05805e5cf4b21f4c7d233cab7dd8421ee76f626f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="legacy-language-service-overview"></a>레거시 언어 서비스 개요
언어 서비스는 특정 구현할 수 있게 하는 편집기 지원 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 기능입니다. 자주 사용 하는 기능 및 기타 기능에 대 한 부분 지원에 대 한 모든 지원을 제공 하는 관리 패키지 프레임 워크 (MPF) 언어 서비스 클래스.  
  
## <a name="fully-supported-features-in-the-mpf"></a>MPF에 완벽 하 게 지원 되는 기능  
 MPF 언어 서비스 클래스는 다음과 같은 기능을 지원합니다.  
  
-   구문 강조  
  
-   개요  
  
-   코드의 주석 블록  
  
-   중괄호 일치  
  
-   코드 조각  
  
-   사용자 지정 문서 속성  
  
-   IntelliSense 매개 변수 정보  
  
-   IntelliSense 요약 정보  
  
-   IntelliSense 멤버 완성  
  
-   IntelliSense 단어 완성  
  
## <a name="partially-supported-features-in-the-mpf"></a>MPF에 부분적으로 지원 되는 기능  
 MPF는 다음과 같은 기능에 대 한 부분에 지원을 제공합니다. 즉, MPF에 의해 호출 되는 메서드를 구현 해야 합니다.  
  
-   코드를 다시 포맷 합니다. 다시 구현 하는 코드를 제공 합니다.  
  
-   올바른 코드를 식별 하 여 중단점을 유효성 검사에 걸쳐 있습니다. 코드 범위를 식별 하는 코드를 제공 합니다.  
  
-   디버거를 지 원하는 **자동** 변수를 표시 하기 위한 창. 작업 창에 표시을 결정 하는 코드를 제공 합니다.  
  
-   지 원하는 **탐색 모음** 빠르게 탐색할 수 있는 형식 및 멤버 사이 대 한 합니다. 구현 하 고 목록에서 정보를 표시 하는 도우미 클래스를 반환 합니다.는 **탐색 모음** 콤보 상자입니다.  
  
## <a name="implementation"></a>구현  
 언어 서비스 자체와 해당 언어에 지원 하 고 언어 서비스 기능을 구현 하려면 몇 가지 단계를 완료 해야 합니다. 이러한 단계는 다음 항목에 설명 합니다.  
  
-   [레거시 언어 서비스를 구현합니다.](../../extensibility/internals/implementing-a-legacy-language-service2.md)  
  
-   [레거시 언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service1.md)  
  
-   [레거시 언어 서비스의 구문 색 지정](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 중괄호 일치](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 개요 표시](../../extensibility/internals/outlining-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 코드 주석 처리](../../extensibility/internals/commenting-code-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 코드 서식 다시 지정](../../extensibility/internals/reformatting-code-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 사용자 지정 문서 속성](../../extensibility/internals/custom-document-properties-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 코드 조각 지원](../../extensibility/internals/support-for-code-snippets-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 탐색 모음 지원](../../extensibility/internals/support-for-the-navigation-bar-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 단어 완성](../../extensibility/internals/word-completion-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 멤버 완성](../../extensibility/internals/member-completion-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스에 대 한 매개 변수 정보](../../extensibility/internals/parameter-info-in-a-legacy-language-service2.md)  
  
-   [레거시 언어 서비스의 빠른 정보](../../extensibility/internals/quick-info-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 자동 창 지원](../../extensibility/internals/support-for-the-autos-window-in-a-legacy-language-service.md)  
  
-   [레거시 언어 서비스의 중단점 유효성 검사](../../extensibility/internals/validating-breakpoints-in-a-legacy-language-service.md)  
  
## <a name="see-also"></a>참고 항목  
 [레거시 언어 서비스를 구현합니다.](../../extensibility/internals/implementing-a-legacy-language-service1.md)   
 [레거시 언어 서비스 확장성](../../extensibility/internals/legacy-language-service-extensibility.md)