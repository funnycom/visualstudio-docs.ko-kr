---
title: "Visual Studio의 디버거를 사용 하 여 코드 탐색 | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 02/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.execution
helpviewer_keywords:
- stepping
- debugging [Visual Studio], execution control
- execution, controlling in debugger
ms.assetid: 759072ba-4aaa-447e-8e51-0dd1456fe896
caps.latest.revision: "42"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cda62de6fe72598674b90e4a0ef5dccd8cf2a2af
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="navigate-code-with-the-visual-studio-debugger"></a>Visual Studio 디버거를 사용 하 여 코드 탐색
디버거에서 코드를 탐색 하는 명령 및 바로 가기를을 잘 알고 있으며 있는 빠르고 쉽게 찾아 앱의 문제를 해결 하려면. 디버거에서 코드를 탐색 하는 동안 응용 프로그램의 상태를 검사 또는 실행 흐름에 해당 하는 방법에 대 한 자세한 정보 수 있습니다.  
  
## <a name="start-debugging"></a>디버깅 시작  
 사용 하 여 디버깅 세션을 시작할 수, **F5** (**디버그** > **디버깅 시작**). 이 명령은 디버거가 연결 된 앱을 시작 합니다.  
  
 녹색 화살표 또한 디버거를 시작 (동일 **F5**).  
  
 ![DBG &#95; 기본 사항 &#95; 디버깅 시작 &#95;](../debugger/media/dbg_basics_start_debugging.png "DBG_Basics_Start_Debugging")  
  
 디버거가 연결 된 앱을 시작할 수는 몇 가지 다른 방법을 포함 **F11** ([코드를 한 단계씩](#BKMK_Step_into__over__or_out_of_the_code)), **F10** ([코드 건너뛰기](#BKMK_Step_over_Step_out)), 또는 사용 하 여 **커서까지 실행**합니다.  이러한 옵션에 수행할 작업에 대 한 정보는이 항목의 다른 섹션을 참조 하십시오.  
  
 을 디버깅할 때는 노란색 줄 다음에 실행 될 코드를 표시 합니다.  
  
 ![DBG &#95; 기본 사항 &#95; 나누기 및 #95; 모드](../debugger/media/dbg_basics_break_mode.png "DBG_Basics_Break_Mode")  
  
 디버깅 하는 동안과 같은 명령을 간을 전환할 수 있습니다 **F5**, **F11** 신속 하 게 검토 하려면 코드 이동 (예: 중단점)이이 항목에서 설명 하는 다른 기능을 사용 합니다.  
  
 지역 창에서 변수 값 보기 또는 조사식 창에서 식 계산과 같은 대부분의 디버거 기능은 디버거가 일시 중지 하는 동안에 사용할 수 있는 (호출 또한 *중단 모드*). 디버거를 일시 중지 하면 함수, 변수, 하는 동안 일시 중단 하면 응용 프로그램 상태가 및 개체가 메모리에 남아 있습니다. 중단 모드에서 요소의 위치와 상태 위반이 나 버그를 확인할 수 있습니다. 일부 프로젝트 형식에 대 한 중단 모드에서 앱에 대 한 조정이 만들 수 있습니다. 이러한 기능을 보여 주는 비디오를 시청 하려면 [디버거 시작](https://www.youtube.com/watch?v=FtGCi5j30YU&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=6)합니다.
  
##  <a name="BKMK_Step_into__over__or_out_of_the_code"></a>한 줄씩 코드를 한 단계씩  
 을 중지 하려면 코드 (각 문)의 각 줄에서 디버깅 하는 동안 사용 된 **F11** 바로 가기 키 (또는 **디버그** > **한 단계씩 코드 실행** 메뉴에서).  
  
> [!TIP]
>  각 코드 줄을 실행 하면서 해당 값을 표시 하거나 사용할 변수 위로 가져가면 수 있습니다는 [지역](../debugger/autos-and-locals-windows.md) 및 [조사식](../debugger/autos-and-locals-windows.md) 변경 해당 값을 조사 하는 windows.  
  
 다음은의 동작에 대 한 자세한 내용 **한 단계씩 코드 실행**:  
  
-   중첩된 함수 호출인 경우 **한 단계씩 코드 실행** 명령은 가장 안쪽에 중첩된 함수를 한 단계씩 실행합니다. **와 같은 호출에** 한 단계씩 코드 실행 `Func1(Func2())`을 사용하면 디버거에서 함수 `Func2`를 한 단계씩 실행합니다.  
  
-   실제로 디버거는 실제 줄이 아닌 코드 문을 단계별로 실행합니다. 예를 들어 한 줄에 `if` 절을 작성할 수 있습니다.  
  
    ```CSharp  
    int x = 42;  
    string s = "Not answered";  
    if( int x == 42) s = "Answered!";  
    ```  
  
    ```VB  
    Dim x As Integer = 42  
    Dim s As String = "Not answered"  
    If x = 42 Then s = "Answered!"  
    ```  
  
     이 줄을 한 단계씩 실행하면 디버거는 조건을 한 단계로 처리하고 결과를 다른 단계로 처리합니다(이 예에서는 조건이 참임).  
  
 함수를 한 단계씩 실행 하는 동안 호출 스택을 시각적으로 추적, 참조 [디버깅 하는 동안 호출 스택의 메서드 매핑할](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)합니다.  
  
##  <a name="BKMK_Step_over_Step_out"></a>코드를 건너뛴 함수  
 디버거에서 코드를 실행 하는 경우 종종 얻게 될 특정 함수에서 수행 되는 작업을 볼 필요가 없습니다 (신경쓰지 않아도 또는 알고 있는 작동 같은 테스트 된 라이브러리 코드). 이러한 명령을 사용 하 여 코드를 통해 건너뛸 (함수 여전히 실행 물론, 되지만, 디버거는 해당 건너뜁니다).  
  
|키보드 명령|메뉴 명령|설명|  
|----------------------|------------------|-----------------|  
|**F10**|**프로시저 단위 실행**|현재 줄에 함수 호출을 포함 하는 경우 **프로시저 단위 실행** 코드를 실행 한 후 호출된 된 함수에서 반환 된 후 코드의 첫 번째 줄에서 실행을 일시 중단 합니다.|  
|**Shift + f 11**|**프로시저 나가기**|**프로시저 나가기** 계속 코드를 실행 하 고 현재 함수 (현재 함수를 통해 디버거 건너뜁니다)는 반환 될 때 실행을 일시 중단 합니다.|  
  
> [!TIP]
>  로 시작 하는 응용 프로그램의 진입점을 찾으려고 해야 할 경우 **F10** 또는 **F11**합니다. 응용 프로그램 상태를 검사 하거나 해당 실행 흐름에 대 한 자세한 내용을 검색 하려고 할 때 유용한 경우가 있습니다.  
  
##  <a name="BKMK_Break_into_code_by_using_breakpoints_or_Break_All"></a>특정 위치 또는 함수까지 실행  
 종종 코드 디버깅 하는 기본 방법은, 이러한 메서드는 유용 검사를 하려는 코드 정확히 알고 있는 경우 또는 디버깅을 시작 하려면 알고 이상.  
  
-   **코드에 중단점 설정**  
  
     코드에 간단한 중단점을 설정하려면 Visual Studio 편집기에서 소스 파일을 엽니다. 실행을 일시 중단 하 고 상황에 맞는 메뉴를 보고 선택할 코드 창에서 마우스 오른쪽 단추로 클릭 하려는 코드 줄에 커서를 설정한 **중단점 > 중단점 삽입** (하거나 키를 눌러 **F9**). 디버거가 해당 줄이 실행 되기 전에 실행 오른쪽을 일시 중단 합니다.  
  
     ![중단점을 설정](../debugger/media/dbg_basics_setbreakpoint.png "DBG_Basics_SetBreakpoint")  
  
     Visual Studio에서 중단점은 조건부 중단점 및 추적점과 같은 다양한 추가 기능을 제공합니다. 참조 [중단점을 사용 하 여](../debugger/using-breakpoints.md)합니다.  
  
-   **커서 위치까지 실행**  
  
     커서 위치까지 실행하려면 소스 창에서 실행 가능한 코드 줄에 커서를 놓습니다. 편집기의 상황에 맞는 메뉴 (편집기에서 마우스 오른쪽 단추 클릭)에서 선택 **커서까지 실행**합니다. 이 임시 중단점 설정과 유사 합니다.

-   **클릭을 실행 합니다.** 

    디버거에서 일시 중지 된 동안 코드의 지점에을 실행 하려면 선택은 **여기로 실행** (아이콘이 표시 코드 줄을 가리키면) 녹색 화살표 아이콘입니다. 이렇게 하면 임시 중단점을 설정할 필요가 없습니다.

    ![디버거는 클릭에 실행의](../debugger/media/dbg-run-to-click.png "DbgRunToClick") 

    > [!NOTE]
    > **실행을 클릭 하 여** 의 새로운 [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]합니다.
  
-   **수동으로 코드 중단**  
  
     실행 중인 응용 프로그램의 사용 가능한 다음 코드 줄에서 중단하려면 **디버그**, **모두 중단** 을 선택합니다(키보드: **Ctrl+Alt+Break**). 
  
     해당 소스 또는 기호(.pdb) 파일 없이 코드를 실행하는 동안 중단하는 경우 디버거에서 적절한 파일을 찾는 데 도움이 될 수 있는 **소스 파일을 찾을 수 없음** 또는 **기호를 찾을 수 없음** 페이지가 표시됩니다. 참조 [기호 (.pdb)을 지정 하 고 소스 파일과](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)합니다. 지원 파일에 액세스할 수 없는 경우에도 디스어셈블리 창에서 어셈블리 명령을 디버깅할 수 있습니다.  
  
-   **호출 스택에 있는 함수까지 실행**  
  
     에 **호출 스택** 창 (디버깅 하는 동안 사용 가능)를 함수를 선택, 마우스 오른쪽 단추로 클릭 및 선택 **커서까지 실행**합니다. 호출 스택을 시각적으로 추적, 참조 [디버깅 하는 동안 호출 스택의 메서드 매핑할](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)합니다.  
  
-   **이름으로 지정된 함수까지 실행**  
  
     지정된 된 함수에 도달할 때까지 응용 프로그램을 실행 하도록 디버거를 알 수 있습니다. 함수 이름을 지정하거나 호출 스택에서 함수를 선택할 수 있습니다.  
  
     함수 이름을 지정하려면 **디버그**, **새 중단점**, **함수에서 중단**을 선택한 다음 함수의 이름과 기타 식별 정보를 입력합니다.  
  
     ![새 중단점 대화 상자](../debugger/media/dbg_execution_newbreakpoint.png "DBG_Execution_NewBreakpoint")  
  
     함수가 오버로드되거나 여러 네임스페이스에 있는 경우 **중단점 선택** 대화 상자에서 원하는 함수를 선택할 수 있습니다.  
  
     ![중단점 선택 대화 상자](../debugger/media/dbg_execution_overloadedbreakpoints.png "DBG_Execution_OverloadedBreakpoints")  
  
##  <a name="BKMK_Set_the_next_statement_to_execute"></a>실행 흐름을 변경 하려면 포인터를 이동  
 디버거를 일시 중지 된 동안에 코드를 실행할 수의 다음 문을 설정 하려면 명령 포인터를 이동할 수 있습니다. 소스 또는 디스어셈블리 창의 여백에 있는 노란색 화살표는 다음에 실행할 문의 위치를 나타냅니다. 코드의 일부를 건너뛰거나 이전에 실행한 줄로 돌아가려면 이 화살표를 이동합니다. 알려진 버그를 포함하는 코드 섹션을 건너뛰려는 경우 등에 이 방법을 사용할 수 있습니다.  
  
 ![포인터를 이동](../debugger/media/dbg_basics_example3.gif "DBG_Basics_Example3")
  
 다음에 실행할 문을 설정하려면 다음 절차 중 하나를 사용합니다.  
  
-   소스 창에서 노랑 화살표를 같은 소스 파일에서 다음 문을 설정할 위치로 끌어 놓습니다.  
  
-   소스 창에서 다음에 실행할 마우스 오른쪽 단추로 클릭 한 다음 선택 하려는 줄에 커서를 설정 **다음 문 설정**합니다.  
  
-   디스어셈블리 창에서 커서를 설정한 다음에 실행할 마우스 오른쪽 단추로 클릭 하려는 어셈블리 명령에는 선택한 **다음 문 설정**합니다.  
  
> [!CAUTION]
>  다음 문을 설정하면 프로그램 카운터가 새 위치로 바로 이동하게 됩니다. 이 명령은 주의해서 사용해야 합니다.  
>   
>  -   기존 실행 위치와 새 실행 위치 사이에서는 명령이 실행되지 않습니다.  
> -   실행 위치를 뒤로 이동하면 그 사이에서 실행된 명령이 실행 취소되지 않습니다.  
> -   다음 문을 다른 함수나 범위로 이동하면 호출 스택이 손상되어 런타임 오류나 예외가 발생할 수 있습니다. 다음 문을 다른 범위로 이동하려고 하면 디버거에서 대화 상자가 열리고 여기서 작업을 취소할 수 있습니다. Visual Basic의 경우 다음 문을 다른 범위나 함수로 이동할 수 없습니다.  
> -   네이티브 C++에서 런타임 검사를 활성화한 경우 다음 문을 설정하면 실행이 메서드의 끝에 도달할 때 예외가 throw될 수 있습니다.  
> -   편집하며 계속하기를 활성화한 경우 편집하며 계속하기에서 즉시 다시 매핑할 수 없는 종류의 편집을 수행하면 **다음 문 설정** 이 실패합니다. 예를 들어 catch 블록 내의 코드를 편집하면 이 문제가 발생합니다. 이 경우에 지원 작업이 않습니다 한다고 알리는 오류 메시지가 표시 됩니다.  
  
> [!NOTE]
>  관리 코드의 경우 다음과 같은 조건에서는 다음 문을 이동할 수 없습니다.  
>   
>  -   다음 문이 현재 문과 다른 메서드에 있는 경우  
> -   Just-In-Time 디버깅을 사용하여 디버깅을 시작한 경우  
> -   호출 스택 해제를 진행 중인 경우  
> -   System.StackOverflowException 또는 System.Threading.ThreadAbortException 예외가 throw된 경우  
  
 응용 프로그램을 실행하는 동안에는 다음 문을 설정할 수 없습니다. 다음에 실행할 문을 설정하려면 디버거가 중단 모드에 있어야 합니다.  
  
## <a name="BKMK_Restrict_stepping_to_Just_My_Code"></a>사용자가 아닌 코드를 한 단계씩  
 기본적으로 디버거 응용 프로그램 코드만 디버깅 하는 동안 라고 디버거에 의해 결정 된를 표시 하려고 *내 코드만*합니다. (참조 [내 코드만](../debugger/just-my-code.md) 다양 한 프로젝트 형식 및 언어에 대 한이 과정 및 동작을 사용자 지정 하는 방법을 볼 수 있습니다.) 하지만, 디버깅 하는 동안에 경우에 따라 필요할 수 있습니다를 프레임 워크 코드, 타사 라이브러리 코드 또는 호출을 살펴보는 운영 체제 (시스템 호출).  
  
 내 코드만 5d;으로 이동 하 여 해제할 수 있습니다 **도구** > **옵션** > **디버깅** 선택을 취소 하 고는 **내 코드만 사용** 확인란을 선택 합니다.  
  
 내 코드만 해제 하면 디버거 사용자 코드가 아닌 한 단계씩 실행할 수 하 고 사용자 코드가 아닌 디버거 창에 나타납니다.  
  
> [!NOTE]
>  장치 프로젝트에 대해서는 내 코드만 옵션이 지원되지 않습니다.  
  
 **한 단계씩 시스템 호출 실행**  
  
 시스템 코드에 대 한 디버깅 기호를 로드 했 고 내 코드만 해제, 하는 경우 다른 모든 호출과 경우와 마찬가지로 시스템 호출을 한 단계씩 실행할 수 있습니다.  
  
 Microsoft 기호 파일에 액세스 하려면 참조 [기호 서버를 사용 하 여 로컬 컴퓨터에 없는 기호 파일을 찾을](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md#BKMK_Use_symbol_servers_to_find_symbol_files_not_on_your_local_machine) 에 [지정 기호 (.pdb) 및 소스 파일](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md) 항목입니다.  
  
 디버깅하는 동안 특정 시스템 구성 요소에 대한 기호를 로드하려면  
  
1.  모듈 창을 엽니다 (키보드: **Ctrl + Alt + U**).  
  
2.  기호를 로드하려는 모듈을 선택합니다.  
  
     **기호 상태** 열을 보면 기호가 로드된 모듈을 확인할 수 있습니다.  
  
3.  상황에 맞는 메뉴에서 **기호 로드** 를 선택합니다.  
  
##  <a name="BKMK_Step_into_properties_and_operators_in_managed_code"></a> 한 단계씩 관리 코드의 속성 및 연산자 실행  
 기본적으로 디버거는 관리 코드의 속성과 연산자를 건너뜁니다. 대부분의 경우 이렇게 하면 더 나은 디버깅 환경이 제공됩니다. 속성이 나 연산자를 한 단계씩 실행을 사용 하도록 설정 하려면 선택 **디버그** > **옵션**합니다. 에 **디버깅** > **일반** 선택을 취소 페이지는 **속성 및 연산자 건너뛰기 (관리 전용) 단계** 확인란