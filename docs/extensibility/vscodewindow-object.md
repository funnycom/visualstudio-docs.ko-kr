---
title: "VSCodeWindow 개체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VSCodeWindow
helpviewer_keywords:
- views [Visual Studio SDK], VSCodeWindow object
- VsCodeWindow object
ms.assetid: cf5fe926-e784-4098-bc01-cac49c7c55c6
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2de0998a3d89c1af3e18fa60aa3f8511716f6165
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="vscodewindow-object"></a>VSCodeWindow 개체
코드 창은 일반적으로 하나 이상의 텍스트 뷰를 포함할 수 있는 특수 한 문서 창에서 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> 개체입니다.  
  
 아키텍처 측면에서 코드 창에는 창 프레임 내에 있는 문서 창이입니다. 기능적으로 코드 창에는 추가 기능이 있는 문서 창 단순히입니다. (Mdi 다중) 다중 문서 인터페이스 모드로 코드 MDI 자식 프레임입니다. 자세한 내용은 참조 [레거시 API를 사용 하 여 코드 창을 사용자 지정](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)합니다.  
  
 다음 표에서의 인터페이스는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow> 개체입니다.  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>|전역 고유 식별자 (GUID)를 식별 하는 서비스를 찾을 일반 액세스 메커니즘을 제공 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>|하나 이상의 코드 보기를 포함 하는 여러 문서 MDI (인터페이스) 자식을 나타냅니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|창 프레임을 채웁니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>   
 [숫자 값 편집](http://msdn.microsoft.com/en-us/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)