---
title: "방법: 프로그래밍 방식으로 워크시트를 보호 | Microsoft Docs"
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
- protection, adding to worksheets
- documents [Office development in Visual Studio], document protection
- document protection, adding to worksheets
- worksheets, protecting
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 94293b90add3cbb4034278b8566ecfb1d138c09e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-protect-worksheets"></a>방법: 프로그래밍 방식으로 워크시트 보호
  Microsoft Office Excel의 보호 기능은 사용자 및 코드가 워크시트의 개체를 수정할 수 없도록 차단합니다. 기본적으로 보호를 설정하면 모든 셀이 잠깁니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 문서 수준 사용자 지정에서 Excel 디자이너를 사용하여 워크시트를 보호할 수 있습니다. 런타임에 프로그래밍 방식으로 모든 프로젝트 형식의 워크시트를 보호할 수도 있습니다.  
  
> [!NOTE]  
>  보호된 워크시트의 영역에는 Windows Forms 컨트롤을 추가할 수 없습니다.  
  
## <a name="using-the-designer"></a>디자이너 사용  
  
#### <a name="to-protect-a-worksheet-in-the-designer"></a>디자이너에서 워크시트를 보호하려면  
  
1.  에 **변경** 그룹는 **검토** 탭을 클릭 **시트 보호**합니다.  
  
     **시트 보호** 대화 상자가 나타납니다. 암호를 설정할 수 있으며, 필요에 따라 셀 서식 지정 또는 행 삽입과 같이 사용자가 워크시트에서 수행할 수 있는 특정 작업을 지정할 수 있습니다.  
  
 사용자가 보호된 워크시트에서 특정 범위를 편집하도록 허용할 수도 있습니다.  
  
#### <a name="to-allow-editing-in-specific-ranges"></a>특정 범위에서 편집을 허용하려면  
  
1.  에 **변경** 그룹는 **검토** 탭을 클릭 **범위 편집 허용 사용자**합니다.  
  
     **범위 편집 허용 사용자** 대화 상자가 나타납니다. 암호를 사용하여 잠금 해제되는 범위 및 암호 없이 범위를 편집할 수 있는 사용자를 지정할 수 있습니다.  
  
## <a name="using-code-at-run-time"></a>런타임에 코드 사용  
 다음 코드에서는 사용자로부터 받은 암호를 포함하는 getPasswordFromUser 변수를 사용하여 암호를 설정하고 정렬만 허용합니다.  
  
#### <a name="to-protect-a-worksheet-by-using-code-in-a-document-level-customization"></a>문서 수준 사용자 지정에서 코드를 사용하여 워크시트를 보호하려면  
  
1.  워크시트의 <xref:Microsoft.Office.Tools.Excel.Worksheet.Protect%2A> 메서드를 호출합니다. 이 예제에서는 `Sheet1`이라는 워크시트를 사용한다고 가정합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#27](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#27)]
     [!code-vb[Trin_VstcoreExcelAutomation#27](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#27)]  
  
#### <a name="to-protect-a-worksheet-by-using-code-in-a-vsto-add-in"></a>VSTO 추가 기능에서 코드를 사용하여 워크시트를 보호하려면  
  
1.  활성 워크시트의 <xref:Microsoft.Office.Interop.Excel._Worksheet.Protect%2A> 메서드를 호출합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#17](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#17)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#17](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#17)]  
  
## <a name="see-also"></a>참고 항목  
 [워크시트 작업](../vsto/working-with-worksheets.md)   
 [방법: 프로그래밍 방식으로 워크시트에서 보호 제거](../vsto/how-to-programmatically-remove-protection-from-worksheets.md)   
 [방법: 프로그래밍 방식으로 통합 문서 보호](../vsto/how-to-programmatically-protect-workbooks.md)   
 [방법: 프로그래밍 방식으로 워크시트 숨기기](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)   
 [워크시트 호스트 항목](../vsto/worksheet-host-item.md)   
 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  