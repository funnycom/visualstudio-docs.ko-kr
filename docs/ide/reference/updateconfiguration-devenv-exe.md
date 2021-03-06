---
title: "-Updateconfiguration (devenv.exe) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- /updateconfiguration Devenv switch
- Devenv, /updateconfiguration switch
- updateconfiguration Devenv switch
ms.assetid: 9a1084cc-8b68-4ccc-aaea-f95939164338
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0ec3bfc47829bce2fe5ad836c970cb28f8a1294e
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2018
---
# <a name="updateconfiguration-devenvexe"></a>/Updateconfiguration (devenv.exe)
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에 시스템의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 패키지를 병합하고 MEF 캐시에서 변경 내용을 확인하도록 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
devenv /updateconfiguration  
```  
  
## <a name="remarks"></a>설명  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] VSIX 패키지를 설치하는 경우 이 명령을 자동으로 실행합니다. 파일을 패치한 후 `devenv.exe /updateconfiguration`을 실행하여 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에서 MEF 캐시를 업데이트하도록 해야 합니다. 이렇게 하면 수정 내용이 적합한지 여부를 평가할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 명령줄은 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에 시스템의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 패키지를 병합하고 MEF 캐시에서 변경 내용을 확인하도록 합니다.  
  
```  
Devenv.exe /updateconfiguration  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio IDE 개인 설정](../../ide/personalizing-the-visual-studio-ide.md)   
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)