---
title: '방법: 항목 목록을 쉼표로 구분하여 표시 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSBuild, separating items with semicolons
- MSBuild, formatting item collections
ms.assetid: 3cae844c-7c6d-4144-82dc-efad10ba458f
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 62fbbfd7df89eee06f476a496b5a7c020c0ff211
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47541743"
---
# <a name="how-to-display-an-item-list-separated-with-commas"></a>방법: 항목 목록을 쉼표로 구분하여 표시
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법:는 항목 목록을 쉼표로 구분 하 여 표시](https://docs.microsoft.com/visualstudio/msbuild/how-to-display-an-item-list-separated-with-commas)합니다.  
  
  
[!INCLUDE[vstecmsbuildengine](../includes/vstecmsbuildengine-md.md)] ([!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)])에서 항목 목록을 사용할 때 쉽게 읽을 수 있는 방식으로 해당 항목 목록의 내용을 표시하는 데 유용합니다. 또는 특별한 구분 기호 문자열로 구분된 항목의 목록을 사용하는 작업이 있을 수 있습니다. 이러한 모든 경우에 항목 목록에 대한 구분 기호 문자열을 지정할 수 있습니다.  
  
## <a name="separating-items-in-a-list-with-commas"></a>목록에서 항목을 쉼표로 구분  
 기본적으로 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)]는 세미콜론을 사용하여 목록에서 항목을 구분합니다. 예를 들어 다음 값을 가진 `Message` 요소가 있습니다.  
  
 `<Message Text="This is my list of TXT files: @(TXTFile)"/>`  
  
 `@(TXTFile)` 항목 목록에 App1.txt, App2.txt 및 App3.txt 항목이 포함되는 경우 다음과 같은 메시지가 표시됩니다.  
  
 `This is my list of TXT files: App1.txt;App2.txt;App3.txt`  
  
 기본 동작을 변경하려는 경우 고유한 구분 기호를 지정할 수 있습니다. 항목 목록 구분 기호를 지정하는 구문은 다음과 같습니다.  
  
 `@(ItemListName, '<separator>')`  
  
 구분 기호는 단일 문자 또는 문자열이며 작은따옴표로 묶어야 합니다.  
  
#### <a name="to-insert-a-comma-and-a-space-between-items"></a>항목 사이에 쉼표 및 공백을 삽입하려면  
  
-   다음과 유사한 항목 표기법을 사용합니다.  
  
     `@(TXTFile, ', ')`  
  
## <a name="example"></a>예제  
 이 예제에서 [Exec](../msbuild/exec-task.md) 작업은 findstr 도구를 실행하여 Phrases.txt 파일에 지정된 텍스트 문자열을 찾습니다. findstr 명령에서 리터럴 검색 문자열은 **/c:** 스위치로 나타나므로 항목 구분 기호 `/c:`는 `@(Phrase)` 항목 목록에 있는 항목 사이에 삽입됩니다.  
  
 이 예제에서 해당하는 명령줄 명령은 다음과 같습니다.  
  
 `findstr /i /c:hello /c:world /c:msbuild phrases.txt`  
  
```  
<Project DefaultTargets = "Find"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <ItemGroup>  
        <Phrase Include="hello"/>  
        <Phrase Include="world"/>  
        <Phrase Include="msbuild"/>  
    </ItemGroup>  
  
    <Target Name = "Find">  
        <!-- Find some strings in a file -->  
        <Exec Command="findstr /i /c:@(Phrase, ' /c:') phrases.txt"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>참고 항목  
 [MSBuild 참조](../msbuild/msbuild-reference.md)   
 [항목](../msbuild/msbuild-items.md)


