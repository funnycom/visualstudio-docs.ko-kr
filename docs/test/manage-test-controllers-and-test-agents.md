---
title: Visual Studio에서 테스트 컨트롤러 및 테스트 에이전트 관리| Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 6d99d01dbe26354b8a3b3afa18d1337c64d1b390
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="manage-test-controllers-and-test-agents"></a>테스트 컨트롤러 및 테스트 에이전트 관리

Visual Studio를 사용하여 테스트를 원격으로 실행하거나 여러 컴퓨터에 테스트를 배포하거나 부하 테스트를 실행하려면 테스트 컨트롤러, 테스트 에이전트 및 테스트 설정 파일을 설치해야 합니다. 이 항목에서는 Test Controller 및 테스트 에이전트를 처음 설치하고 구성한 후 관리하는 방법에 대해 설명합니다.

Microsoft Test Manager를 사용하여 랩 환경에서 테스트를 실행하는 경우 Microsoft Test Manager용 **랩 센터**의 **테스트 컨트롤러 관리자**를 사용하여 테스트 컨트롤러와 해당 에이전트를 관리합니다. 이 항목은 Visual Studio를 사용하여 테스트를 실행할 경우에만 적용할 수 있습니다.

테스트 에이전트와 테스트 컨트롤러를 설치 및 구성하여 Visual Studio에서 테스트를 실행하는 방법은 [테스트 에이전트 및 컨트롤러 구성](../test/configure-test-agents-and-controllers-for-load-tests.md)을 참조하세요.

테스트 컨트롤러 및 등록된 에이전트를 구성하고 모니터링하려면 실행할 테스트가 포함된 테스트 프로젝트에 테스트 설정 파일이 있어야 합니다. 테스트 설정 파일을 열고 **역할**을 선택한 다음, **컨트롤러** 필드의 드롭다운에서 **테스트 컨트롤러 관리**를 선택합니다.

부하 테스트 프로젝트의 경우 **부하 테스트** 메뉴에서 **테스트 컨트롤러 관리**를 선택할 수도 있습니다.

## <a name="add-a-test-agent-to-a-test-controller"></a>테스트 컨트롤러에 테스트 에이전트 추가

테스트 에이전트를 다른 테스트 컨트롤러에 추가할 수도 있고 방금 설치한 테스트 컨트롤러에 테스트 에이전트를 추가해야 할 수도 있습니다.

### <a name="to-add-a-test-agent-to-a-test-controller"></a>테스트 컨트롤러에 테스트 에이전트를 추가하려면

1. **시작** > **테스트 에이전트 구성 도구**를 선택합니다.

     **테스트 에이전트 구성** 대화 상자가 표시됩니다.

    > [!NOTE]
    > 테스트 에이전트를 테스트 컨트롤러에 추가하려면 테스트 에이전트가 설치되어 있어야 합니다. 테스트 에이전트를 설치하는 방법에 대한 자세한 내용은 [테스트 에이전트 설치 및 구성](../test/lab-management/install-configure-test-agents.md)을 참조하세요.

2. 테스트 에이전트가 실행되는 방식을 변경하려면 **실행 옵션**을 선택합니다.

     테스트 에이전트를 실행하기 위한 다음 두 개의 옵션이 표시됩니다.

     **서비스** 테스트를 실행할 때 비디오 기록을 만들거나 코딩된 UI 테스트와 같이 데스크톱과 상호 작용하는 자동화된 테스트를 실행할 필요가 없는 경우 **다음으로 테스트 에이전트 실행**에서 **서비스**를 선택합니다. 그러면 테스트 에이전트가 서비스로 시작됩니다. **다음**을 선택합니다.

     이제 테스트 에이전트가 서비스로 시작될 때 사용할 사용자에 대한 세부 정보를 입력할 수 있습니다.

    1. **사용자 이름**에 이름을 입력합니다.

    2. **암호**에 암호를 입력합니다.

        |**중요한 사용자 계정 정보**|
        |--------------------------------------------|
        |- 사용자 계정에 대한 Null 암호는 지원되지 않습니다.|
        |- IntelliTrace 수집기 또는 네트워크 에뮬레이션을 사용하려면 사용자 계정이 Administrators 그룹의 멤버여야 합니다.|
        |- 에이전트 사용자 이름이 에이전트 서비스에 없으면 해당 사용자 이름이 추가됩니다. 이 경우 테스트 컨트롤러에 대한 사용 권한이 필요합니다.|
        |- 테스트 컨트롤러를 사용하려는 사용자는 테스트 컨트롤러의 사용자 계정에 있어야 합니다. 그렇지 않으면 컨트롤러에 대한 테스트를 실행할 수 없습니다.|

     **대화형 프로세스** 테스트를 실행할 때 비디오 기록을 만들거나 코딩된 UI 테스트와 같이 데스크톱과 상호 작용해야 하는 자동화된 테스트를 실행하려면 **대화형 프로세스**를 선택합니다. 그러면 테스트 에이전트가 서비스 대신 대화형 프로세스로 시작됩니다.

     다음 페이지에서 테스트 에이전트가 프로세스로 시작되면 사용자에 대한 세부 정보 및 기타 옵션을 입력합니다.

    1. **사용자 이름**에 이름을 입력합니다.

    2. **암호**에 암호를 입력합니다.

        > [!NOTE]
        > 현재 활성화되지 않은 다른 사용자를 사용하여 테스트 에이전트를 대화형 프로세스로 실행하도록 구성하는 경우 컴퓨터를 다시 시작한 후 다른 사용자로 로그온해야 에이전트를 시작할 수 있습니다. 또한 사용자 계정에 대해 null 암호가 지원되지 않습니다. IntelliTrace 수집기 또는 네트워크 에뮬레이션을 사용하려면 사용자 계정이 Administrators 그룹의 멤버여야 합니다.

        |**중요한 사용자 계정 정보**|
        |--------------------------------------------|
        |- 사용자 계정에 대한 Null 암호는 지원되지 않습니다.|
        |- IntelliTrace 또는 네트워크 에뮬레이션 진단 데이터 어댑터를 사용하려면 사용자 계정이 Administrators 그룹의 멤버여야 합니다. 테스트 에이전트를 실행하는 컴퓨터에서 최소 권한 사용자 계정이 있는 OS가 있는 경우에도 관리자 권한(높은 권한)으로 실행해야 합니다.|
        |- 에이전트 사용자 이름이 에이전트 서비스에 없으면 해당 사용자 이름이 추가됩니다. 이 경우 테스트 컨트롤러에 대한 사용 권한이 필요합니다.|
        |- 테스트 컨트롤러를 사용하려는 사용자는 테스트 컨트롤러의 사용자 계정에 있어야 합니다. 그렇지 않으면 컨트롤러에 대한 테스트를 실행할 수 없습니다.|

    3. 테스트 에이전트가 있는 컴퓨터를 다시 시작한 후에도 이 컴퓨터에서 테스트를 실행할 수 있도록 하려면 테스트 에이전트 사용자로 자동으로 로그온하도록 컴퓨터를 설정하면 됩니다. **자동 로그온**을 선택합니다. 이렇게 하면 사용자 이름과 암호가 레지스트리에 암호화된 형태로 저장됩니다.

    4. 데스크톱과 상호 작용해야 하는 자동화된 테스트를 방해하지 않도록 화면 보호기를 해제하려면 **화면 보호기를 사용하지 않도록 설정**을 선택합니다.

        > [!WARNING]
        > 자동으로 로그온하거나 화면 보호기를 해제하는 데는 보안 위험이 뒤따릅니다. 자동 로그온 기능을 사용하도록 설정한 경우 다른 사용자가 이 컴퓨터를 시작하고 미리 구성되어 있는 계정을 사용하여 자동으로 로그온할 수 있습니다. 화면 보호기를 사용하지 않도록 설정한 경우 사용자가 로그온하지 않더라도 컴퓨터가 잠금 해제될 수 있습니다. 이렇게 되면 컴퓨터에 물리적으로 접근할 수 있는 아무나 컴퓨터에 액세스할 수 있습니다. 컴퓨터에서 자동 로그온 기능을 사용하거나 화면 보호기를 해제할 때는 해당 컴퓨터가 물리적으로 안전하게 보호되는지 확인해야 합니다. 예를 들어 출입이 제한된 실험실의 컴퓨터는 실제로 안전하다고 볼 수 있습니다. (**화면 보호기를 사용하지 않도록 설정**의 선택을 취소하더라도 화면 보호기를 사용하도록 설정되지는 않습니다.)

3. 이 에이전트를 다른 테스트 컨트롤러에 등록하려면 **테스트 컨트롤러에 등록**을 선택합니다. **다음 테스트 컨트롤러에 테스트 에이전트 등록**에 테스트 컨트롤러의 이름을 입력하고 **콜론(:)**과 사용할 포트 번호를 차례로 입력합니다. 예를 들어 **agent1:6901**을 입력합니다.

    > [!NOTE]
    > 기본 포트 번호는 6901입니다.

4. 변경 내용을 저장하려면 **설정 적용**을 선택합니다. **구성 요약** 대화 상자를 닫은 다음, 테스트 에이전트 구성 도구를 닫습니다.

> [!WARNING]
> 다른 테스트 컨트롤러에서 실행하도록 현재 에이전트가 구성되어 있으면 해당 컨트롤러에서 테스트 에이전트를 제거해야 합니다.

## <a name="remove-a-test-agent-from-a-test-controller"></a>테스트 컨트롤러에서 테스트 에이전트 제거

테스트 에이전트를 제거하려면 먼저 이를 오프라인 상태로 설정해야 합니다.

> [!NOTE]
> 이 절차를 사용하여 컨트롤러에 랩 환경의 일부로 등록된 에이전트를 제거할 수 없습니다. 컨트롤러에서 이러한 에이전트를 제거하려면 Microsoft Test Manager를 사용하여 환경을 제거해야 합니다.

### <a name="to-remove-a-test-agent-from-a-test-controller"></a>테스트 컨트롤러에서 테스트 에이전트를 제거하려면

1. 테스트 컨트롤러가 팀 프로젝트에 등록되어 있지 않으면 다음 단계를 따릅니다.

    1. Visual Studio에서 테스트 프로젝트의 테스트 설정 파일을 열고 **역할**을 선택한 다음, **컨트롤러** 필드의 드롭다운에서 **테스트 컨트롤러 관리**를 선택합니다.

         **테스트 컨트롤러 관리** 대화 상자가 나타납니다.

    2. **컨트롤러** 드롭다운 목록에 테스트 컨트롤러가 설정된 컴퓨터의 이름을 입력합니다. 앞서 특정 테스트 컨트롤러를 관리한 적이 있으면 목록에서 해당 이름을 선택할 수 있습니다.

    3. **에이전트** 창에서 테스트 에이전트 이름을 선택합니다. 에이전트가 아직 온라인 상태이면 **오프라인**을 선택합니다. 제거하려면 **제거**를 선택합니다.

        > [!NOTE]
        > 테스트 에이전트를 제거하면 테스트 컨트롤러와의 연결만 끊어집니다. 테스트 에이전트를 완전히 제거하려면 테스트 에이전트 컴퓨터에서 **프로그램 및 기능** 제어판을 사용합니다.

2. 테스트 컨트롤러가 팀 프로젝트에 등록된 경우 Microsoft Test Manager를 사용하여 에이전트를 제거합니다.

## <a name="change-the-settings-for-a-test-agent"></a>테스트 에이전트의 설정 변경

테스트 에이전트의 상태는 다음 값 중 하나가 될 수 있습니다.

|상태|설명|
|------------|-----------------|
|테스트를 실행하는 중|테스트를 실행하고 있습니다.|
|준비됨|테스트를 실행하거나 데이터 및 진단 정보를 수집하는 데 사용할 수 있습니다.|
|오프라인|테스트를 실행하거나 데이터 및 진단 정보를 수집하는 데 사용할 수 없습니다.|
|연결 끊김|테스트 에이전트가 시작되지 않았습니다.|

다음 절차에 따라 테스트 에이전트의 상태나 기타 설정을 변경할 수 있습니다.

### <a name="to-change-the-settings-of-a-test-agent"></a>테스트 에이전트의 설정을 변경하려면

> [!NOTE]
> 테스트 에이전트가 테스트 컨트롤러에 등록되어 있고 해당 테스트 컨트롤러가 팀 프로젝트에 등록되어 있으면 Microsoft Test Manager에서 설정을 변경합니다.

1. 부하 테스트의 테스트 컨트롤러 및 등록된 에이전트를 구성하고 모니터링하려면 Visual Studio에서 **부하 테스트** 메뉴를 선택한 다음, **테스트 컨트롤러 관리**를 선택합니다. 기타 테스트의 경우에는 Visual Studio에서 테스트 프로젝트의 테스트 설정 파일을 열고 **역할**을 선택한 다음, **컨트롤러** 필드의 드롭다운에서 **테스트 컨트롤러 관리**를 선택합니다.

   **테스트 컨트롤러 관리** 대화 상자가 열립니다.

1. 변경할 테스트 에이전트가 등록되어 있는 테스트 컨트롤러의 이름을 테스트 컨트롤러 목록에서 선택합니다. 목록에 테스트 컨트롤러가 표시되지 않으면 테스트 컨트롤러를 올바르게 등록했는지 확인합니다. 자세한 내용은 테스트 컨트롤러를 구성하는 방법에 대한 절차를 참조하십시오.

1. (선택 사항) **테스트 에이전트** 창에서 속성을 변경할 테스트 에이전트 컴퓨터를 선택합니다.

1. **속성**을 선택합니다.

1. 필요에 따라 다음 테스트 에이전트 속성을 변경합니다.

|테스트 에이전트 속성|설명|
|-------------------------|-----------------|
|**가중치**|성능 수준이 각기 다른 여러 테스트 에이전트를 사용하는 경우 부하를 분산하는 데 사용합니다. 예를 들어 가중치가 100인 테스트 에이전트에는 가중치가 50인 테스트 에이전트보다 두 배 많은 부하가 걸립니다.|
|**IP 전환**|IP 전환을 구성하는 데 사용됩니다. IP 전환 기능을 사용하면 테스트 에이전트에서 IP 주소 범위를 사용하여 서버에 요청을 보낼 수 있습니다. 이를 통해 여러 클라이언트 컴퓨터에서 발생하는 호출을 시뮬레이션할 수 있습니다.<br /><br /> 부하 테스트에서 웹 팜에 액세스하는 경우 IP 전환이 중요합니다. 대부분의 부하 균형 도구에서는 클라이언트의 IP 주소를 사용하여 클라이언트와 특정 웹 서버 사이의 선호도를 설정합니다. 모든 요청이 클라이언트 하나에서 생성되면 부하 균형 도구에서 부하 균형을 조정하지 않습니다. 웹 팜에서 부하를 잘 분산하려면 요청이 특정 IP 주소에 편중되지 않도록 해야 합니다. **참고:** 네트워크 어댑터를 지정하거나 **(모두 지정되지 않음)**을 사용하여 현재 사용되지 않는 항목을 자동으로 선택할 수 있습니다. <br /><br /> IP 전환 기능을 사용하려면 해당 에이전트 컴퓨터에서 관리자 그룹의 사용자로 Visual Studio 테스트 에이전트 서비스를 실행해야 합니다. 이 사용자는 에이전트를 설치하는 동안 선택되지만 서비스 속성을 수정한 후 서비스를 다시 시작하여 변경할 수 있습니다.<br /><br /> IP 전환 기능이 올바르게 작동하는지 확인하려면 웹 서버에서 IIS 로깅을 사용하도록 설정하고 사용자가 구성한 IP 주소로부터 요청이 들어오는지 여부를 IIS 로깅 기능을 사용하여 확인합니다.|
|**특성**|테스트 에이전트를 선택하는 데 사용할 수 있는 이름/값 쌍의 집합입니다. 예를 들어, 테스트에서 특정 OS가 필요할 수 있습니다. 테스트 설정 파일의 **역할** 탭에 특성을 추가한 다음, 특성이 일치하는 테스트 에이전트를 선택하는 데 사용할 수 있습니다. 여러 컴퓨터에서 테스트를 실행하려는 경우 테스트를 실행하도록 구성된 테스트 설정 역할에 특성을 만든 다음, 해당 역할에서 사용하려는 각 테스트 에이전트에서 일치하는 특성을 구성합니다. **참고:** 이러한 특성은 Visual Studio에 대한 테스트 설정에서만 사용되기 때문에 이 설정은 팀 프로젝트에 등록되지 않은 테스트 컨트롤러에 등록되어 있는 테스트 에이전트에서만 사용할 수 있습니다.|

테스트 에이전트 가중치 및 테스트 에이전트 특성 변경 내용은 곧바로 적용되지만 실행 중인 테스트에는 영향을 주지 않습니다. IP 주소 범위를 적용하려면 테스트 컨트롤러를 다시 시작해야 합니다.

(선택 사항) 테스트 에이전트의 상태를 변경하려면 목록에서 에이전트를 선택하고 에이전트의 현재 상태를 기준으로 사용 가능한 선택 항목 중 필요한 작업을 선택합니다.

> [!NOTE]
> 테스트 에이전트가 프로세스로 실행되고 있으면 테스트 에이전트가 설치된 컴퓨터에서 실행되는 알림 영역 아이콘을 통해 테스트 에이전트의 상태를 관리할 수 있습니다. 이 알림 영역에는 테스트 에이전트의 상태가 표시됩니다. 테스트 에이전트가 이 도구를 사용하여 프로세스로 실행되는 경우 테스트 에이전트를 시작하거나 중지하거나 다시 시작할 수 있습니다. 테스트 에이전트가 실행 중이 아닌 경우 프로세스로 시작하려면 **시작**, **모든 프로그램**, **Microsoft Visual Studio** , **Microsoft Visual Studio Test Agent**를 차례로 선택합니다. 이렇게 하면 알림 영역 아이콘이 추가됩니다.

## <a name="configure-a-test-controller"></a>테스트 컨트롤러 구성

테스트 컨트롤러를 구성하려면 **팀 테스트 컨트롤러 구성 도구**를 사용해야 합니다. 테스트 컨트롤러를 구성할 때 테스트 컨트롤러를 다른 팀 프로젝트 컬렉션에 등록하거나 팀 프로젝트 컬렉션에서 테스트 컨트롤러의 등록을 취소할 수 있습니다.

테스트 컨트롤러를 Team Foundation Server 프로젝트 컬렉션에 등록하려면 테스트 컨트롤러 서비스에 사용하는 계정이 팀 프로젝트 컬렉션에 대한 Project Collection Test Service Accounts 그룹의 멤버이거나, 테스트 컨트롤러 구성 도구를 실행하는 데 사용하는 계정이 Project Collection Administrator여야 합니다.

> [!NOTE]
> 팀 프로젝트 컬렉션의 기존 환경을 사용하는 팀 프로젝트 컬렉션에서 테스트 컨트롤러의 등록을 취소할 경우, 해당 팀 프로젝트 컬렉션을 이동한 후 이동한 팀 프로젝트 컬렉션에 대한 테스트 컨트롤러를 다시 등록하면 해당 환경이 여전히 유지 관리됩니다.

### <a name="to-configure-a-test-controller"></a>테스트 컨트롤러를 구성하려면

1. 언제든 테스트 컨트롤러를 다시 구성하기 위해 도구를 실행하려면 **시작** > **모든 프로그램** >  **Microsoft Visual Studio** > **Microsoft Visual Studio Test Controller 구성 도구**를 차례로 선택합니다.

     **테스트 컨트롤러 구성** 대화 상자가 표시됩니다.

2. 테스트 컨트롤러 서비스에 대한 로그온 계정으로 사용할 사용자를 선택합니다.

    > [!NOTE]
    > 사용자 계정에 대한 Null 암호는 지원되지 않습니다.

4. (선택 사항) 랩 환경에서 테스트 컨트롤러를 사용하지 않고 Visual Studio에서만 테스트를 실행하려면 **팀 프로젝트 컬렉션에 등록**을 선택 취소합니다.

5. (선택 사항) 부하 테스트를 위한 테스트 컨트롤러를 구성하려면 **부하 테스트 구성**을 선택합니다. 그런 다음, SQL Server 인스턴스를 **다음 SQL Server에서 부하 테스트 결과 데이터베이스 만들기**에 입력합니다.

> [!NOTE]
> 테스트 컨트롤러에 대한 자세한 문제 해결 정보는 [테스트 에이전트 설치 및 구성](../test/lab-management/install-configure-test-agents.md)을 참조하세요.

## <a name="manage-your-agents-when-you-run-your-tests-with-a-test-controller"></a>테스트 컨트롤러와 함께 테스트를 실행할 때 에이전트 관리

Visual Studio의 테스트 설정에 응용 프로그램의 역할을 추가할 때 각 역할에 대한 에이전트 속성을 추가할 수 있습니다. 이에 따라 이 역할에 사용할 수 있는 테스트 에이전트가 결정됩니다. 이러한 테스트 설정을 사용해서 테스트를 실행할 때는 테스트 설정에 대해 선택한 테스트 컨트롤러에 따라 필요한 에이전트의 사용 가능 여부가 결정됩니다. 에이전트의 사용 가능 여부를 확인할 때 발생할 수 있는 상황은 다음과 같습니다.

-   테스트를 실행해야 할 역할에 사용할 수 있는 에이전트가 없습니다. 이 경우 테스트를 실행할 수 없습니다. 다음 작업 중 하나를 수행한 후 테스트를 다시 실행해야 합니다.

    -   이 역할에 대해 에이전트를 사용할 수 있게 될 때까지 기다린 후 테스트를 실행합니다.

    -   이 역할에 사용할 수 있는 에이전트가 오프라인 상태이면 에이전트를 다시 시작한 후 사용할 수 있습니다.

    -   해당 역할에 맞는 올바른 에이전트 속성이 설정된 다른 에이전트를 테스트 컨트롤러에 추가합니다.

    -   테스트 설정의 이 역할에 대한 에이전트 속성을 변경하여 다른 에이전트를 사용할 수 있도록 합니다.

-   진단 데이터 어댑터를 실행하는 하나 이상의 역할에 사용할 수 있는 에이전트가 없습니다. 이 경우 테스트를 실행할 수 있지만 진단 데이터 어댑터는 실행할 수 없습니다. 진단 데이터 어댑터 없이 테스트를 실행하거나 다음 작업 중 하나를 수행한 후 테스트를 다시 실행해야 합니다.

    -   해당 역할에 대해 에이전트를 사용할 수 있게 될 때까지 기다립니다.

    -   이 역할에 사용할 수 있는 에이전트가 오프라인 상태이면 **테스트** 메뉴의 **테스트 컨트롤러 관리**에서 에이전트의 상태를 온라인으로 변경합니다. 컨트롤러에서 에이전트의 연결이 끊어졌으면 에이전트를 다시 시작해야 합니다.

    -   이 테스트 실행에 필요한 에이전트에서 다른 테스트를 실행하고 있지 않은지 확인합니다. 에이전트의 상태는 **테스트** 메뉴의 **테스트 컨트롤러 관리**에서 확인할 수 있습니다.

    -   해당 역할에 맞는 올바른 에이전트 속성이 설정된 다른 에이전트를 테스트 컨트롤러에 추가합니다.

    -   테스트 설정의 해당 역할에 대한 에이전트 속성을 변경하여 다른 에이전트를 사용할 수 있도록 합니다.

## <a name="load-tests-from-delay-signed-assemblies"></a>서명이 연기된 어셈블리에서 부하 테스트

테스트 컨트롤러 및 테스트 에이전트는 강력하게 서명된 어셈블리이거나 서명되지 않은 어셈블리인 테스트 어셈블리만 로드할 수 있습니다. 일부 테스트 어셈블리는 응용 프로그램의 프로덕션 어셈블리에 액세스할 수 있어야 하기 때문에 서명이 연기되어 있습니다. 하지만 이러한 어셈블리는 테스트 어셈블리일 뿐이며 배포되지 않기 때문에 강력하게 서명되지 않습니다. 이러한 어셈블리는 서명이 연기되었기 때문에 로드될 수 없습니다. 따라서 테스트 컨트롤러 컴퓨터를 비롯하여 어셈블리가 로드될 모든 컴퓨터에서 이러한 어셈블리에 대해 강력한 이름 확인을 사용하지 않도록 해야 합니다. 서명이 연기된 확인을 사용하지 않으려면 sn.exe를 사용하십시오. 강력한 이름 확인을 건너뛰도록 요청되는 서명이 연기된 어셈블리의 공개 키 토큰이 포함되어야 할 수도 있습니다.

Sn.exe(강력한 이름 도구)를 사용하여 서명이 연기된 확인을 사용하지 않도록 합니다.

이렇게 하면 명령을 실행하는 컴퓨터에서 지정한 어셈블리에서만 강력한 이름 확인이 해제됩니다. 이렇게 하려면 충분한 권한이 있어야 합니다.

테스트 실행이 완료된 후 SN.exe 명령을 사용하여 서명이 연기된 확인을 다시 사용해야 합니다.

서명 확인을 해제하거나 다시 사용할 때는 스크립트에서 SN.exe 명령을 사용하는 것이 좋습니다. 설정 스크립트에서 확인을 해제하고 정리 스크립트에서 확인을 다시 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [테스트 에이전트 설치 및 구성](../test/lab-management/install-configure-test-agents.md)