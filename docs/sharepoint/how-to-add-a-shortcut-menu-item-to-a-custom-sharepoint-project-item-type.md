---
title: "방법: 사용자 지정 SharePoint 프로젝트 항목 형식에 바로 가기 메뉴 항목을 추가 | Microsoft Docs"
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
- SharePoint project items, defining your own types
- project items [SharePoint development in Visual Studio], defining your own types
- SharePoint development in Visual Studio, defining new project item types
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: e30a04d06f74f905daeebc4236962e88c20540bd
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type"></a>방법: 사용자 지정 SharePoint 프로젝트 항목 형식에 바로 가기 메뉴 항목 추가
  사용자 지정 SharePoint 프로젝트 항목 형식을 정의한 경우에 프로젝트 항목에 바로 가기 메뉴 항목을 추가할 수 있습니다. 프로젝트 항목을 클릭할 때 메뉴 항목이 표시 **솔루션 탐색기**합니다.  
  
 다음 단계에서는 SharePoint 프로젝트 항목 형식 사용자 고유의 이미 정의한 가정 합니다. 자세한 내용은 참조 [하는 방법: SharePoint 프로젝트 항목 형식 정의](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)합니다.  
  
### <a name="to-add-a-shortcut-menu-item-to-a-custom-project-item-type"></a>사용자 지정 프로젝트 항목 형식에 바로 가기 메뉴 항목을 추가 하려면  
  
1.  에 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> 방식의 프로그램 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> 구현, 핸들은 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> 의 이벤트는 *projectItemTypeDefinition* 매개 변수입니다.  
  
2.  에 대 한 이벤트 처리기에서는 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> 이벤트를 새 추가 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> 개체는 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.ViewMenuItems%2A> 또는 <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.AddMenuItems%2A> 이벤트 인수 매개 변수 컬렉션입니다.  
  
3.  에 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem.Click> 새에 대 한 이벤트 처리기 <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> 개체, 사용자가 바로 가기 메뉴 항목을 선택할 때 실행 하려는 작업을 수행 합니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 사용자 지정 프로젝트 항목 형식에 상황에 맞는 메뉴 항목을 추가 하는 방법을 보여 줍니다. 프로젝트 항목에서 바로 가기 메뉴를 열 때 **솔루션 탐색기** 를 선택 하 고는 **출력 창에 메시지 쓰기** 에 메시지를 표시 하는 메뉴 항목을 Visual Studio는 **출력**  창.  
  
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#4](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemtypemenu.cs#4)]
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#4](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemtypemenu.vb#4)]  
  
 SharePoint 프로젝트 서비스를 사용 하 여 메시지를 작성 하는이 예제는 **출력** 창. 자세한 내용은 참조 [SharePoint 프로젝트 서비스를 사용 하 여](../sharepoint/using-the-sharepoint-project-service.md)합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제는 클래스 라이브러리 프로젝트를 다음 어셈블리에 대 한 참조로 필요합니다.  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-project-item"></a>프로젝트 항목 배포  
 다른 개발자가 프로젝트 항목을 사용할 수 있도록 프로젝트 템플릿이나 프로젝트 항목 템플릿을 만듭니다. 자세한 내용은 참조 [SharePoint 프로젝트 항목에 대 한 프로젝트 템플릿과 항목 템플릿 만들기](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)합니다.  
  
 프로젝트 항목을 배포 하려면 만들기를 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 어셈블리, 서식 파일 및 프로젝트 항목과 함께 배포 하려는 다른 파일에 대 한 패키지 (VSIX) 확장 합니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구에 대 한 확장명 배포](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: SharePoint 프로젝트 항목 형식 정의](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)   
 [방법: 사용자 지정 SharePoint 프로젝트 항목 형식에 속성 추가](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)   
 [사용자 지정 SharePoint 프로젝트 항목 형식 정의](../sharepoint/defining-custom-sharepoint-project-item-types.md)  
  
  