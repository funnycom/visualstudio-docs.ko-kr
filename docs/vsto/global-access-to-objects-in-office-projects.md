---
title: "Office 프로젝트의 개체에 전역 액세스 | Microsoft Docs"
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
- ThisDocument_Shutdown
- ThisDocument_Startup
- Globals class, object global access
- worksheets [Office development in Visual Studio], global access
- documents [Office development in Visual Studio], global access
- event handlers [Office development in Visual Studio]
- ThisWorkbook_Startup
- application-level addins [Office development in Visual Studio]
- addins [Office development in Visual Studio], events
- workbooks [Office development in Visual Studio], global access
- ThisWorkbook_Shutdown
- document-level customizations [Office development in Visual Studio]
- Startup event
- Shutdown event
- projects [Office development in Visual Studio], global access
- Office documents [Office development in Visual Studio, global access
- ThisAddin_Startup
- events [Office development in Visual Studio]
- ThisAddIn_Shutdown
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: bdfc9b62e6dc94560693c072526e1f2989ddec15
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="global-access-to-objects-in-office-projects"></a>Office 프로젝트의 개체에 전역 액세스
  Office 프로젝트를 만들면 Visual Studio에서 `Globals` 라는 클래스를 프로젝트에 자동으로 생성합니다. `Globals` 클래스를 사용하여 프로젝트의 모든 코드에서 런타임에 여러 프로젝트 항목에 액세스할 수 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="how-to-use-the-globals-class"></a>Globals 클래스를 사용하는 방법  
 `Globals` 는 프로젝트의 특정 항목에 대한 참조를 유지하는 정적 클래스입니다. `Globals` 클래스를 사용하면 런타임에 프로젝트의 코드에서 다음과 같은 항목에 액세스할 수 있습니다.  
  
-   Excel 통합 문서 또는 서식 파일 프로젝트의 `ThisWorkbook` 및 `Sheet`*n* 클래스. 사용 하 여 이러한 개체에 액세스할 수 있습니다는 `Globals.ThisWorkbook` 및 `Sheet`  *n*  속성입니다.  
  
-   Word 문서 또는 서식 파일 프로젝트의 `ThisDocument` 클래스. `Globals.ThisDocument` 속성을 사용하여 이 개체에 액세스할 수 있습니다.  
  
-   VSTO 추가 기능 프로젝트의 `ThisAddIn` 클래스입니다. `Globals.ThisAddIn` 속성을 사용하여 이 개체에 액세스할 수 있습니다.  
  
-   리본 디자이너를 사용하여 사용자 지정한 프로젝트의 모든 리본. `Globals.Ribbons` 속성을 사용하여 리본에 액세스할 수 있습니다. 자세한 내용은 [Accessing the Ribbon at Run Time](../vsto/accessing-the-ribbon-at-run-time.md)을 참조하십시오.  
  
-   Outlook VSTO 추가 기능 프로젝트의 모든 Outlook 양식 영역입니다. `Globals.FormRegions` 속성을 사용하여 양식 영역에 액세스할 수 있습니다. 자세한 내용은 [Accessing a Form Region at Run Time](../vsto/accessing-a-form-region-at-run-time.md)을 참조하세요.  
  
-   리본 컨트롤을 만들고 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 또는 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]를 대상으로 하는 프로젝트에서 런타임에 호스트 항목을 만들 수 있는 팩터리 개체. `Globals.Factory` 속성을 사용하여 이 개체에 액세스할 수 있습니다. 이 개체는 다음 인터페이스 중 하나를 구현하는 클래스의 인스턴스입니다.  
  
    -   <xref:Microsoft.Office.Tools.Factory>  
  
    -   <xref:Microsoft.Office.Tools.Excel.Factory>  
  
    -   <xref:Microsoft.Office.Tools.Outlook.Factory>  
  
    -   <xref:Microsoft.Office.Tools.Word.Factory>  
  
 예를 들어 사용자가 Excel에 대한 문서 수준 프로젝트의 작업창에서 단추를 클릭하면 `Globals.Sheet1` 속성을 사용하여 <xref:Microsoft.Office.Tools.Excel.NamedRange> 의 `Sheet1` 컨트롤에 텍스트를 삽입할 수 있습니다.  
  
 [!code-vb[Trin_VstcoreProgramming#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/Sheet1.vb#1)]
 [!code-csharp[Trin_VstcoreProgramming#1](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/Sheet1.cs#1)]  
  
## <a name="initializing-the-globals-class"></a>Globals 클래스 초기화  
 문서 또는 VSTO 추가 기능이 완전히 초기화되기 전에 `Globals` 클래스를 사용하려고 시도하는 코드는 런타임 예외를 throw할 수 있습니다. 예를 들어 `Globals` 클래스는 선언된 개체가 인스턴스화되기 전에 모든 호스트 항목에 대한 참조로 초기화되지 않을 수 있으므로 클래스 수준 변수를 선언할 때 `Globals` 를 사용하면 실패할 수 있습니다.  
  
> [!NOTE]  
>  `Globals` 클래스는 디자인 타임에 초기화되지 않지만 컨트롤 인스턴스는 디자이너에서 만듭니다. 즉, 사용자 정의 컨트롤 클래스 내부에서 `Globals` 클래스의 속성을 사용하는 사용자 정의 컨트롤을 만드는 경우 반환된 개체를 사용하기 전에 속성에서 **null** 을 반환하는지 여부를 확인해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Accessing the Ribbon at Run Time](../vsto/accessing-the-ribbon-at-run-time.md)   
 [런타임에 양식 영역 액세스](../vsto/accessing-a-form-region-at-run-time.md)   
 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)   
 [문서 호스트 항목](../vsto/document-host-item.md)   
 [통합 문서 호스트 항목](../vsto/workbook-host-item.md)   
 [워크시트 호스트 항목](../vsto/worksheet-host-item.md)   
 [Writing Code in Office Solutions](../vsto/writing-code-in-office-solutions.md)  
  
  