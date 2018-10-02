---
title: 새 항목 추가 명령 | Microsoft 문서
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- project.addnewitem
helpviewer_keywords:
- Add New Item command
- File.AddNewItem command
ms.assetid: 63b7df32-db83-463b-bbe7-7ff011fe5298
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8f380a11440ed413871d2c80603148aa7cc77390
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554471"
---
# <a name="add-new-item-command"></a>새 항목 추가 명령
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [새 항목 추가 명령](https://docs.microsoft.com/visualstudio/ide/reference/add-new-item-command)입니다.  
  
  
현재 솔루션에 .htm, .css, .txt 또는 프레임셋 같은 새 솔루션 항목을 추가하고 엽니다.  
  
## <a name="syntax"></a>구문  
  
```  
File.AddNewItem [filename] [/t:templatename] [/e:editorname]  
```  
  
## <a name="arguments"></a>인수  
 `filename`  
 선택 사항입니다. 솔루션에 추가할 항목의 경로와 파일 이름입니다.  
  
## <a name="switches"></a>스위치  
 /t: `templatename`  
 선택 사항입니다. 만들 파일의 형식을 지정합니다. 템플릿 이름이 지정되지 않은 경우 기본적으로 텍스트 파일이 만들어집니다.  
  
 /t:`templatename` 인수 구문은 **새 솔루션 항목 추가** 대화 상자에 있는 정보를 미러링합니다. 전체 범주 뒤에 파일 형식을 입력해야 합니다. 백슬래시(`\`)로 범주 이름과 파일 형식을 구분하고 전체 문자열을 따옴표로 묶습니다.  
  
 예를 들어 새 텍스트 파일을 만들려면 /t:`templatename` 인수에 대해 다음과 같이 입력합니다.  
  
```  
/t:"General\Style Sheet"  
```  
  
 /e: `editorname`  
 선택 사항입니다. 파일이 열리는 편집기의 이름입니다. 편집기 이름을 제공하지 않고 인수를 지정한 경우 **연결 프로그램** 대화 상자가 나타납니다.  
  
 /e:`editorname` 인수 구문은 **연결 프로그램 대화 상자**에 따옴표로 묶여 나타나는 순서대로 편집기 이름을 사용합니다.  
  
 예를 들어 소스 코드 편집기에서 스타일시트를 열려면 /e:`editorname` 인수에 대해 다음과 같이 입력합니다.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="example"></a>예제  
 이 예제에서는 새 솔루션 항목인 MyHTMLpg를 현재 솔루션에 추가합니다.  
  
```  
>File.AddNewItem MyHTMLpg /t:"General\HTML Page"  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)


