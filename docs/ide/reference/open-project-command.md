---
title: "프로젝트 열기 명령 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- file.openproject
helpviewer_keywords:
- op command
- File.OpenProject command
- Open Project command
ms.assetid: baa85f86-041b-49f4-9ced-0c397dc180e1
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 6ae2b8f0c9f0a17f29bf42a8a2893f8671df4cd6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="open-project-command"></a>프로젝트 열기 명령
기존 프로젝트를 엽니다.  
  
## <a name="syntax"></a>구문  
  
```  
File.OpenProject filename  
```  
  
## <a name="arguments"></a>인수  
 `filename`  
 필수. 열 프로젝트의 전체 경로와 파일 이름입니다.  
  
 `filename` 인수 구문에서 공백을 포함하는 경로에는 따옴표를 사용해야 합니다.  
  
## <a name="remarks"></a>설명  
 입력 시 자동 완성에서 올바른 경로와 파일 이름을 찾으려고 합니다.  
  
 디버깅 중에는 이 명령을 사용할 수 없습니다.  
  
## <a name="example"></a>예  
 이 예제는 Test1이라는 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 프로젝트를 엽니다.  
  
```  
>File.OpenProject "C:\My Projects\Test1\Test1.vbproj"  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)