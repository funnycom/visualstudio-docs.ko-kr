---
title: 명령줄에서 이식 가능한 프로파일링 데이터 파일 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ceb63a7-b835-4988-b756-2afc3fcc4808
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 314dc97e5881949ee69131576932db1865969b2c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47565315"
---
# <a name="creating-portable-profiling-data-files-from-the-command-line"></a>명령줄에서 이식 가능한 프로파일링 데이터 파일 만들기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [이식 가능한 프로 파일링 데이터 파일 만들기 명령줄에서](https://docs.microsoft.com/visualstudio/profiling/creating-portable-profiling-data-files-from-the-command-line)합니다.  
  
프로파일링 데이터를 더 쉽게 공유하기 위해 [VSPerfReport](../profiling/vsperfreport.md) 명령줄 도구를 사용하여 프로파일링 실행에 대한 기호를 .vsp 파일로 포함할 수 있습니다.  
  
 또한 더 작고 IDE에서 로드하는 데 더 빠른 미리 분석된 프로파일링 데이터(.vsps) 파일을 만들 수도 있습니다.  
  
> [!NOTE]
>  기호(.pdb) 파일을 **VSPerfReport**에 사용할 수 있는지 확인합니다. 자세한 내용은 [방법: 명령줄에서 기호 파일 위치 지정](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md)을 참조하세요.  
>   
>  **VSReport**에 대한 경로에 대한 자세한 내용은 [명령줄 도구의 경로 지정](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)을 참조하세요.  
>   
>  .vsps 파일에서 프로파일링 데이터를 필터링할 수 없습니다.  
  
### <a name="to-embed-the-symbols-for-a-profiling-run-into-a-profiling-data-vsp-file"></a>프로파일링 실행에 대한 기호를 프로파일링 데이터(.vsp) 파일에 포함하려면  
  
-   명령 프롬프트 창에서 다음 명령을 입력합니다.  
  
     \<Path>**VSPerfReport \<** VSP File> **/PackSymbols**  
  
     기본적으로 .vsps 파일은 .vsp 파일의 기본 이름으로 지정됩니다. **출력** 옵션을 사용하여 다른 이름을 지정할 수 있습니다.  
  
### <a name="to-create-a-summary-profiling-data-file"></a>요약 프로파일링 데이터 파일을 만들려면  
  
-   명령 프롬프트 창에서 다음 명령을 입력합니다.  
  
     \<Path>**VSPerfReport \<** VSP File> **/SummaryFile** [**/Output:**\<File Name>]  
  
     기본적으로 .vsps 파일은 .vsp 파일의 기본 이름으로 지정됩니다. **출력** 옵션을 사용하여 다른 이름을 지정할 수 있습니다.


