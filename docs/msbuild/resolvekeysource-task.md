---
title: "ResolveKeySource 작업 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ResolveKeySource
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ResolveKeySource task [MSBuild]
- MSBuild, ResolveKeySource task
ms.assetid: 449f06c2-e9aa-4236-ab1e-c45c25452b2e
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 42faa2075c7c594ff19b15bf2be16742b62f6202
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="resolvekeysource-task"></a>ResolveKeySource 작업
강력한 이름 키 원본을 확인합니다.  
  
## <a name="task-parameters"></a>작업 매개 변수  
 다음 표에서는 `ResolveKeySource` 작업의 매개 변수에 대해 설명합니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`AutoClosePasswordPromptShow`|선택적 `Int32` 매개 변수입니다.<br /><br /> 카운트다운 메시지를 표시할 시간(초)을 설정하거나 가져옵니다.|  
|`AutoClosePasswordPromptTimeout`|선택적 `Int32` 매개 변수입니다.<br /><br /> 암호 프롬프트 대화 상자를 닫기 전에 대기하는 시간(초)을 가져오거나 설정합니다.|  
|`CertificateFile`|선택적 `String` 매개 변수입니다.<br /><br /> 인증서 파일의 경로를 가져오거나 설정합니다.|  
|`CertificateThumbprint`|선택적 `String` 매개 변수입니다.<br /><br /> 인증서 지문을 가져오거나 설정합니다.|  
|`KeyFile`|선택적 `String` 매개 변수입니다.<br /><br /> 키 파일의 경로를 가져오거나 설정합니다.|  
|`ResolvedKeyContainer`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 확인된 키 컨테이너를 가져오거나 설정합니다.|  
|`ResolvedKeyFile`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 확인된 키 파일을 가져오거나 설정합니다.|  
|`ResolvedThumbprint`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 확인된 인증서 지문을 가져오거나 설정합니다.|  
|`ShowImportDialogDespitePreviousFailures`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 이전에 실패했어도 가져오기 대화 상자를 표시합니다.|  
|`SuppressAutoClosePasswordPrompt`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 암호 프롬프트 대화 상자가 자동으로 닫혀서는 안 되는지 여부를 지정하는 부울 값을 가져오거나 설정합니다.|  
  
## <a name="remarks"></a>설명  
 이 작업은 위에 나와 있는 매개 변수 외에 <xref:Microsoft.Build.Utilities.Task> 클래스에서 직접 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수도 상속합니다. 이러한 추가 매개 변수 및 해당 설명이 포함된 목록은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [작업 참조](../msbuild/msbuild-task-reference.md)