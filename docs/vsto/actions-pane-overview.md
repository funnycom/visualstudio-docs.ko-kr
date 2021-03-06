---
title: "작업 창 개요 | Microsoft Docs"
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
- actions panes [Office development in Visual Studio], about actions panes
- actions panes [Office development in Visual Studio]
- smart documents [Office development in Visual Studio]
- user controls [Office development in Visual Studio], actions panes
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 0e3fb356c00b3e9943ba8aff696283d4c5339e18
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="actions-pane-overview"></a>작업 창 개요
  작업창은 사용자 지정 가능한 **문서 동작** 특정 Microsoft Office Word 문서 또는 Microsoft Office Excel 통합 문서에 연결 된 작업창입니다. 다른 기본 제공 작업창과 함께 Office 작업창 내과 같은 호스트의 **XML 원본은** Excel의 작업 창 또는 **스타일 및 서식** Word의 작업창입니다. Windows Forms 컨트롤 또는 WPF 컨트롤을 사용하여 작업 창 사용자 인터페이스를 디자인할 수 있습니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Word 또는 Excel에 대한 문서 수준 사용자 지정에만 작업 창을 만들 수 있습니다. VSTO 추가 기능에서는 작업 창을 만들 수 없습니다. 자세한 내용은 [Features Available by Office Application and Project Type](../vsto/features-available-by-office-application-and-project-type.md)을 참조하세요.  
  
> [!NOTE]  
>  작업 창은 사용자 지정 작업창과 다릅니다. 사용자 지정 작업창은 특정 문서가 아니라 응용 프로그램과 연결됩니다. VSTO 추가 기능에서 일부 Microsoft Office 응용 프로그램에 대한 사용자 지정 작업창을 만들 수 있습니다. 자세한 내용은 참조 [사용자 지정 작업창](../vsto/custom-task-panes.md)합니다.  
  
 ![비디오에 링크](../vsto/media/playvideo.gif "비디오에 링크") 관련된 동영상 데모를 참조 하십시오. [어떻게 수행 할까요 사용 하 여 WPF 컨트롤 내부의 Excel 작업 창?](http://go.microsoft.com/fwlink/?LinkId=132763)합니다.  
  
## <a name="displaying-the-actions-pane"></a>작업 창 표시  
 작업 창은 <xref:Microsoft.Office.Tools.ActionsPane> 클래스로 표현됩니다. 문서 수준 프로젝트를 만드는 경우 프로젝트에서 `ThisWorkbook`(Excel용) 또는 `ThisDocument`(Word용) 클래스의 `ActionsPane` 필드를 통해 코드에서 이 클래스의 인스턴스를 사용할 수 있습니다. 작업 창을 표시하려면 `ActionsPane` 필드의 <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> 속성에 Windows Forms 컨트롤을 추가합니다. 다음 코드 예제에서는 `actions`라는 컨트롤을 작업 창에 추가합니다.  
  
 [!code-csharp[Trin_VstcoreActionsPaneWord#7](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#7)]
 [!code-vb[Trin_VstcoreActionsPaneWord#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#7)]  
  
 작업 창에 컨트롤을 명시적으로 추가하는 즉시 런타임에 표시됩니다. 작업 창이 표시되면 사용자 작업에 대한 응답으로 컨트롤을 동적으로 추가하거나 제거할 수 있습니다. 일반적으로 사용자가 처음 문서를 열 때 작업 창이 표시되도록 `ThisDocument` 또는 `ThisWorkbook`의 `Startup` 이벤트 처리기에 작업 창을 표시하는 코드를 추가합니다. 그러나 문서의 사용자 작업에 대한 응답으로만 작업 창을 표시하는 것이 좋습니다. 예를 들어 문서에서 컨트롤의 `Click` 이벤트에 코드를 추가할 수 있습니다.  
  
### <a name="adding-multiple-controls-to-the-actions-pane"></a>작업 창에 여러 컨트롤 추가  
 작업 창에 여러 컨트롤을 추가하는 경우 대체로 사용자 정의 컨트롤에 컨트롤을 그룹화한 다음 사용자 정의 컨트롤을 <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> 속성에 추가해야 합니다. 이 프로세스에는 다음 단계가 포함됩니다.  
  
1.  추가 하 여 작업 창의 사용자 인터페이스 (UI)을 만듭니다는 **작업 창 컨트롤** 또는 **사용자 정의 컨트롤** 항목을 프로젝트입니다. 두 항목에는 모두 사용자 지정 Windows Forms <xref:System.Windows.Forms.UserControl> 클래스가 포함되어 있습니다. **작업 창 컨트롤** 및 **사용자 정의 컨트롤** 항목은 동일 하며, 유일한 차이점은 이름 뿐입니다.  
  
2.  디자이너를 사용하여 또는 코드를 작성하여 <xref:System.Windows.Forms.UserControl>에 Windows Forms 컨트롤을 추가합니다.  
  
    > [!NOTE]  
    >  Windows Forms <xref:System.Windows.Forms.UserControl>에 WPF <xref:System.Windows.Controls.UserControl>을 추가하여 작업 창에 WPF 컨트롤을 추가할 수도 있습니다. 자세한 내용은 참조 [Office 솔루션에서 WPF 컨트롤을 사용 하 여](../vsto/using-wpf-controls-in-office-solutions.md)합니다.  
  
3.  프로젝트에서 `ThisWorkbook`(Excel용) 또는 `ThisDocument`(Word용) 클래스의 `ActionsPane` 필드에 포함된 컨트롤에 사용자 지정 사용자 정의 컨트롤의 인스턴스를 추가합니다.  
  
 이 과정을 자세히 보여 주는 예제를 보려면 [하는 방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)합니다.  
  
## <a name="hiding-the-actions-pane"></a>작업 창 숨기기  
 <xref:Microsoft.Office.Tools.ActionsPane> 클래스에는 <xref:Microsoft.Office.Tools.ActionsPane.Hide%2A> 메서드 및 <xref:Microsoft.Office.Tools.ActionsPane.Visible%2A> 속성이 있지만 <xref:Microsoft.Office.Tools.ActionsPane> 클래스 자체의 멤버를 사용하여 사용자 인터페이스에서 작업 창을 제거할 수 없습니다. 호출 된 <xref:Microsoft.Office.Tools.ActionsPane.Hide%2A> 메서드 또는 설정은 <xref:Microsoft.Office.Tools.ActionsPane.Visible%2A> 속성을 **false** 작업 창의 컨트롤만 숨겨집니다 작업창은 숨겨지지 않습니다.  
  
 솔루션에서 작업창을 숨기려면 다음 여러 가지 옵션이 있습니다.  
  
-   Word의 경우 설정는 <xref:Microsoft.Office.Interop.Word.TaskPane.Visible%2A> 속성의는 <xref:Microsoft.Office.Interop.Word.TaskPane> 에 문서 동작 작업 창을 나타내는 개체 **false**합니다. 다음 코드 예제는 프로젝트의 `ThisDocument` 클래스에서 실행해야 합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#34](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#34)]
     [!code-vb[Trin_VstcoreActionsPaneWord#34](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#34)]  
  
-   Excel에 대 한 설정의 <xref:Microsoft.Office.Interop.Excel._Application.DisplayDocumentActionTaskPane%2A> 의 속성은 <xref:Microsoft.Office.Tools.Excel.Workbook.Application%2A> 개체를 **false**합니다. 다음 코드 예제는 프로젝트의 `ThisWorkbook` 클래스에서 실행해야 합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneExcel#11](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ThisWorkbook.cs#11)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ThisWorkbook.vb#11)]  
  
-   Word 또는 Excel 설정할 수도 있습니다는 <xref:Microsoft.Office.Core.CommandBar.Visible%2A> 작업창을 나타내는 명령 모음의 속성 **false**합니다. 다음 코드 예제는 프로젝트의 `ThisDocument` 또는 `ThisWorkbook` 클래스에서 실행해야 합니다.  
  
     [!code-csharp[Trin_VstcoreActionsPaneExcel#9](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ThisWorkbook.cs#9)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#9](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ThisWorkbook.vb#9)]  
  
### <a name="clearing-the-actions-pane-when-the-document-is-opened"></a>문서를 열 때 작업 창 지우기  
 작업 창이 표시되는 동안 사용자가 문서를 저장하는 경우 작업 창에 컨트롤이 포함되어 있는지 여부에 관계없이 문서를 열 때마다 작업 창이 표시됩니다. 표시되는 시기를 제어하려는 경우 `ThisDocument` 또는 `ThisWorkbook`의 `Startup` 이벤트 처리기에서 `ActionsPane` 필드의 <xref:Microsoft.Office.Tools.ActionsPane.Clear%2A> 메서드를 호출하여 문서를 열 때 작업 창이 표시되지 않도록 합니다.  
  
### <a name="determining-when-the-actions-pane-is-closed"></a>작업 창이 닫히는 시기 결정  
 작업 창이 닫힐 때 발생하는 이벤트는 없습니다. <xref:Microsoft.Office.Tools.ActionsPane> 클래스에 <xref:Microsoft.Office.Tools.ActionsPane.VisibleChanged> 이벤트가 있긴 하지만 이 이벤트는 최종 사용자가 작업 창을 닫을 때 발생하지 않습니다. 작업 창의 컨트롤은 호출 하 여 숨겨진 경우이 이벤트는 발생 하는 대신,는 <xref:Microsoft.Office.Tools.ActionsPane.Hide%2A> 메서드 또는 설정 하 여는 <xref:Microsoft.Office.Tools.ActionsPane.Visible%2A> 속성을 **false**합니다.  
  
 최종 사용자가 작업 창을 닫는 경우 응용 프로그램의 UI(사용자 인터페이스)에서 다음 절차 중 하나를 수행하여 다시 표시할 수 있습니다.  
  
##### <a name="to-display-the-actions-pane-by-using-the-ui-of-word-or-excel"></a>Word 또는 Excel의 UI를 사용하여 작업 창을 표시하려면  
  
1.  리본 메뉴에서 클릭 된 **보기** 탭 합니다.  
  
2.  에 **표시/숨기기** 그룹에서 클릭는 **문서 동작** 토글 단추입니다.  
  
## <a name="programming-actions-pane-events"></a>작업 창 이벤트 프로그래밍  
 작업 창에 여러 개의 사용자 정의 컨트롤을 추가한 다음 사용자 정의 컨트롤을 표시하거나 숨겨 문서의 이벤트에 응답하는 코드를 작성할 수 있습니다. 문서에 XML 스키마 요소를 매핑하는 경우 삽입 지점이 XML 요소 중 하나의 내부에 있을 때마다 작업 창에 특정 사용자 정의 컨트롤을 표시할 수 있습니다. 자세한 내용은 참조 [하는 방법: Visual Studio 내부의 Word 문서에 스키마 맵](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md) 및 [하는 방법: Visual Studio 내의 워크시트에 스키마 맵](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)합니다.  
  
 호스트 컨트롤, 응용 프로그램 또는 문서 이벤트를 포함하여 개체의 이벤트에 응답하는 코드를 작성할 수도 있습니다. 자세한 내용은 참조 [연습: NamedRange 컨트롤의 이벤트 프로그래밍](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)합니다.  
  
## <a name="binding-data-to-controls-on-the-actions-pane"></a>작업 창의 컨트롤에 데이터 바인딩  
 작업 창의 컨트롤은 Windows Forms의 컨트롤과 동일한 데이터 바인딩 기능을 가지고 있습니다. 데이터 집합, 형식화된 데이터 집합 및 XML과 같은 데이터 소스에 컨트롤을 바인딩할 수 있습니다. 자세한 내용은 [Data Binding and Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms)을 참조하세요.  
  
 작업 창의 컨트롤과 문서의 컨트롤을 동일한 데이터 집합에 바인딩할 수 있습니다. 예를 들어 작업 창의 컨트롤과 워크시트의 컨트롤 간에 마스터/세부 관계를 만들 수 있습니다. 자세한 내용은 참조 [연습: Excel 작업 창의 컨트롤에 데이터 바인딩](../vsto/walkthrough-binding-data-to-controls-on-an-excel-actions-pane.md)합니다.  
  
## <a name="validating-data-in-actions-pane-controls"></a>작업 창 컨트롤의 데이터 유효성 검사  
 작업 창에 있는 컨트롤의 <xref:System.Windows.Forms.Control.Validating> 이벤트 처리기에 메시지 상자를 표시하는 경우 포커스가 두 번째로 컨트롤에서 메시지 상자로 이동할 때 이벤트가 발생할 수도 있습니다. 이 문제를 방지하려면 <xref:System.Windows.Forms.ErrorProvider> 컨트롤을 사용하여 유효성 검사 오류 메시지를 표시합니다.  
  
## <a name="user-control-stacking-order"></a>사용자 정의 컨트롤 스택 순서  
 여러 개의 사용자 정의 컨트롤을 사용하는 경우 가로 또는 세로로 도킹하는지에 관계없이 작업 창에서 사용자 정의 컨트롤을 제대로 쌓는 코드를 작성할 수 있습니다. <xref:Microsoft.Office.Tools.ActionsPane.StackOrder%2A> 속성의 <xref:Microsoft.Office.Tools.StackStyle> 열거형을 사용하여 작업 창의 사용자 정의 컨트롤 스택 순서를 설정할 수 있습니다. 자세한 내용은 참조 [하는 방법: 작업 창에서 컨트롤 레이아웃 관리](../vsto/how-to-manage-control-layout-on-actions-panes.md)  
  
 <xref:Microsoft.Office.Tools.ActionsPane.StackOrder%2A> 속성은 다음 <xref:Microsoft.Office.Tools.StackStyle> 열거형 값을 사용할 수 있습니다.  
  
|스택 스타일|정의|  
|--------------------|----------------|  
|FromBottom|작업 창의 아래쪽에서 쌓습니다.|  
|FromLeft|작업 창의 왼쪽에서 쌓습니다.|  
|FromRight|작업 창의 오른쪽에서 쌓습니다.|  
|FromTop|작업 창의 위쪽에서 쌓습니다.|  
|없음|스택 순서가 정의되지 않습니다. 개발자가 순서를 제어합니다.|  
  
 다음 코드에서는 <xref:Microsoft.Office.Tools.ActionsPane.StackOrder%2A> 속성을 설정하여 작업 창의 위쪽에서 사용자 정의 컨트롤을 쌓습니다.  
  
 [!code-csharp[Trin_VstcoreActionsPaneExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ThisWorkbook.cs#10)]
 [!code-vb[Trin_VstcoreActionsPaneExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ThisWorkbook.vb#10)]  
  
## <a name="anchoring-controls"></a>컨트롤 고정  
 사용자가 런타임에 작업 창의 크기를 조정하는 경우 작업 창과 함께 컨트롤의 크기가 조정될 수 있습니다. Windows Forms 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 사용하여 작업 창에 컨트롤을 고정할 수 있습니다. 동일한 방식으로 사용자 정의 컨트롤에 Windows Forms 컨트롤을 고정할 수도 있습니다. 자세한 내용은 참조 [하는 방법: Windows Forms에서 컨트롤 고정](/dotnet/framework/winforms/controls/how-to-anchor-controls-on-windows-forms)합니다.  
  
## <a name="resizing-the-actions-pane"></a>작업 창 크기 조정  
 <xref:Microsoft.Office.Tools.ActionsPane>이 작업창에 포함되어 있으므로 <xref:Microsoft.Office.Tools.ActionsPane>의 크기를 직접 변경할 수는 없습니다. 그러나 작업창을 나타내는 <xref:Microsoft.Office.Core.CommandBar>의 <xref:Microsoft.Office.Core.CommandBar.Width%2A> 속성을 설정하여 프로그래밍 방식으로 작업창의 너비를 변경할 수 있습니다. 가로로 도킹되어 있거나 부동 창인 경우 작업창의 높이를 변경할 수 있습니다.  
  
 사용자가 요구 사항에 가장 적합한 작업창 크기를 선택할 수 있어야 하므로 일반적으로 프로그래밍 방식으로 작업창의 크기를 조정하지 않는 것이 좋습니다. 그러나 작업창의 너비를 조정해야 하는 경우 다음 코드를 사용하여 이 작업을 수행할 수 있습니다.  
  
 [!code-csharp[Trin_VstcoreActionsPaneWord#102](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#102)]
 [!code-vb[Trin_VstcoreActionsPaneWord#102](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#102)]  
  
## <a name="repositioning-the-actions-pane"></a>작업 창 위치 변경  
 <xref:Microsoft.Office.Tools.ActionsPane>은 작업창에 포함되어 있으므로 직접 위치를 변경할 수 없습니다. 그러나 작업창을 나타내는 <xref:Microsoft.Office.Core.CommandBar>의 <xref:Microsoft.Office.Core.CommandBar.Position%2A> 속성을 설정하여 프로그래밍 방식으로 작업창을 이동할 수 있습니다.  
  
 사용자가 화면에서 요구 사항에 가장 적합한 작업창 위치를 선택할 수 있어야 하므로 일반적으로 프로그래밍 방식으로 작업창의 위치를 변경하지 않는 것이 좋습니다. 그러나 작업창을 특정 위치로 이동해야 하는 경우 다음 코드를 사용하여 이 작업을 수행할 수 있습니다.  
  
 [!code-csharp[Trin_VstcoreActionsPaneWord#100](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#100)]
 [!code-vb[Trin_VstcoreActionsPaneWord#100](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#100)]  
  
> [!NOTE]  
>  최종 사용자는 언제든지 작업창의 위치를 수동으로 변경할 수 있습니다. 프로그래밍 방식으로 지정한 위치에 작업창이 도킹된 상태로 유지되도록 하는 방법은 없습니다. 그러나 방향 변경을 검사하고 작업 창의 컨트롤이 올바른 방향으로 쌓이는지 확인할 수 있습니다. 자세한 내용은 참조 [하는 방법: 작업 창에서 컨트롤 레이아웃 관리](../vsto/how-to-manage-control-layout-on-actions-panes.md)합니다.  
  
 <xref:Microsoft.Office.Tools.ActionsPane> 개체는 작업창에 포함되어 있으므로 <xref:Microsoft.Office.Tools.ActionsPane>의 <xref:Microsoft.Office.Tools.ActionsPane.Top%2A> 및 <xref:Microsoft.Office.Tools.ActionsPane.Left%2A> 속성을 설정해도 해당 위치가 변경되지 않습니다.  
  
 작업창이 도킹되지 않은 경우 작업창을 나타내는 <xref:Microsoft.Office.Core.CommandBar>의 <xref:Microsoft.Office.Core.CommandBar.Top%2A> 및 <xref:Microsoft.Office.Core.CommandBar.Left%2A> 속성을 설정할 수 있습니다. 다음 코드는 도킹되지 않은 작업창을 문서의 왼쪽 위로 이동합니다.  
  
 [!code-csharp[Trin_VstcoreActionsPaneWord#101](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#101)]
 [!code-vb[Trin_VstcoreActionsPaneWord#101](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#101)]  
  
## <a name="see-also"></a>참고 항목  
 [Office 솔루션에서 WPF 컨트롤 사용](../vsto/using-wpf-controls-in-office-solutions.md)   
 [Office UI 사용자 지정](../vsto/office-ui-customization.md)   
 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)   
 [방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [연습: 작업 창에서 문서로 텍스트 삽입](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)   
 [연습: Word 작업 창의 컨트롤에 데이터 바인딩](../vsto/walkthrough-binding-data-to-controls-on-a-word-actions-pane.md)   
 [연습: Excel 작업 창의 컨트롤에 데이터 바인딩](../vsto/walkthrough-binding-data-to-controls-on-an-excel-actions-pane.md)   
 [방법: 작업 창에서 컨트롤 레이아웃 관리](../vsto/how-to-manage-control-layout-on-actions-panes.md)   
 [연습: 작업창에서 문서로 텍스트 삽입](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)  
  
  