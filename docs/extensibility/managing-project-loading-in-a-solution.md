---
title: "솔루션의 프로젝트 로드 관리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: solutions, managing project loading
ms.assetid: 097c89d0-f76a-4aaf-ada9-9a778bd179a0
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a2be2c75704646bab50f89377d960d44f6fa14f1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="managing-project-loading-in-a-solution"></a>솔루션에서 관리 프로젝트 로드
Visual Studio 솔루션에는 다 수의 프로젝트 포함 될 수 있습니다. 기본 Visual Studio 동작은 솔루션을 열 때에는 솔루션의 모든 프로젝트를 로드 하 고 사용자 모두 로드 작업이 완료 될 때까지 프로젝트 액세스를 사용할 수 없도록 합니다. 프로젝트 로드 프로세스가 2 분 이상 소요 시간:, 프로젝트의 총 수와 로드 되는 프로젝트 수를 보여 주는 진행률 표시줄이 표시 됩니다. 사용자는 여러 프로젝트를 포함 하는 솔루션에서 작업할 때 프로젝트를 언로드할 수 있지만이 프로시저에는 몇 가지 단점이: 언로드된 프로젝트에는 솔루션 다시 빌드 명령의 일환으로 빌드하지 않은 및 닫힘의 멤버 및 형식 설명을 IntelliSense 프로젝트는 표시 되지 않습니다.  
  
 개발자는 솔루션 로드 시간을 줄일 수 있습니다 및 로드 동작을 만들어 솔루션 로드 관리자는 프로젝트를 관리 합니다. 솔루션 로드 관리자 수 특정 프로젝트 또는 프로젝트 형식에 대 한 우선 순위를 로드 하는 다른 프로젝트 설정, 배경 빌드를 시작 하기 전에 프로젝트를 로드 했는지 확인, 다른 백그라운드 작업이 완료 될 때까지 백그라운드 로드 지연 및 수행 다른 프로젝트 부하 관리 작업입니다.  
  
## <a name="project-loading-priorities"></a>우선 순위를 로드 하는 프로젝트  
 Visual Studio는 4 개의 서로 다른 프로젝트 로드 우선 순위를 정의합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop._VSProjectLoadPriority>(기본값): 솔루션을 열 프로젝트 비동기적으로 로드 됩니다. 언로드된 프로젝트가 이미 솔루션을 연 후이 우선 순위 설정 되 면 프로젝트는 다음 유휴 지점에 로드 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop._VSProjectLoadPriority>: 솔루션을 열 프로젝트 사용자가 속한 모든 프로젝트에 로드 될 때까지 기다릴 필요 없이 로드 될 프로젝트에 액세스할 수 있도록 백그라운드에서 로드 됩니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop._VSProjectLoadPriority>: 프로젝트 액세스 될 때 로드 됩니다. 때나 (솔루션의 사용자 옵션 파일에 유지 됨)는 열려 있는 문서 목록에 있기 때문에 솔루션을 열면 프로젝트에 속하는 파일을 열 때 솔루션 탐색기에서 프로젝트 노드를 확장할 때는 프로젝트에 액세스 하는 다른 프로젝트 즉 로드 되는 프로젝트에 종속 됩니다. 이러한 유형의 프로젝트 빌드 프로세스를 시작 하기 전에 자동으로 로드 되지 않았습니다. 솔루션 로드 관리자는 필요한 모든 프로젝트를 로드 했는지 확인 해야 합니다. 이러한 프로젝트는 전체 솔루션 파일에서 찾기/바꾸기를 시작 하기 전에 로드 해야 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop._VSProjectLoadPriority>: 프로젝트는 로드 되지 않게 하려면 사용자가 명시적으로 요청 하지 않는 한 합니다. 이 경우 프로젝트를 명시적으로 로드 되지 않은 경우입니다.  
  
## <a name="creating-a-solution-load-manager"></a>솔루션 로드 관리자 만들기  
 개발자가 관리자를 만들 수 솔루션 로드를 구현 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager> 알리고 Visual Studio 솔루션 로드 관리자 활성 상태 인지 확인 합니다.  
  
#### <a name="activating-a-solution-load-manager"></a>솔루션 로드 관리자 활성화  
 Visual Studio 솔루션 로드 관리자 하나만 지정된 된 시간에 솔루션 로드를 활성화할 때 Visual Studio를 알려 하므로 관리자를 허용 합니다. 두 번째 솔루션 로드 관리자는 나중에 활성화 되 면 솔루션 로드 관리자의 연결이 끊어집니다.  
  
 가져와야 하는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution> 설정 및 서비스는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4> 속성:  
  
```csharp  
IVsSolution pSolution = GetService(typeof(SVsSolution)) as IVsSolution;  
object objLoadMgr = this;   //the class that implements IVsSolutionManager  
pSolution.SetProperty((int)__VSPROPID4.VSPROPID_ActiveSolutionLoadManager, objLoadMgr);  
```  
  
#### <a name="implementing-ivssolutionloadmanager"></a>IVsSolutionLoadManager 구현  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager.OnBeforeOpenProject%2A> 메서드 솔루션 열기의 과정 동안 호출 됩니다. 이 메서드를 구현 하려면 사용는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManagerSupport> 서비스를 관리 하려면 프로젝트의 형식에 대 한 부하 우선 순위를 설정 합니다. 예를 들어 다음 코드를 백그라운드에서 로드 C# 프로젝트 형식 설정 합니다.  
  
```csharp  
Guid guidCSProjectType = new Guid("{FAE04EC0-301F-11d3-BF4B-00C04F79EFBC}");  
pSLMgrSupport.SetProjectLoadPriority(guidProjectID, (uint)_VSProjectLoadPriority.PLP_BackgroundLoad);  
```  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadManager.OnDisconnect%2A> Visual Studio를 종료 하 고 또는 다른 패키지로 전송 활성 솔루션 로드 관리자도 호출 하 여는 경우 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.SetProperty%2A> 와 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4> 속성입니다.  
  
#### <a name="strategies-for-different-kinds-of-solution-load-manager"></a>다양 한 종류의 솔루션 로드 관리자에 대 한 전략  
 관리 하는 솔루션의 형식에 따라 다양 한 방법으로 부하 관리자 솔루션을 구현할 수 있습니다.  
  
 솔루션 로드 관리자는 일반적으로 로드 하는 솔루션을 관리를 위한 서비스, VSPackage의 일환으로 구현할 수 있습니다. 추가 하 여 패키지를 autoload로 설정 해야는 <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> 값이 VSPackage에서 <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionOpening_guid>합니다. 솔루션 로드 관리자에서 활성화할 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> 메서드.  
  
> [!NOTE]
>  자동 로드 패키지에 대 한 자세한 내용은 참조 [로드 Vspackage](../extensibility/loading-vspackages.md)합니다.  
  
 Visual Studio에서 마지막 솔루션 부하 관리자만 활성화할를 인식 하므로 일반 솔루션 부하 관리자 자신을 활성화 하기 전에 기존 부하 관리자 인지 검색 항상 해야 합니다. GetProperty() 솔루션 서비스를 호출 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4> 반환 `null`, 관리자가 없거나 활성 솔루션 로드 합니다. Null 반환 하지 않으면, 개체가 솔루션 로드 관리자와 동일 하 게 인지 확인 합니다.  
  
 VSPackage 솔루션 로드 이벤트를 구독할 수 솔루션 로드 관리자 몇 가지 유형의 솔루션을 관리 하려는 경우 (호출 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AdviseSolutionEvents%2A>)에 대 한 이벤트 처리기를 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeOpenSolution%2A> 솔루션 로드 관리자를 활성화 합니다.  
  
 솔루션 로드 관리자만 특정 솔루션 관리 하려는 경우 솔루션 파일의 일부로 활성화 정보를 유지할 수 있습니다. 이 작업을 수행 하려면 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.WriteSolutionProps%2A> 사전 솔루션 섹션에 대 한 합니다.  
  
 특정 솔루션 부하 관리자에서 자체를 비활성화 해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents.OnAfterCloseSolution%2A> 다른 솔루션 로드 관리자와 충돌 하지 순서 대로 이벤트 처리기입니다.  
  
 전역 프로젝트 부하 우선 순위 (예를 들어에 설정 된 속성 옵션 페이지)를 유지 하기 위해 솔루션 로드 관리자에서 활성화할 수 있습니다만 솔루션 로드 관리자 해야 할 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A> 이벤트 처리기를 다음에 솔루션 속성에서 설정을 유지 합니다. 솔루션 로드 관리자를 비활성화 합니다.  
  
## <a name="handling-solution-load-events"></a>솔루션 로드 이벤트를 처리합니다.  
 솔루션 로드 이벤트를 구독 하려면 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AdviseSolutionEvents%2A> 솔루션 로드 관리자를 활성화 하면 됩니다. 구현 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents>, 우선 순위를 로드 하는 다른 프로젝트와 관련 된 이벤트에 응답할 수 있습니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeOpenSolution%2A>:이 솔루션을 열기 전에 발생 합니다. 솔루션의 프로젝트에 대 한 우선 순위를 로드 하는 프로젝트를 변경 하기를 사용할 수 있습니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeBackgroundSolutionLoadBegins%2A>:이 솔루션은 완전히 로드 하지만 배경 이전 프로젝트 로드가 다시 시작 후 발생 합니다. 예를 들어 사용자 부하 우선 순위는 LoadIfNeeded, 프로젝트 액세스 했을 수 또는 솔루션 로드 관리자 변경 했을 수 프로젝트 부하 우선 순위는 해당 프로젝트의 백그라운드 로드를 시작 하는 BackgroundLoad를 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnAfterBackgroundSolutionLoadComplete%2A>:이 다음에 발생 처음 완전히 로드 된 솔루션이 솔루션 로드 관리자가 있는지 여부. 솔루션이 완전히 로드 될 때마다 백그라운드 로드 또는 요청 시 로드 한 후에 실행 됩니다. 같은 시간에 <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionExistsAndFullyLoaded_guid> 다시 활성화 됩니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnQueryBackgroundLoadProjectBatch%2A>:이 프로젝트 (또는 프로젝트)를 로드 하기 전에 발생 합니다. 기타 백그라운드 프로세스가 완료 된 후에 프로젝트를 로드 하려면 설정 `pfShouldDelayLoadToNextIdle` 를 **true**합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnBeforeLoadProjectBatch%2A>:이 프로젝트의 일괄 처리를 로드 하려고 할 때 발생 합니다. 경우 `fIsBackgroundIdleBatch` 가 true 인 경우; 백그라운드에서 로드 하는 프로젝트는 `fIsBackgroundIdleBatch` 이 false 이면 프로젝트는 로드 되도록 사용자 요청으로 인해 동기적으로 예를 들어 사용자 솔루션 탐색기에서 보류 중인 프로젝트를 확장 합니다. 그렇지 않은 경우 수행 해야 하는 비용이 많이 드는 작업을 수행 하려면이 옵션을 구현할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A>합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionLoadEvents.OnAfterLoadProjectBatch%2A>:이 프로젝트의 일괄 처리가 로드 된 후 발생 합니다.  
  
## <a name="detecting-and-managing-solution-and-project-loading"></a>검색 및 관리 솔루션 및 프로젝트 로드  
 프로젝트 및 솔루션의 부하 상태를 검색 하기 위해 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.GetProperty%2A> 다음 값을 사용 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>: `var` 반환 `true` 솔루션과 해당 프로젝트가 모두 로드 된 경우, 그렇지 않으면 `false`합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>: `var` 반환 `true` 경우 프로젝트의 현재에 로드 되는 백그라운드 그렇지 않으면 `false`합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID4>: `var` 반환 `true` 경우 프로젝트의 현재 로드 되 고 동기적으로 다른 명시적 부하 또는 사용자 명령으로 인해 그렇지 않으면 `false`합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID2>: `var` 반환 `true` 닫혀 있는 경우 솔루션이 현재 되 고 그렇지 않으면 `false`합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>: `var` 반환 `true` 솔루션 현재을 여는 그렇지 않은 경우 `false`합니다.  
  
 다음 방법 중 하나를 호출 하 여 프로젝트 및 솔루션 (프로젝트 부하 우선 순위 이란) 없이 로드 되도록을 보장할 수도 있습니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureSolutionIsLoaded%2A>: 메서드가 반환 되기 전에 로드 하도록 솔루션의 프로젝트를 강제로이 메서드를 호출 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureProjectIsLoaded%2A>:이 메서드를 호출에서 프로젝트를 강제로 `guidProject` 메서드가 반환 되기 전에 로드 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution4.EnsureProjectsAreLoaded%2A>:이 메서드를 호출에서 프로젝트를 강제로 `guidProjectID` 메서드가 반환 되기 전에 로드 합니다.  
  
> [!NOTE]
>  이어야 합니다. 기본적으로 요청에 있는 프로젝트만 로드 및 이지만 배경 부하 우선 순위 로드 되는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSBSLFLAGS> 플래그는 메서드에 전달 된, 명시적으로 로드 하는 것으로 표시 된 것을 제외한 모든 프로젝트를 로드 됩니다.