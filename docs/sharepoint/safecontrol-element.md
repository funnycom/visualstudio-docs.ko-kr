---
title: "SafeControl 요소 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SafeControl element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 7458120d7a130de96a1a271c83e5376fe94481f3
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="safecontrol-element"></a>SafeControl 요소
  ASPX 컨트롤 또는 SharePoint 사이트에서 모든 ASPX 페이지에 액세스 하려면 모든 사용자에 대 한 안전한 것으로 지정 하는 웹 파트를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
<SafeControl Assembly = "Name of assembly that contains the safe control"  
    IsSafe = "true/false"  
    IsSafeAgainstScript = "true/false"  
    Name = "Name of this safe control entry"  
    Namespace = "Namespace of the safe control"  
    TypeName = "Type of the safe control" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|**어셈블리**|선택적 **xs: string** 특성입니다.<br /><br /> ASPX 컨트롤 또는 웹 파트 정의 된 어셈블리의 이름입니다. 기본적으로이 특성 사용에서 **$SharePoint.Project.AssemblyFullName$** 어셈블리 이름에 대 한 대체 가능 매개 변수입니다. 자세한 내용은 참조 [대체 가능 매개 변수](../sharepoint/replaceable-parameters.md)합니다.|  
|**IsSafe**|선택적 **xs: boolean** 특성입니다.<br /><br /> ASPX 컨트롤 또는 웹 파트 안전 하 게 신뢰할 수 없는 사용자가 액세스할 수 있는지 여부를 지정 합니다.|  
|**IsSafeAgainstScript**|선택적 **xs: boolean** 특성입니다.<br /><br /> 신뢰할 수 없는 사용자가 볼 하거나 ASPX 컨트롤 또는 웹 파트의 속성을 편집할 수를 지정 합니다.|  
|**이름**|선택적 **xs: string** 특성입니다.<br /><br /> 컬렉션에서이 안전 컨트롤 항목의 이름입니다.|  
|**네임스페이스**|선택적 **xs: string** 특성입니다.<br /><br /> ASPX 컨트롤 또는 웹 파트의 네임 스페이스입니다.|  
|**TypeName**|선택적 **xs: string** 특성입니다.<br /><br /> ASPX 컨트롤 또는 웹 파트의 형식 이름입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[SafeControls](../sharepoint/safecontrols-element.md)|ASPX 컨트롤 및 모든 사용자는 SharePoint 사이트에서 ASPX 페이지에 액세스할 수에 대 한 안전한 것으로 지정 하는 웹 파트의 컬렉션을 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 안전 컨트롤에 대 한 자세한 내용은 참조 [패키징 및 배포 프로젝트 항목에는 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)합니다.  
  
## <a name="element-information"></a>요소 정보  
  
|||  
|-|-|  
|**네임스페이스**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**스키마 이름**|SharePoint 프로젝트 항목 스키마|  
|**유효성 검사 파일**|ProjectItemModelSchema.xsd|  
|**비어 있을 수 있습니다.**|아니요|  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 프로젝트 항목 스키마 참조](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [프로젝트 항목에 패키징 및 배포 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)  
  
  