---
title: -Edit(devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /edit switch
- /Edit Devenv swtich
ms.assetid: 02b3d6e7-a2b1-4d83-a747-aa8c2fb758b7
caps.latest.revision: "6"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 34b256a788f2ce8077d7f62921a63565f210139a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="edit-devenvexe"></a>/Edit (devenv.exe)
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 기존 인스턴스에 지정된 파일을 엽니다.  
  
## <a name="syntax"></a>구문  
  
```  
Devenv /edit [file1[ file2]]  
```  
  
## <a name="arguments"></a>인수  
 `file1`  
 선택 사항입니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 기존 인스턴스에서 열 파일입니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 인스턴스가 없으면 간소화된 창 레이아웃으로 새 인스턴스가 만들어지고 `file1`이 새 인스턴스에서 열립니다.  
  
 `file2`  
 선택 사항입니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 기존 인스턴스에서 열 하나 이상의 추가 파일입니다.  
  
## <a name="remarks"></a>설명  
 지정된 파일이 없고 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 기존 인스턴스가 있으면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 기존 인스턴스가 포커스를 받습니다. 지정된 파일이 없고 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 기존 인스턴스가 없으면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 새 인스턴스가 간소화된 창 레이아웃으로 만들어집니다.  
  
 예를 들어 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 기존 인스턴스가 모달 상태인 경우 [옵션 대화 상자](../../ide/reference/options-dialog-box-visual-studio.md)가 열리면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]이(가) 모달 상태를 벗어날 때 파일이 기존 인스턴스에서 열립니다.  
  
## <a name="example"></a>예  
 이 예제에서는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 기존 인스턴스로 `MyFile.cs` 파일을 열거나 없는 경우 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 새 인스턴스로 파일을 엽니다.  
  
```  
devenv /edit MyFile.cs  
```  
  
## <a name="see-also"></a>참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)