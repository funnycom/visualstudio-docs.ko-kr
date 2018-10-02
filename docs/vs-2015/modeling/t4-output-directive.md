---
title: T4 출력 지시문 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03a14993-47ad-4f2e-8032-57db28d5842a
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: e0eaa2d8e3fc257e14e04bad3cac706b8a3bc92a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47552259"
---
# <a name="t4-output-directive"></a>T4 Output 지시문
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [T4 Output 지시문](https://docs.microsoft.com/visualstudio/modeling/t4-output-directive)합니다.  
  
[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 텍스트 템플릿에서 `output` 지시문은 변환된 파일의 인코딩과 파일 이름 확장명을 정의하는 데 사용됩니다.  
  
 예를 들어, 경우에 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 라는 템플릿 파일을 포함 하는 프로젝트 **MyTemplate.tt** 다음 지시문을 포함 하는:  
  
 `<#@output extension=".cs"#>`  
  
 그런 다음 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 라는 파일을 생성 하는 **MyTemplate.cs**  
  
 전처리된 런타임 텍스트 템플릿에는 `output` 지시문이 필요하지 않습니다. 대신 응용 프로그램은 `TextTransform()`을 호출하여 생성된 문자열을 가져옵니다. 자세한 내용은 [T4 텍스트 템플릿을 사용 하 여 런타임 텍스트 생성](../modeling/run-time-text-generation-with-t4-text-templates.md)합니다.  
  
## <a name="using-the-output-directive"></a>output 지시문 사용  
  
```  
<#@ output extension=".fileNameExtension" [encoding="encoding"] #>  
```  
  
 각 텍스트 템플릿에 `output` 지시문이 두 개 이상 있어서는 안 됩니다.  
  
## <a name="extension-attribute"></a>확장 특성  
 생성된 텍스트 출력 파일의 파일 이름 확장명을 지정합니다.  
  
 기본값은 **.cs**  
  
 예를 들면 다음과 같습니다.  
 `<#@ output extension=".txt" #>`  
  
 `<#@ output extension=".htm" #>`  
  
 `<#@ output extension=".cs" #>`  
  
 `<#@ output extension=".vb" #>`  
  
 허용되는 값:  
 유효한 모든 파일 이름 확장명  
  
## <a name="encoding-attribute"></a>인코딩 특성  
 출력 파일을 생성할 때 사용할 인코딩을 지정합니다. 예를 들면 다음과 같습니다.  
  
 `<#@ output encoding="utf-8"#>`  
  
 기본값은 텍스트 템플릿 파일에 사용되는 인코딩입니다.  
  
 허용되는 값:  
 `us-ascii`  
  
 `utf-16BE`  
  
 `utf-16`  
  
 `utf-8`  
  
 `utf-7`  
  
 `utf-32`  
  
 `0`(시스템 기본값)  
  
 일반적으로는 <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=fullName>가 반환하는 모든 인코딩으로 된 WebName 문자열 또는 CodePage 번호를 사용할 수 있습니다.


