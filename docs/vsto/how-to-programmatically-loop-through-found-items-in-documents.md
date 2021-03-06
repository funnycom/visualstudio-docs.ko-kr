---
title: "방법: 프로그래밍 방식으로 문서에서 찾은 항목 반복 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- loops, through found items in documents
- documents [Office development in Visual Studio], searching
- text [Office development in Visual Studio], searching in documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 7ad153a0a08546ebc9fad93ce7287e4c2fc4a043
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-loop-through-found-items-in-documents"></a>방법: 프로그래밍 방식으로 문서에서 찾은 항목 순환 검색
  <xref:Microsoft.Office.Interop.Word.Find> 클래스에는 <xref:Microsoft.Office.Interop.Word.Find.Found%2A> 반환 하는 속성 **true** 검색 한 항목을 찾을 때마다. <xref:Microsoft.Office.Interop.Word.Range> 메서드를 사용하여 <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> 에서 찾은 모든 인스턴스를 순환 검색할 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-loop-through-found-items"></a>찾은 항목을 순환 검색하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Range> 개체를 선언합니다.  
  
     다음 코드 예제는 문서 수준 사용자 지정에서 사용할 수 있습니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#79](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#79)]
     [!code-csharp[Trin_VstcoreWordAutomation#79](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#79)]  
  
     다음 코드 예제는 VSTO 추가 기능에서 사용할 수 있습니다. 이 예제에서는 활성 문서를 사용합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#79](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#79)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#79](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#79)]  
  
2.  루프에서 <xref:Microsoft.Office.Interop.Word.Find.Found%2A> 속성을 사용하여 문서의 문자열 항목을 모두 검색하고 문자열을 찾을 때마다 정수 변수를 1씩 증분합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#80)]
     [!code-csharp[Trin_VstcoreWordAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#80)]  
  
3.  메시지 상자에는 문자열이 발견된 횟수가 표시됩니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#81](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#81)]
     [!code-csharp[Trin_VstcoreWordAutomation#81](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#81)]  
  
 다음 예제에서는 전체 메서드를 보여 줍니다.  
  
## <a name="document-level-customization-example"></a>문서 수준 사용자 지정 예제  
  
#### <a name="to-loop-through-items-in-a-document-level-customization"></a>문서 수준 사용자 지정에서 항목을 순환 검색하려면  
  
1.  다음 예제에서는 문서 수준 사용자 지정의 전체 코드를 보여 줍니다. 이 코드를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#78](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#78)]
     [!code-csharp[Trin_VstcoreWordAutomation#78](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#78)]  
  
## <a name="vsto-add-in-example"></a>VSTO 추가 기능 예제  
  
#### <a name="to-loop-through-items-in-an-vsto-add-in"></a>VSTO 추가 기능에서 항목을 순환 검색하려면  
  
1.  다음 예제에서는 VSTO 추가 기능의 전체 코드를 보여 줍니다. 이 코드를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#78](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#78)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#78](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#78)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: 프로그래밍 방식으로 검색 하 고 문서에서 텍스트 바꾸기](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)   
 [방법: 프로그래밍 방식으로 Word에서 검색 옵션 설정](../vsto/how-to-programmatically-set-search-options-in-word.md)   
 [방법: 프로그래밍 방식으로 정의 하 고 문서에서 범위 선택](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 검색 후 선택 영역 복원](../vsto/how-to-programmatically-restore-selections-after-searches.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  