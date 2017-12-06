---
title: "Visual Studio에서 색 테마 및 글꼴 설정 | Microsoft Docs"
ms.custom: 
ms.date: 11/20/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7adb1ec7badaefceb8430d0fcacd8e54e7404ea7
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2017
---
# <a name="quickstart-personalize-the-visual-studio-ide-and-editor"></a>빠른 시작: Visual Studio IDE 및 편집기 개인 설정

이 5~10분이 걸리는 빠른 시작에서는 텍스트 편집기에서 Visual Studio 색 테마 및 두 개의 텍스트 색을 사용자 지정합니다.

## <a name="set-the-color-theme"></a>색 테마 설정

Visual Studio 2017의 기본 색 테마는 **파랑**이라고 합니다. **어두운**으로 변경해 보겠습니다.

1. 메뉴 모음에서 **도구**, **옵션**을 선택합니다.

1. **환경**, **일반** 옵션 페이지에서 **색 테마** 선택을 **어두운**으로 변경한 다음 **확인**을 선택합니다.

   전체 IDE의 색 테마가 **어두운**으로 변경됩니다.

   ![어두운 테마의 VS](media/quickstart-personalize-dark-theme.png)

> [!TIP]
> [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=VisualStudioProductTeam.VisualStudio2017ColorThemeEditor)에서 **Visual Studio 색 테마 편집기**를 설치하여 미리 정의된 추가 테마를 설치할 수 있습니다. 이 도구를 설치하면 색 테마 드롭다운 목록에 추가 색 테마가 나타납니다.

## <a name="change-text-color"></a>텍스트 색 변경

이제 편집기의 일부 텍스트 색을 사용자 지정해 보겠습니다. 먼저 XML 파일을 열어 기본 색을 확인하겠습니다.

1. 메뉴 모음에서 **파일**, **새로 만들기**, **파일...**을 차례로 선택합니다.

1. **새 파일** 대화 상자의 **일반** 범주 아래에서 **XML 파일**을 선택한 다음 **열기**를 선택합니다.

1. `<?xml version="1.0" encoding="utf-8"?>`를 포함하는 줄 아래에 다음 XML을 붙여넣습니다.

   ```xml
   <Catalog>
     <Book id="bk101">
     <Author>Garghentini, Davide</Author>
     <Title>XML Developer's Guide</Title>
     <Genre>Computer</Genre>
     <Price>44.95</Price>
     <PublishDate>2000-10-01</PublishDate>
     <Description>
       An in-depth look at creating applications with XML.
     </Description>
   </Book>
   <Book id="bk102">
     <Author>Garcia, Debra</Author>
     <Title>Midnight Rain</Title>
     <Genre>Fantasy</Genre>
     <Price>5.95</Price>
     <PublishDate>2000-12-16</PublishDate>
     <Description>
       A former architect battles corporate zombies, an evil
       sorceress, and her own childhood to become queen of the world.
     </Description>
   </Book>
   </Catalog>
   ```

   줄 번호는 옥색이며, xml 특성은 연한 파랑색입니다. 이러한 항목의 텍스트 색을 변경해 보겠습니다.

   ![XML 파일 글꼴 색](media/quickstart-personalize-xml-file.png)

1. **옵션** 대화 상자를 열려면 메뉴 모음에서 **도구**, **옵션**을 차례로 선택합니다.

1. **환경** 아래에서 **글꼴 및 색** 범주를 선택합니다.

   **설정 표시** 아래의 텍스트에 **텍스트 편집기**라고 표시됩니다. 이것이 우리가 원하는 설정입니다. 드롭다운 목록을 확장하여 글꼴 및 텍스트 색을 사용자 지정할 수 있는 위치의 광범위한 목록을 표시할 수 있습니다.

1. 줄 번호 텍스트의 색을 변경하려면 **표시 항목** 목록에서 **줄 번호**를 선택합니다. **항목 전경** 상자에서 **올리브**를 선택합니다.

   ![옵션 대화 상자, 글꼴 및 색 범주](media/quickstart-personalize-line-number-color.png)

1. 대화 상자를 종료하기 전에 XML 특성의 색도 변경해 보겠습니다. **표시 항목** 목록에서 **XML 특성**이 표시될 때까지 아래로 스크롤하여 선택합니다. **항목 전경** 상자에서 **라임**을 선택합니다. **확인**을 선택하여 선택 항목을 저장하고 대화 상자를 닫습니다.

   이제 줄 번호는 올리브색이며, XML 특성은 밝은 라임 녹색입니다. C++ 또는 C# 코드 파일과 같은 다른 파일 형식을 열면 해당 줄 번호도 올리브색으로 표시됩니다.

   ![새 글꼴 색이 적용된 XML 파일](media/quickstart-personalize-xml-file-new-colors.png)

Visual Studio에서 색을 사용자 지정하는 몇 가지 방법을 살펴보았습니다. **옵션** 대화 상자에서 다른 사용자 지정 옵션도 탐색하여 자신에게 맞게 Visual Studio를 설정하시기 바랍니다.

## <a name="see-also"></a>참고 항목

[빠른 시작: 먼저 Visual Studio IDE 살펴보기](../ide/quickstart-ide-orientation.md)  
[Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)  
[편집기 사용자 지정](../ide/customizing-the-editor.md)  
[Visual Studio IDE 개요](../ide/visual-studio-ide.md)