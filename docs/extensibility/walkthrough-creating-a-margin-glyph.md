---
title: "연습: 여백 문자 모양 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], new - margin glyph
ms.assetid: 814185db-24f9-417f-b3b1-7c5aabb42b45
caps.latest.revision: "29"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fc813ed3c29c2fe0a4cac1c348ffed18ae8fd2d2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-margin-glyph"></a>연습: 여백 문자 모양 만들기
사용자 지정 편집기 확장을 사용 하 여 편집기의 여백과의 모양을 사용자 지정할 수 있습니다. 이 연습에서는 코드 주석에 "todo" 이라는 단어가 표시 될 때마다 표시기 여백에 사용자 지정 문자를 넣습니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-a-mef-project"></a>MEF 프로젝트 만들기  
  
1.  C# VSIX 프로젝트를 만듭니다. (에 **새 프로젝트** 대화 상자에서 **Visual C# / 확장성**, 다음 **VSIX 프로젝트**.) 솔루션 이름을 `TodoGlyphTest`합니다.  
  
2.  편집기 분류자 프로젝트 항목을 추가 합니다. 자세한 내용은 참조 [편집기 항목 템플릿을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-an-editor-item-template.md)합니다.  
  
3.  기존 클래스 파일을 삭제합니다.  
  
## <a name="defining-the-glyph"></a>문자 모양을 정의합니다.  
 문자 모양을 구현 하 여 정의 된 <xref:Microsoft.VisualStudio.Text.Editor.IGlyphFactory> 인터페이스입니다.  
  
#### <a name="to-define-the-glyph"></a>문자 모양이 정의 하려면  
  
1.  클래스 파일을 추가 하 고 이름을 `TodoGlyphFactory`합니다.  
  
2.  다음 추가 선언을 사용 하 여 합니다.  
  
     [!code-csharp[VSSDKTodoGlyphTest#1](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_1.cs)]
     [!code-vb[VSSDKTodoGlyphTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_1.vb)]  
  
3.  라는 클래스를 추가 `TodoGlyphFactory` 를 구현 하는 <xref:Microsoft.VisualStudio.Text.Editor.IGlyphFactory>합니다.  
  
     [!code-csharp[VSSDKTodoGlyphTest#2](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_2.cs)]
     [!code-vb[VSSDKTodoGlyphTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_2.vb)]  
  
4.  기호의 크기를 정의 하는 private 필드를 추가 합니다.  
  
     [!code-csharp[VSSDKTodoGlyphTest#3](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_3.cs)]
     [!code-vb[VSSDKTodoGlyphTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_3.vb)]  
  
5.  구현 `GenerateGlyph` 문자 모양 사용자 인터페이스 (UI) 요소를 정의 하 여 합니다. `TodoTag`이 연습의 뒷부분에서 정의 됩니다.  
  
     [!code-csharp[VSSDKTodoGlyphTest#4](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_4.cs)]
     [!code-vb[VSSDKTodoGlyphTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_4.vb)]  
  
6.  라는 클래스를 추가 `TodoGlyphFactoryProvider` 를 구현 하는 <xref:Microsoft.VisualStudio.Text.Editor.IGlyphFactoryProvider>합니다. 이 클래스와 내보내기는 <xref:Microsoft.VisualStudio.Utilities.NameAttribute> "TodoGlyph"의 <xref:Microsoft.VisualStudio.Utilities.OrderAttribute> 후 VsTextMarker의는 <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "code"의 및 <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> TodoTag의 합니다.  
  
     [!code-csharp[VSSDKTodoGlyphTest#5](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_5.cs)]
     [!code-vb[VSSDKTodoGlyphTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_5.vb)]  
  
7.  구현 된 <xref:Microsoft.VisualStudio.Text.Editor.IGlyphFactoryProvider.GetGlyphFactory%2A> 인스턴스화하여 메서드는 `TodoGlyphFactory`합니다.  
  
     [!code-csharp[VSSDKTodoGlyphTest#6](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_6.cs)]
     [!code-vb[VSSDKTodoGlyphTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_6.vb)]  
  
## <a name="defining-a-todo-tag-and-tagger"></a>Todo 태그 및 태거 정의  
 태그 형식 및 태거를 만들고 태거 공급자를 사용 하 여 내보내기 하 여 이전 단계에서 정의한 UI 요소와 표시기 여백 간의 관계를 정의 합니다.  
  
#### <a name="to-define-a-todo-tag-and-tagger"></a>Todo 태그 및 태거를 정의 하려면  
  
1.  새 클래스 파일을 프로젝트에 추가 하 고 이름을 `TodoTagger`합니다.  
  
2.  다음 가져오기를 추가 합니다.  
  
     [!code-csharp[VSSDKTodoGlyphTest#7](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_7.cs)]
     [!code-vb[VSSDKTodoGlyphTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_7.vb)]  
  
3.  라는 클래스를 추가 `TodoTag`합니다.  
  
     [!code-csharp[VSSDKTodoGlyphTest#8](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_8.cs)]
     [!code-vb[VSSDKTodoGlyphTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_8.vb)]  
  
4.  이름의 클래스를 수정 `TodoTagger` 를 구현 하는 <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> 형식의 `TodoTag`합니다.  
  
     [!code-csharp[VSSDKTodoGlyphTest#9](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_9.cs)]
     [!code-vb[VSSDKTodoGlyphTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_9.vb)]  
  
5.  에 `TodoTagger` 클래스에 대 한 전용 필드를 추가 <xref:Microsoft.VisualStudio.Text.Classification.IClassifier> 분류에서 찾을 텍스트를 포함 하 고 있습니다.  
  
     [!code-csharp[VSSDKTodoGlyphTest#10](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_10.cs)]
     [!code-vb[VSSDKTodoGlyphTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_10.vb)]  
  
6.  분류자를 설정 하는 생성자를 추가 합니다.  
  
     [!code-csharp[VSSDKTodoGlyphTest#11](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_11.cs)]
     [!code-vb[VSSDKTodoGlyphTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_11.vb)]  
  
7.  구현 된 <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A> 모든 분류를 검색 하 여 메서드 이름에 포함 된 단어 "주석" 및 검색 텍스트를 포함 하는 텍스트가 포함 됩니다. 검색 텍스트를 찾을 때마다 새 다시 생성 <xref:Microsoft.VisualStudio.Text.Tagging.TagSpan%601> 형식의 `TodoTag`합니다.  
  
     [!code-csharp[VSSDKTodoGlyphTest#12](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_12.cs)]
     [!code-vb[VSSDKTodoGlyphTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_12.vb)]  
  
8.  선언 된 `TagsChanged` 이벤트입니다.  
  
     [!code-csharp[VSSDKTodoGlyphTest#13](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_13.cs)]
     [!code-vb[VSSDKTodoGlyphTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_13.vb)]  
  
9. 라는 클래스를 추가 `TodoTaggerProvider` 를 구현 하는 <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider>, 및 사용 하 여 내보내기는 <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "코드"와 <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> TodoTag의 합니다.  
  
     [!code-csharp[VSSDKTodoGlyphTest#14](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_14.cs)]
     [!code-vb[VSSDKTodoGlyphTest#14](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_14.vb)]  
  
10. 가져오기는 <xref:Microsoft.VisualStudio.Text.Classification.IClassifierAggregatorService>합니다.  
  
     [!code-csharp[VSSDKTodoGlyphTest#15](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_15.cs)]
     [!code-vb[VSSDKTodoGlyphTest#15](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_15.vb)]  
  
11. 구현 된 <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider.CreateTagger%2A> 인스턴스화하여 메서드는 `TodoTagger`합니다.  
  
     [!code-csharp[VSSDKTodoGlyphTest#16](../extensibility/codesnippet/CSharp/walkthrough-creating-a-margin-glyph_16.cs)]
     [!code-vb[VSSDKTodoGlyphTest#16](../extensibility/codesnippet/VisualBasic/walkthrough-creating-a-margin-glyph_16.vb)]  
  
## <a name="building-and-testing-the-code"></a>코드 빌드 및 테스트  
 이 코드를 테스트 하려면 TodoGlyphTest 솔루션을 빌드하고 실험적 인스턴스에서 실행 합니다.  
  
#### <a name="to-build-and-test-the-todoglyphtest-solution"></a>빌드하고 TodoGlyphTest 솔루션을 테스트 하려면  
  
1.  솔루션을 빌드합니다.  
  
2.  F5 키를 눌러 프로젝트를 실행 합니다. Visual Studio의 두 번째 인스턴스가 인스턴스화됩니다.  
  
3.  표시기 여백 표시 되어 있는지 확인 합니다. (에 **도구** 메뉴를 클릭 하 여 **옵션**합니다. 에 **텍스트 편집기** 페이지에서 다음 사항을 확인 **표시기 여백** 을 선택 합니다.)  
  
4.  주석이 있는 코드 파일을 엽니다. 단어 "todo" 주석 섹션 중 하나를 추가 합니다.  
  
5.  표시기 여백에 코드 창의 왼쪽에 진한 파란색 개요 있는 밝은 파란색 원을 표시 됩니다.