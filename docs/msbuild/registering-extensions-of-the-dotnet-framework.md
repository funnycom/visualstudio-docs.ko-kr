---
title: ".NET Framework 확장명 등록 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Add References dialog box, registering extensions of the .NET Framework
- MSBuild, registering extensions of the .NET Framework
- .NET Framework extensions, registering
ms.assetid: deee6f53-ea87-4b88-a120-bea589822e03
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 495a6bb1d72e521b3f44ea989974446def555c15
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="registering-extensions-of-the-net-framework"></a>.NET Framework 확장명 등록
.NET Framework의 특정 버전을 확장하는 어셈블리를 개발할 수 있습니다. 해당 어셈블리가 Visual Studio의 **참조 추가** 대화 상자에 표시되도록 설정하려면 이 어셈블리를 포함하는 폴더를 시스템 레지스트리에 추가해야 합니다.  
  
 Trey Research라는 회사가 .NET Framework 4를 확장하는 라이브러리를 개발하여 프로젝트가 .NET Framework 4를 대상으로 할 때 라이브러리 어셈블리가 **참조 추가** 대화 상자에 표시되도록 하려는 경우를 예로 들어 보겠습니다. 이때 어셈블리는 32비트 컴퓨터에서 실행되는 32비트 어셈블리 또는 64비트 컴퓨터에서 실행되는 64비트 어셈블리이며 C:\TreyResearch\Extensions4\ 폴더에 설치된다고 가정합니다.  
  
 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\ 키를 사용하여 이 폴더를 등록합니다. 이 키에 기본값인 C:\TreyResearch\Extensions4를 지정합니다.  
  
> [!NOTE]
>  .NET Framework 버전의 빌드 번호는 다를 수 있습니다.  
  
 64비트 컴퓨터에서 32비트 어셈블리를 등록하려면 HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\와 같이 Wow6432 노드를 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 통합](../msbuild/visual-studio-integration-msbuild.md)