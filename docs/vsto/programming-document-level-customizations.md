---
title: "문서 수준 사용자 지정 프로그래밍 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Sheet3
- thisWorkbook
- thisDocument
- Sheet1
- Sheet2
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ThisDocument class
- Sheet3 class
- ThisWorkbook class
- writing code for Office solutions
- programming [Office development in Visual Studio], document-level customizations
- Sheet1 class
- Office applications [Office development in Visual Studio], document-level customizations
- Sheet2 class
- document-level customizations [Office development in Visual Studio], programming
- application development [Office development in Visual Studio], document-level customizations
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: a614173fc33547c3512c031b7e0bd8a5575e7cb2
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="programming-document-level-customizations"></a>문서 수준 사용자 지정 프로그래밍
  문서 수준 사용자 지정을 사용하여 Microsoft Office Word 또는 Microsoft Office Excel을 확장한 경우 다음 작업을 수행할 수 있습니다.  
  
-   개체 모델을 사용하여 응용 프로그램을 자동화합니다.  
  
-   문서 화면에 컨트롤을 추가합니다.  
  
-   사용자 지정 어셈블리에서 문서에 VBA(Visual Basic for Applications) 코드를 호출합니다.  
  
-   VBA에서 사용자 지정 어셈블리에 코드를 호출합니다.  
  
-   Microsoft Office가 설치되지 않은 서버에서 문서의 특정 측면을 관리합니다.  
  
-   응용 프로그램의 UI(사용자 인터페이스)를 사용자 지정합니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 문서 수준 프로젝트에서 코드 작성의 일부 측면은 Visual Studio의 다른 프로젝트 유형과 다릅니다. 이러한 차이점 대부분은 Office 개체 모델이 관리 코드에 표시되는 방식에 기인합니다. 자세한 내용은 [Writing Code in Office Solutions](../vsto/writing-code-in-office-solutions.md)을 참조하세요.  
  
 Visual Studio에서 Office 개발 도구를 사용 하 여 만들 수 있는 문서 수준 사용자 지정 및 다른 유형의 솔루션에 대 한 일반 정보를 참조 하십시오. [Office 솔루션 개발 개요 &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
## <a name="using-the-generated-classes-in-document-level-projects"></a>문서 수준 프로젝트에서 생성된 클래스 사용  
 문서 수준 프로젝트를 만들 때 Visual Studio에서 프로젝트에서 코드 작성을 시작하기 위해 사용할 수 있는 클래스를 자동으로 생성합니다. Visual Studio에서는 다양한 Word 및 Excel용 클래스를 생성합니다.  
  
-   Word용 문서 수준 프로젝트에서는 `ThisDocument` 클래스가 기본적으로 호출됩니다.  
  
-   Excel용 문서 수준 프로젝트에는 통합 문서에 대해 하나, 각 워크시트에 대해 하나씩 생성된 클래스가 여러 개 있습니다. 기본적으로 이러한 클래스에는 다음 이름이 있습니다.  
  
    -   `ThisWorkbook`  
  
    -   `Sheet1`  
  
    -   `Sheet2`  
  
    -   `Sheet3`  
  
 생성된 클래스에는 문서가 열리거나 닫힐 때 호출되는 이벤트 처리기가 포함됩니다. 문서가 열릴 때 코드를 실행하려면 `Startup` 이벤트 처리기에 코드를 추가합니다. 문서가 닫히기 직전에 코드를 실행하려면 `Shutdown` 이벤트 처리기에 코드를 추가합니다. 자세한 내용은 [Events in Office Projects](../vsto/events-in-office-projects.md)을 참조하세요.  
  
### <a name="understanding-the-design-of-the-generated-classes"></a>생성된 클래스 디자인 이해  
 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 또는 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]를 대상으로 하는 프로젝트에서 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 의 호스트 항목 형식은 인터페이스이므로 이를 통해 생성된 클래스에서 구현을 파생할 수 없습니다. 대신, 생성된 클래스는 다음 기본 클래스에서 대부분의 멤버를 파생합니다.  
  
-   `ThisDocument`: <xref:Microsoft.Office.Tools.Word.DocumentBase>에서 파생됩니다.  
  
-   `ThisWorkbook`: <xref:Microsoft.Office.Tools.Excel.WorkbookBase>에서 파생됩니다.  
  
-   `Sheet` *n*: <xref:Microsoft.Office.Tools.Excel.WorksheetBase>에서 파생됩니다.  
  
 이러한 기본 클래스는 해당 멤버에 대한 모든 호출을 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에 있는 해당 호스트 항목 인터페이스의 내부 구현으로 리디렉션합니다. 예를 들어 <xref:Microsoft.Office.Tools.Word.DocumentBase.Protect%2A> 클래스의 `ThisDocument` 메서드를 호출하는 경우 <xref:Microsoft.Office.Tools.Word.DocumentBase> 클래스는 이 호출을 <xref:Microsoft.Office.Tools.Word.Document> 에 있는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]인터페이스의 내부 구현으로 리디렉션합니다.  
  
## <a name="accessing-the-object-model-of-the-host-application"></a>호스트 응용 프로그램의 개체 모델 액세스  
 호스트 응용 프로그램의 개체 모델에 액세스하려면 프로젝트에서 생성된 클래스의 멤버를 사용합니다. 이러한 각 클래스는 Excel 또는 Word의 개체 모델에 있는 개체에 해당하며 대부분의 동일한 속성, 메서드 및 이벤트를 포함합니다. 예를 들어 Word 문서 수준 프로젝트의 `ThisDocument` 클래스는 Word 개체 모델의 <xref:Microsoft.Office.Interop.Word.Document> 개체와 동일한 대부분의 멤버를 제공합니다.  
  
 다음 코드 예제에서는 Word 개체 모델을 사용하여 Word 문서 수준 사용자 지정의 일부인 문서를 저장하는 방법을 보여 줍니다. 이 예제는 `ThisDocument` 클래스에서 실행하기 위한 것입니다.  
  
```vb  
Me.Save()  
```  
  
```csharp  
this.Save();  
```  
  
 `ThisDocument` 클래스 외부에서 동일한 작업을 수행하려면 `Globals` 개체를 사용하여 `ThisDocument` 클래스에 액세스합니다. 예를 들어 작업 창 UI에 **저장** 단추를 포함하려는 경우 작업 창 코드 파일에 이 코드를 추가할 수 있습니다.  
  
```vb  
Globals.ThisDocument.Save()  
```  
  
```csharp  
Globals.ThisDocument.Save();  
```  
  
 `ThisDocument` 클래스는 <xref:Microsoft.Office.Tools.Word.Document> 호스트 항목에서 대부분의 멤버를 가져오므로 이 코드에 호출된 `Save` 메서드는 실제로 <xref:Microsoft.Office.Tools.Word.Document.Save%2A> 호스트 항목의 <xref:Microsoft.Office.Tools.Word.Document> 메서드입니다. 이 메서드는 Word 개체 모델의 <xref:Microsoft.Office.Interop.Word._Document.Save%2A> 개체의 <xref:Microsoft.Office.Interop.Word.Document> 메서드에 해당합니다.  
  
 Word 및 Excel의 개체 모델 사용에 대한 자세한 내용은 [Word Object Model Overview](../vsto/word-object-model-overview.md) 및 [Excel Object Model Overview](../vsto/excel-object-model-overview.md)를 참조하세요.  
  
 에 대 한 자세한 내용은 `Globals` 개체, 참조 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)합니다.  
  
## <a name="adding-controls-to-documents"></a>문서에 컨트롤 추가  
 문서의 UI를 사용자 지정하려면 Windows Forms 컨트롤 또는 *호스트 컨트롤* 을 문서 화면에 추가하면 됩니다. 다양한 컨트롤 집합을 결합하고 코드를 작성하여 컨트롤을 데이터에 바인딩하고, 사용자로부터 정보를 수집하고, 사용자 작업에 응답할 수 있습니다.  
  
 호스트 컨트롤은 Word 및 Excel 개체 모델의 일부 개체를 확장한 클래스입니다. 예를 들어 <xref:Microsoft.Office.Tools.Excel.ListObject> 호스트 컨트롤은 Excel의 <xref:Microsoft.Office.Interop.Excel.ListObject> 기능을 모두 제공합니다. 그러나 <xref:Microsoft.Office.Tools.Excel.ListObject> 호스트 컨트롤에는 추가 이벤트 및 데이터 바인딩 기능도 있습니다.  
  
 자세한 내용은 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md) 및 [Windows Forms Controls on Office Documents Overview](../vsto/windows-forms-controls-on-office-documents-overview.md)를 참조하세요.  
  
## <a name="combining-vba-and-document-level-customizations"></a>VBA 및 문서 수준 사용자 지정 결합  
 문서 수준 사용자 지정의 일부인 문서에서 VBA 코드를 사용할 수 있습니다. 사용자 지정 어셈블리에서 문서의 VBA 코드를 호출하거나, 문서의 VBA 코드에서 사용자 지정 어셈블리의 코드를 호출할 수 있도록 프로젝트를 구성할 수도 있습니다.  
  
 자세한 내용은 [Combining VBA and Document-Level Customizations](../vsto/combining-vba-and-document-level-customizations.md)을 참조하세요.  
  
## <a name="managing-documents-on-a-server"></a>서버에서 문서 관리  
 Microsoft Office Word 또는 Microsoft Office Excel이 설치되지 않은 서버에서 문서 수준 사용자 지정의 다양한 측면을 관리할 수 있습니다. 예를 들어 문서의 데이터 캐시에 있는 데이터를 액세스 및 수정할 수 있습니다. 또한 문서와 연결된 사용자 지정 어셈블리를 관리할 수도 있습니다. 예를 들어 프로그래밍 방식으로 문서에서 어셈블리를 제거하여 문서에서 더 이상 코드를 실행하지 못하게 하거나 프로그래밍 방식으로 문서에 어셈블리를 연결할 수 있습니다.  
  
 자세한 내용은 [ServerDocument 클래스를 사용하여 서버의 문서 관리](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)을 참조하십시오.  
  
## <a name="customizing-the-user-interface-of-microsoft-office-applications"></a>Microsoft Office 응용 프로그램의 사용자 인터페이스 사용자 지정  
 다음 방법으로 문서 수준 사용자 지정을 사용하여 Word 및 Excel의 UI를 사용자 지정할 수 있습니다.  
  
-   호스트 컨트롤 또는 Windows Forms 컨트롤을 문서 화면에 추가합니다.  
  
     자세한 내용은 [Automating Word by Using Extended Objects](../vsto/automating-word-by-using-extended-objects.md), [Automating Excel by Using Extended Objects](../vsto/automating-excel-by-using-extended-objects.md)및 [Windows Forms Controls on Office Documents Overview](../vsto/windows-forms-controls-on-office-documents-overview.md)을 참조하십시오.  
  
-   문서에 작업 창 추가  
  
     자세한 내용은 [Actions Pane Overview](../vsto/actions-pane-overview.md)을 참조하십시오.  
  
-   리본에 사용자 지정 탭을 추가합니다.  
  
     자세한 내용은 참조 [리본 개요](../vsto/ribbon-overview.md)합니다.  
  
-   리본의 기본 제공 탭에 사용자 지정 그룹을 추가합니다.  
  
     자세한 내용은 [How to: Customize a Built-in Tab](../vsto/how-to-customize-a-built-in-tab.md)을 참조하세요.  
  
 UI의 Microsoft Office 응용 프로그램 사용자 지정 하는 방법에 대 한 자세한 내용은 참조 [Office UI 사용자 지정](../vsto/office-ui-customization.md)합니다.  
  
## <a name="getting-extended-objects-from-native-office-objects-in-document-level-customizations"></a>문서 수준 사용자 지정의 네이티브 Office 개체에서 확장 개체 가져오기  
 많은 Office 이벤트용 이벤트 처리기에서는 이벤트를 발생시키는 통합 문서, 워크시트 또는 문서를 나타내는 네이티브 Office 개체를 수신합니다. 문서 수준 사용자 지정의 문서 또는 통합 문서에서 이벤트를 발생시킨 경우에만 일부 코드를 실행할 수도 있습니다. 예를 들어 Excel용 문서 수준 사용자 지정에서 사용자가 사용자 지정된 통합 문서의 워크시트 중 하나를 활성화할 때는 일부 코드가 실행되고, 동시에 열린 다른 일부 통합 문서의 워크시트를 활성화할 때는 코드가 실행되지 않도록 할 수 있습니다.  
  
 네이티브 Office 개체가 있을 때 개체가 문서 수준 사용자 지정의 *호스트 항목* 또는 *호스트 컨트롤* 로 확장되었는지 테스트할 수 있습니다. 호스트 항목 및 호스트 컨트롤은 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 에서 제공하는 형식으로, 기본적으로 Word 또는 Excel 개체 모델에 있는 개체( *네이티브 Office 개체*라고 함)에 기능을 추가합니다. 호스트 항목 및 호스트 컨트롤을 통칭하여 *확장 개체*라고도 합니다. 호스트 항목 및 호스트 컨트롤에 대한 자세한 내용은 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)를 참조하세요.  
  
## <a name="understanding-the-getvstoobject-and-hasvstoobject-methods"></a>GetVstoObject 및 HasVstoObject 메서드 이해  
 네이티브 Office 개체를 테스트 하려면 프로젝트에는 GetVstoObject 및 HasVstoObject 메서드를 사용 합니다.  
  
-   사용자 지정에서 네이티브 Office 개체에 확장된 개체가 있는지 여부를 확인 하려는 경우 HasVstoObject 메서드를 사용 합니다. 네이티브 Office 개체에 확장 개체가 있는 경우 이 메서드는 **true** 를 반환하고 그렇지 않은 경우 **false** 를 반환합니다.  
  
-   네이티브 Office 개체에 대 한 확장된 개체를 가져오려는 경우 GetVstoObject 메서드를 사용 합니다. 지정한 네이티브 Office 개체에 <xref:Microsoft.Office.Tools.Excel.ListObject>, <xref:Microsoft.Office.Tools.Excel.Workbook>, <xref:Microsoft.Office.Tools.Excel.Worksheet>또는 <xref:Microsoft.Office.Tools.Word.Document> 개체가 있는 경우 이 메서드는 해당 개체를 반환합니다. 그렇지 않으면 반환 GetVstoObject **null**합니다. GetVstoObject 메서드 반환 하는 예를 들어 한 <xref:Microsoft.Office.Tools.Word.Document> 경우 지정 된 <xref:Microsoft.Office.Interop.Word.Document> Word 문서 프로젝트의 문서에 대 한 기본 개체입니다.  
  
 문서 수준 프로젝트에서를 만들려면 새 GetVstoObject 메서드를 사용할 수 없습니다 <xref:Microsoft.Office.Tools.Excel.Workbook>, <xref:Microsoft.Office.Tools.Excel.Worksheet>, 또는 <xref:Microsoft.Office.Tools.Word.Document> 런타임에 호스트 항목입니다. 이 메서드는 디자인 타임에 프로젝트에서 생성된 기존 호스트 항목에 액세스할 때만 사용할 수 있습니다. 런타임에 새 호스트 항목을 만들려면 VSTO 추가 기능 프로젝트를 개발해야 합니다. 자세한 내용은 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md) 및 [런타임에 VSTO 추가 기능에서 Word 문서 및 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)를 참조하세요.  
  
## <a name="using-the-getvstoobject-and-hasvstoobject-methods"></a>GetVstoObject 및 HasVstoObject 메서드 사용  
 GetVstoObject 및 HasVstoObject 메서드를 호출 하려면 Globals.Factory.GetVstoObject 또는 Globals.Factory.HasVstoObject 메서드를 사용 하 고 네이티브 Word 또는 Excel 개체에 전달 (같은 <xref:Microsoft.Office.Interop.Word.Document> 또는 <xref:Microsoft.Office.Interop.Excel.Worksheet>)를 테스트 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)   
 [Combining VBA and Document-Level Customizations](../vsto/combining-vba-and-document-level-customizations.md)   
 [ServerDocument 클래스를 사용 하 여 서버의 문서 관리](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)   
 [Writing Code in Office Solutions](../vsto/writing-code-in-office-solutions.md)  
  
  