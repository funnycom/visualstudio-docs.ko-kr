---
title: "GPU 코드 디버그 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: c7e77a5a-cb57-4b11-9187-ecc89acc8775
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0699df7890528a200648ad10975b3cf272a3534f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-gpu-code"></a>GPU 코드 디버깅
GPU(그래픽 처리 장치)에서 실행되는 C++ 코드를 디버깅할 수 있습니다. Visual Studio의 GPU 디버깅 지원에는 경합 상태 감지, 프로세스 시작, 프로세스에 연결 및 디버깅 창에 대한 통합이 포함됩니다.  
  
## <a name="supported-platforms"></a>지원되는 플랫폼  
 디버깅은 [!INCLUDE[win7](../debugger/includes/win7_md.md)], [!INCLUDE[win8](../debugger/includes/win8_md.md)], [!INCLUDE[winsvr08_r2](../debugger/includes/winsvr08_r2_md.md)] 및 [!INCLUDE[winserver8](../debugger/includes/winserver8_md.md)]에서 지원됩니다. 소프트웨어 에뮬레이터에서 디버깅하는 경우 [!INCLUDE[win8](../debugger/includes/win8_md.md)] 또는 [!INCLUDE[winserver8](../debugger/includes/winserver8_md.md)]가 필요합니다. 하드웨어에서 디버깅하는 경우에는 사용 중인 그래픽 카드의 드라이버를 설치해야 합니다. 하드웨어 공급업체에 따라 일부 디버거 기능을 구현하지 않는 경우도 있습니다. 제한 사항에 대해서는 공급업체 설명서를 참조하십시오.  
  
> [!NOTE]
>  Visual Studio에서 GPU 디버깅을 지원하려는 IHV(Independent Hardware Vendor)는 VSD3DDebug 인터페이스를 구현하고 해당 공급업체의 드라이버를 대상으로 하는 DLL을 만들어야 합니다.  
  
## <a name="configuring-gpu-debugging"></a>GPU 디버깅 구성  
 디버거는 동일한 응용 프로그램 실행에 포함된 CPU 코드와 GPU 코드 둘 다에서 중단될 수 없습니다. 기본적으로 디버거는 CPU 코드에서 중단됩니다. GPU 코드를 디버깅하려면 다음 두 단계 중 하나를 사용합니다.  
  
-   에 **디버그 형식** 목록에서 **표준** 도구 모음 선택 **GPU 전용**합니다.  
  
-   **솔루션 탐색기**, 프로젝트에 대 한 바로 가기 메뉴에서 선택 **속성**합니다. 에 **속성 페이지** 대화 상자에서 **디버깅**를 선택한 후 **GPU 전용** 에 **디버거 형식** 목록.  
  
## <a name="launching-and-attaching-to-applications"></a>응용 프로그램 시작 및 응용 프로그램에 연결  
 Visual Studio 디버깅 명령을 사용하여 GPU 디버깅을 시작하고 중지할 수 있습니다. 자세한 내용은 [디버거로 코드 탐색](../debugger/navigating-through-code-with-the-debugger.md)을 참조하세요. 또한 실행 중인 프로세스에 GPU 디버거를 연결할 수 있지만, 이는 해당 프로세스가 GPU 코드를 실행하는 경우에만 가능합니다. 자세한 내용은 참조 [실행 중인 프로세스에 연결할](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)합니다.  
  
## <a name="run-current-tile-to-cursor-and-run-to-cursor"></a>현재 Tile을 커서까지 실행 및 커서까지 실행  
 GPU에서 디버깅하는 경우 커서 위치까지 실행하기 위한 두 가지 옵션이 있습니다. 두 옵션에 대한 명령은 코드 편집기의 바로 가기 메뉴에서 사용할 수 있습니다.  
  
1.  **커서까지 실행** 명령은 커서 위치에 도달 하 고 다음 중단 될 때까지 응용 프로그램을 실행 합니다. 이는 현재 스레드가 커서까지 실행됨을 의미하는 것이 아니라 커서 지점에 도달하는 첫 번째 스레드가 중단을 트리거함을 의미합니다. 참조 [디버거로 코드 탐색](../debugger/navigating-through-code-with-the-debugger.md)  
  
2.  **실행 현재 Tile을 커서** 명령은 모든 현재 타일의 스레드가 커서 한 다음 중단 될 때까지 응용 프로그램을 실행 합니다.  
  
## <a name="debugging-windows"></a>디버깅 창  
 특정 디버깅 창을 사용하여 GPU 스레드를 검사하고 플래그를 설정하고 중지할 수 있습니다. 자세한 내용은 다음을 참조하세요.  
  
-   [병렬 스택 창 사용](../debugger/using-the-parallel-stacks-window.md)  
  
-   [작업 창 사용](../debugger/using-the-tasks-window.md)  
  
-   [방법: 병렬 조사식 창 사용](../debugger/how-to-use-the-parallel-watch-window.md)  
  
-   [스레드 및 프로세스 디버깅](../debugger/debug-threads-and-processes.md) (디버그 위치 도구 모음)  
  
-   [방법: GPU 스레드 창 사용](../debugger/how-to-use-the-gpu-threads-window.md)  
  
## <a name="data-synchronization-exceptions"></a>데이터 동기화 예외  
 디버거는 실행 중에 몇 가지 데이터 동기화 조건을 식별할 수 있습니다. 조건이 감지되는 경우 디버거는 중단 상태로 전환됩니다. 두 가지 옵션이-**중단** 또는 **계속**합니다. 사용 하 여는 **예외** 대화 상자는 디버거가 이러한 조건을 감지할지도 조건을 중단 되 있는지 여부를 구성할 수 있습니다. 자세한 내용은 참조 [디버거를 사용한 예외 관리](../debugger/managing-exceptions-with-the-debugger.md)합니다. 사용할 수도 있습니다는 **옵션** 대화 상자는 기록 된 데이터는 데이터의 값을 변경 되지 않는 경우 디버거가 예외를 무시 해야 지정 합니다. 자세한 내용은 참조 [옵션 대화 상자, 디버깅, 일반](../debugger/general-debugging-options-dialog-box.md)합니다.  
  
## <a name="troubleshooting"></a>문제 해결  
  
### <a name="specifying-an-accelerator"></a>가속기 지정  
 코드에서 실행 중인 경우 GPU 코드의 중단점만 적중 되는 [accelerator:: direct3d_ref](/cpp/parallel/amp/reference/accelerator-class.md#accelerator__direct3d_ref_Data_Member) (REF) 가속기입니다. REF 가속기가으로 자동으로 선택 하 고 코드에서 가속기를 지정 하지 않으면는 **디버깅 가속기 형식** 프로젝트 속성에 있습니다. 코드에서 명시적으로 가속기를 선택하는 경우에는 REF 가속기가 디버깅 중에 사용되지 않으며 GPU 하드웨어에 디버깅 지원 기능이 없는 한 중단점이 적중되지 않습니다. 디버깅 중에 REF 가속기를 사용하도록 코드를 작성하여 이 문제를 해결할 수 있습니다. 자세한 내용은 프로젝트 속성을 참조 하십시오. 및 [accelerator 및 accelerator_view 개체를 사용 하 여](/cpp/parallel/amp/using-accelerator-and-accelerator-view-objects) 및 [c + + 디버그 구성에 대 한 프로젝트 설정을](../debugger/project-settings-for-a-cpp-debug-configuration.md)합니다.  
  
### <a name="conditional-breakpoints"></a>조건부 중단점  
 GPU 코드에서 조건부 중단점이 지원되지만 장치에서 일부 식은 계산될 수 없습니다. 식이 장치에서 계산될 수 없는 경우 디버거에서 계산됩니다. 디버거는 대개 장치보다 느리게 실행됩니다.  
  
### <a name="error-there-is-a-configuration-issue-with-the-selected-debugging-accelerator-type"></a>오류: 선택한 디버깅 가속기 형식에 구성 문제가 있습니다.  
 이 오류는 프로젝트 설정과 디버깅하고 있는 PC의 구성이 일치하지 않는 경우 발생합니다. 자세한 내용은 참조 [c + + 디버그 구성에 대 한 프로젝트 설정을](../debugger/project-settings-for-a-cpp-debug-configuration.md)합니다.  
  
### <a name="error-the-debug-driver-for-the-selected-debugging-accelerator-type-is-not-installed-on-the-target-machine"></a>오류: 선택한 디버깅 가속기 형식용 디버그 드라이버가 대상 컴퓨터에 설치되어 있지 않습니다.  
 이 오류는 원격 PC에서 디버깅하는 경우에 발생합니다. 디버거는 드라이버가 원격 PC에 설치되어 있는지 여부를 런타임까지 확인할 수 없습니다. 드라이버는 그래픽 카드의 제조업체에서 제공합니다.  
  
### <a name="error-timeout-detection-and-recovery-tdr-must-be-disabled-at-the-remote-site"></a>오류: 원격 사이트에서 TDR(제한 시간 탐지 및 복구)을 사용하지 않도록 설정해야 합니다.  
 C++ AMP 계산이 Windows TDR(제한 시간 탐지 및 복구)에서 설정된 기본 시간 간격을 초과할 수 있습니다. 이 경우 계산이 취소되고 데이터가 손실됩니다. 자세한 내용은 참조 [c + + amp에서 TDRs 처리](http://go.microsoft.com/fwlink/p/?LinkId=249154)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: c + + AMP 응용 프로그램 디버깅](/cpp/parallel/amp/walkthrough-debugging-a-cpp-amp-application)   
 [C + + 디버그 구성에 대 한 프로젝트 설정](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [Visual Studio에서 GPU 디버깅을 시작합니다](http://go.microsoft.com/fwlink/p/?LinkId=255381)