---
title: "Bookmark 컨트롤 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.Toolbox.Bookmark
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- bookmarks, controlling
- Bookmark control, data binding
- Bookmark control, events
- Bookmark control
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 38e3286d24f0591ca4ced3339118b6d0d4bfe1d7
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="bookmark-control"></a>Bookmark 컨트롤
  <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤은 고유한 이름이 있고 이벤트를 노출하며 데이터에 바인딩될 수 있는 책갈피입니다. 책갈피는 Microsoft Office Word 문서에서 항목 또는 위치를 표시하는 자리 표시자로 사용할 수 있습니다. <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤은 <xref:Microsoft.Office.Interop.Word.Bookmark> 개체 및 <xref:Microsoft.Office.Interop.Word.Range> 개체의 조합입니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 문서 수준 프로젝트에서는 디자인 타임 또는 런타임에 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 문서에 추가할 수 있습니다. VSTO 추가 기능 프로젝트에서는 런타임에 열려 있는 임의 문서에 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 추가할 수 있습니다. 자세한 내용은 [How to: Add Bookmark Controls to Word Documents](../vsto/how-to-add-bookmark-controls-to-word-documents.md)을 참조하세요.  
  
## <a name="binding-data-to-the-control"></a>컨트롤에 데이터 바인딩  
 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤은 단순 데이터 바인딩을 지원합니다. 책갈피는 <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> 속성을 사용하여 데이터 원본에 바인딩해야 합니다. 책갈피의 기본 데이터 바인딩 속성은 <xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A> 속성입니다.  
  
 바인딩된 데이터 집합의 데이터가 업데이트되면 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤이 변경 내용을 반영합니다.  
  
 문서 수준 프로젝트에서 **데이터 원본** 창을 사용하여 데이터를 책갈피에 바인딩할 수 있습니다. 자세한 내용은 [How to: Populate Documents with Data from Objects](../vsto/how-to-populate-documents-with-data-from-objects.md)을 참조하십시오.  
  
## <a name="formatting"></a>서식  
 <xref:Microsoft.Office.Interop.Word.Bookmark> 에 적용할 수 있는 서식은 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤에 적용할 수 있습니다. 여기에는 글꼴, 들여쓰기, 간격, 번호 매기기 및 스타일이 포함됩니다.  
  
## <a name="assigning-text-to-the-bookmark"></a>책갈피에 텍스트 할당  
 <xref:Microsoft.Office.Interop.Word.Bookmark> 개체와 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤 간의 추가 차이점은 텍스트가 책갈피에 할당될 때 동작하는 방법입니다. 텍스트를 길이가 0인 <xref:Microsoft.Office.Interop.Word.Bookmark>에 할당하는 경우 텍스트가 책갈피의 오른쪽에 추가되고 책갈피는 길이가 0인 상태로 유지됩니다. 그러나 텍스트를 길이가 0인 <xref:Microsoft.Office.Tools.Word.Bookmark>에 할당하는 경우 텍스트가 책갈피로 삽입되고 책갈피 길이는 삽입된 문자의 총 수로 확장됩니다.  
  
 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤에는 또한 <xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A> 속성도 있습니다. 이 속성은 <xref:Microsoft.Office.Interop.Word.Range.Text%2A> 컨트롤의 <xref:Microsoft.Office.Tools.Word.Bookmark.Range%2A> 속성 또는 <xref:Microsoft.Office.Tools.Word.Bookmark> 개체의 <xref:Microsoft.Office.Interop.Word.Bookmark.Range%2A> 속성에서 사용할 수 있는 <xref:Microsoft.Office.Interop.Word.Bookmark> 속성과 다릅니다.  
  
|Text 속성|설명|  
|-------------------|-----------------|  
|<xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A>|이 속성을 사용하여 텍스트를 책갈피 안에 표시하고 문서에 책갈피를 남겨 둡니다. 텍스트를 책갈피에 할당하면 책갈피 범위를 확장하고 책갈피를 삭제하지 않습니다.<br /><br /> 예를 들어 `Bookmark1.Text = "Hello world"` 는 텍스트를 책갈피에 삽입하고 책갈피를 그대로 둡니다.|  
|<xref:Microsoft.Office.Interop.Word.Range.Text%2A>|이 속성을 사용하여 책갈피 위치에 텍스트를 표시하고 책갈피를 자동으로 삭제합니다. 예를 들어 `Bookmark1.Range.Text = "Hello world"` 는 책갈피에 텍스트를 삽입하고 책갈피를 삭제합니다.|  
  
## <a name="renaming-the-control-at-design-time"></a>디자인 타임에 컨트롤 이름 바꾸기  
 문서 수준 프로젝트에서 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 **도구 상자** 에서 문서로 끌어 놓으면 Visual Studio가 자동으로 컨트롤의 이름을 생성합니다. **속성** 창에서 컨트롤의 이름을 변경할 수 있습니다.  
  
## <a name="overlapping-controls"></a>컨트롤 겹침  
 책갈피 컨트롤은 서로 겹칠 수 있습니다. 즉, 동일한 텍스트를 둘 이상의 책갈피에서 공유할 수 있습니다. 겹치는 책갈피 중 하나에 새 텍스트를 할당하면 새 텍스트만 포함하고 책갈피는 더 이상 겹치지 않게 됩니다. 이제 다른 책갈피는 원래 겹치는 책갈피 간에 공유하지 않은 텍스트만 포함합니다.  
  
 다음 표는 "This is sample text." 문장이 두 개의 겹치는 책갈피에서 공유되는 방법을 보여 줍니다.  
  
|책갈피|텍스트|  
|--------------|----------|  
|겹치는 책갈피|[this is {sample] text.}|  
|책갈피1|This is sample|  
|책갈피2|sample text.|  
  
 새 텍스트 "This is replacement."를 책갈피1에 할당하면 책갈피가 더 이상 겹치지 않고 책갈피2는 원래 책갈피1에 속하지 않았던 텍스트만 유지합니다.  
  
|책갈피|텍스트|  
|--------------|----------|  
|별도의 두 책갈피|[this is replacement]{ text.}|  
|책갈피1|This is replacement|  
|책갈피2|text.|  
  
 하나의 책갈피가 다른 책갈피 내에 완전히 포함된 상태에서 외부 책갈피의 텍스트를 변경하는 경우 내부 책갈피는 삭제되지 않습니다. 그러나 내부 책갈피는 빈 책갈피가 되어 외부 책갈피 끝으로 이동합니다. 다음 표는 "This is sample text." 문장이 다른 책갈피 내에 포함된 책갈피에서 공유되는 방법을 보여 줍니다.  
  
|책갈피|텍스트|  
|--------------|----------|  
|겹치는 책갈피|[this is {sample} text.]|  
|책갈피1|This is sample text.|  
|책갈피2|sample|  
  
 새 텍스트 "This is replacement."를 책갈피1에 할당하는 경우 책갈피가 더 이상 겹치지 않고 책갈피2는 책갈피1의 끝에 있는 빈 책갈피가 됩니다.  
  
|책갈피|텍스트|  
|--------------|----------|  
|별도의 두 책갈피|[this is replacement.]{}|  
|책갈피1|This is replacement.|  
|책갈피2|*\<빈 >*|  
  
## <a name="events"></a>이벤트  
 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤에 대해 다음 이벤트를 사용할 수 있습니다.  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.Deselected>  
  
-   <xref:System.ComponentModel.IComponent.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.Selected>  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.SelectionChange>  
  
## <a name="see-also"></a>참고 항목  
 [확장 된 개체를 사용 하 여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)   
 [How to: Add Bookmark Controls to Word Documents](../vsto/how-to-add-bookmark-controls-to-word-documents.md)   
 [연습: 책갈피에 대 한 바로 가기 메뉴 만들기](../vsto/walkthrough-creating-shortcut-menus-for-bookmarks.md)   
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  