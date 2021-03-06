---
title: "방법: MSBuild.exe를 사용하여 솔루션의 특정 대상 빌드 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, building specific targets in a solution
- msbuild.exe, building specific targets in a solution
- MSBuild, msbuild.exe
ms.assetid: f46feb9b-4c16-4fec-b6e1-36a959692ba3
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4437c8030f66ae24d94a83d796c0d0edf7e59c79
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2018
---
# <a name="how-to-build-specific-targets-in-solutions-by-using-msbuildexe"></a>방법: MSBuild.exe를 사용하여 솔루션의 특정 대상 빌드
MSBuild.exe를 사용하여 솔루션에서 특정 프로젝트의 특정 대상을 빌드할 수 있습니다.  
  
### <a name="to-build-a-specific-target-of-a-specific-project-in-a-solution"></a>솔루션에서 특정 프로젝트의 특정 대상을 빌드하려면  
  
1.  명령줄에서 `MSBuild.exe <SolutionName>.sln`을 입력합니다. 여기서 `<SolutionName>`은 실행할 대상이 포함된 솔루션의 파일 이름에 해당합니다.  
  
2. `/target:` 스위치 뒤에 대상을 **`ProjectName`**`:`**`TargetName`** 형식으로 지정합니다. 프로젝트 이름에 `%`, `$`, `@`, `;`, `.`, `(`, `)` 또는 `'` 문자를 포함하는 경우 지정된 대상 이름에서 `_`로 변경합니다.
  
## <a name="example"></a>예  
 다음 예제에서는 `NotInSlnFolder` 프로젝트의 `Rebuild` 대상을 실행하고 나서 `NewFolder` 솔루션 폴더에 있는 `InSolutionFolder` 프로젝트의 `Clean` 대상을 실행합니다.  
  
```
msbuild SlnFolders.sln /target:NotInSlnfolder:Rebuild;NewFolder\InSolutionFolder:Clean`
```

## <a name="troubleshooting"></a>문제 해결

사용할 수 있는 옵션을 검사하려는 경우 MSBuild에서 제공하는 디버깅 옵션을 사용할 수 있습니다. `MSBUILDEMITSOLUTION=1` 환경 변수를 설정하고 솔루션을 빌드합니다. 그러면 빌드 시 솔루션의 MSBuild의 내부 보기를 보여주는 `<SolutionName>.sln.metaproj`라는 MSBuild 파일을 만듭니다. 이 보기를 검사하여 빌드할 수 있는 대상을 확인할 수 있습니다.

이 내부 보기가 필요하지 않으면 이 환경 변수 설정을 사용하여 빌드하지 않습니다. 이 설정은 솔루션에서 프로젝트를 빌드하는 문제가 발생할 수 있습니다.

## <a name="see-also"></a>참고 항목  
 [명령줄 참조](../msbuild/msbuild-command-line-reference.md)   
 [MSBuild 참조](../msbuild/msbuild-reference.md)   
 [MSBuild](../msbuild/msbuild.md)  
 [MSBuild 개념](../msbuild/msbuild-concepts.md)
