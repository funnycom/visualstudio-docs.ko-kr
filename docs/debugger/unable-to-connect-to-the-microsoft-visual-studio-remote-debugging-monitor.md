---
title: "Microsoft Visual Studio 원격 디버깅 모니터에 연결할 수 없습니다. | Microsoft Docs"
ms.custom: 
ms.date: 08/24/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.error.remote_debug
- vs.debug.error.firewall.remotemachine
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 6efbb27052dc837ab10a74d8f43e949dfb816190
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="unable-to-connect-to-the-microsoft-visual-studio-remote-debugging-monitor"></a>Unable to Connect to the Microsoft Visual Studio Remote Debugging Monitor
이 메시지는 원격 디버깅 모니터는 하지 제대로 설정 원격 컴퓨터에서 또는 원격 컴퓨터에 네트워크 문제 또는 방화벽으로 인해 액세스할 수 없기 때문에 발생할 수 있습니다.
  
> [!IMPORTANT]
>  제품 버그 때문에이 메시지가 수신 되었다고 생각 되는 경우 다음 문의 [이 문제를 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) Visual Studio로 합니다. 자세한 도움말이 필요한 경우 [Talk to Us](../ide/talk-to-us.md) 에서 Microsoft에 문의하는 방법을 참조하세요.

## <a name="specificerrors"></a>자세한 오류 메시지는 무엇입니까?

`Unable to Connect to the Microsoft Visual Studio Remote Debugging Monitor` 메시지는 일반 합니다. 일반적으로 더 구체적인 메시지 오류 문자열에 포함 되며 문제 또는 보다 정확 하 게 수정 프로그램에 대 한 검색의 원인을 파악 하는 데 도움이 되. 다음은 몇 주 오류 메시지에 추가 하는 일반적인 오류 메시지:

- [디버거는 원격 컴퓨터에 연결할 수 없습니다. 디버거가 지정 된 컴퓨터 이름을 확인할 수 없습니다.](#cannot_connect)
- [원격 디버거 연결 요청을 거부 했습니다.](#rejected)
- [메모리 위치에 대 한 잘못 된 액세스](#invalid_access)
- [원격 컴퓨터에서 실행 중인 지정된 된 이름으로 서버인](#no_server)
- [요청한 이름이 올바르지만 요청 된 형식의 데이터가 없습니다.](#valid_name)
- [대상 컴퓨터에 Visual Studio 원격 디버거는이 컴퓨터에 다시 연결할 수 없습니다.](#cant_connect_back)
- [액세스가 거부 되었습니다.](#access_denied)
- [보안 패키지 관련 오류가 발생 했습니다.](#security_package)

## <a name="cannot_connect"></a>디버거는 원격 컴퓨터에 연결할 수 없습니다. 디버거가 지정 된 컴퓨터 이름을 확인할 수 없습니다.

다음이 단계를 시도해 보십시오.

1. 올바른 컴퓨터 이름을 입력 하 고 포트 번호에 있는지 확인는 **프로세스에 연결** 대화 상자 또는 프로젝트 속성 (참조 속성을 설정 하려면 [이러한 단계](#server_incorrect)). 컴퓨터 이름에는 다음과 같은 형식 이어야 합니다.

    `computername:port`

    > [!NOTE]
    > 포트 번호와 일치 해야는 [포트 번호의 원격 디버거](../debugger/remote-debugger-port-assignments.md), 어떤 *실행 중 이어야 합니다* 대상 컴퓨터에 있습니다.

2. 컴퓨터 이름을 작동 하지 않는 경우 IP 주소를 시도 하 고 포트 번호 대신 합니다.

3. 대상 컴퓨터에서 실행 되는 원격 디버거 버전이 Visual Studio 버전에 일치 하는지 확인 합니다. 올바른 버전의 원격 디버거를 가져오려는 참조 [원격 디버깅](../debugger/remote-debugging.md)합니다.

    > [!TIP]
    > 프로세스에 연결 하는 성공적으로 연결 되었지만 원하는 프로세스에 표시 되지 않으면 경우 선택 된 **모든 사용자가 확인란의 프로세스 표시**합니다. 이 프로세스는 다른 사용자 계정으로 연결 된 경우를 표시 됩니다.

4. 이 오류가 해결 되지 않으면 경우 참조 [원격 컴퓨터에 연결할 수 없기](#dns)합니다.

## <a name="rejected"></a>원격 디버거 연결 요청을 거부 했습니다.

에 **프로세스에 연결** 대화 상자 또는 프로젝트 속성에서 원격 컴퓨터 이름 및 포트 번호와 원격 디버거 창에 표시 된 이름 및 포트 번호 일치 하는지 확인 합니다. 잘못 된, 수정 하 고 다시 시도 하십시오.

이러한 값은 올바른 경우 메시지에 언급 **Windows 인증** 모드, 원격 디버거에 올바른 인증 모드에 있는 확인 (**도구 > 옵션**).

## <a name="invalid_access"></a>메모리 위치에 대 한 잘못 된 액세스

내부 오류가 발생 했습니다. Visual Studio를 다시 시작 하 고 다시 시도 하십시오.

## <a name="no_server"></a>원격 컴퓨터에서 실행 중인 지정된 된 이름으로 서버인

Visual Studio 원격 디버거에 연결할 수 없습니다. 이 메시지는 여러 가지 이유로 발생할 수 있습니다.

- 다른 사용자 계정으로 원격 디버거를 실행할 수 있습니다. 참조 [다음이 단계](#user_accounts)

- 포트가는 방화벽에서 차단 됩니다. 방화벽은 있는지 확인 [요청을 차단 하지](#firewall)타사 방화벽을 사용 하는 경우에 특히, 합니다.

- 원격 디버거 버전이 Visual Studio 일치 하지 않습니다. 올바른 버전의 원격 디버거를 가져오려면 참조 [원격 디버깅](../debugger/remote-debugging.md)


## <a name="#valid_name"></a>요청한 이름이 올바르지만 요청 된 형식의 데이터가 없습니다.

원격 컴퓨터 존재 하지만 Visual Studio 원격 디버거에 연결할 수 없습니다. 이 메시지는 여러 가지 이유로 발생할 수 있습니다.

- DNS 문제 때문에 연결 합니다. 참조 [이러한 단계](#dns)합니다.

- 다른 사용자 계정으로 원격 디버거를 실행할 수 있습니다. 에 따라 [이러한 단계](#user_accounts)합니다.

- 포트가는 방화벽에서 차단 됩니다. 방화벽은 있는지 확인 [요청을 차단 하지](#firewall)타사 방화벽을 사용 하는 경우에 특히, 합니다.

- 원격 디버거 버전이 Visual Studio 일치 하지 않습니다. 올바른 버전의 원격 디버거를 가져오려는 참조 [원격 디버깅](../debugger/remote-debugging.md)합니다.

## <a name="cant_connect_back"></a>대상 컴퓨터에 Visual Studio 원격 디버거는이 컴퓨터에 다시 연결할 수 없습니다.

다른 사용자 계정으로 원격 디버거를 실행할 수 있습니다. 원격 디버거를 열고 **도구 > 권한을** 원격 디버거의 사용 권한에 사용자를 추가 하려면. 자세한 내용은 참조 [원격 디버거가 다른 사용자 계정으로 실행 되 고](#user_accounts)합니다.

또한 오류 메시지가 방화벽을 설명, 로컬 컴퓨터의 방화벽이 Visual Studio로 다시 원격 컴퓨터에서 통신을 방해할 수 수 있습니다. 참조 [이러한 단계](#firewall)합니다.

## <a name="access_denied"></a>액세스가 거부 되었습니다.

(지원 되지 않음) 32 비트 컴퓨터에서 64 비트 원격 컴퓨터에서 디버깅 하려는 경우이 오류가 표시 될 수 있습니다.

## <a name="security_package"></a>보안 패키지 관련 오류가 발생 했습니다.

Windows XP 및 Windows 7에 특정 레거시 문제일 수 있습니다. 이 참조 [정보](https://stackoverflow.com/questions/4786016/unable-to-connect-to-the-microsoft-remote-debugging-monitor-a-security-package)합니다. 

## <a name="causes-and-recommendations"></a>원인 및 권장 사항

### <a name="dns"></a>원격 컴퓨터에 연결할 수 없습니다. 

원격 컴퓨터 이름을 사용 하 여 연결할 수 없는 경우 IP 주소를 대신 사용해 보세요. 사용할 수 있습니다 `ipconfig` IPv4 주소를 얻기 위해 원격 컴퓨터에는 명령줄에서입니다. 호스트 파일을 사용 하는 경우 올바르게 구성 되어 있는지 확인 합니다.

실패할 경우 원격 컴퓨터를 네트워크에 액세스할 수 있는지 확인 하십시오 ([ping](https://technet.microsoft.com/en-us/library/cc732509(v=ws.10).aspx) 원격 컴퓨터). 인터넷을 통해 원격 디버깅이 지원 되지 않는 일부 Microsoft Azure 시나리오를 제외 하 고 있습니다.
  
### <a name="server_incorrect"></a>서버 이름이 잘못 되었거나 제 3 자 소프트웨어 방해 하는 원격 디버거

Visual Studio에서 프로젝트 속성을 보고 하 고 서버 이름이 올바른지 확인 합니다. 에 대 한 항목을 참조 [C# 및 Visual Basic](../debugger/remote-debugging-csharp.md#remote_csharp) 및 [c + +](../debugger/remote-debugging-cpp.md#remote_cplusplus)합니다. Asp.net, 열고 **속성 / 웹 / 서버** 또는 **속성 /debug** 프로젝트 형식에 따라 합니다.

> [!NOTE]
> 프로세스에 연결 하는 경우 프로젝트 속성에서 원격 설정은 사용 되지 않습니다.

서버 이름이 올바른지, 바이러스 백신 소프트웨어 또는 타사 방화벽 원격 디버거를 차단 될 수 있습니다. 로컬로 디버그 하는 경우 Visual Studio는 32 비트 응용 프로그램, 있으므로 64 비트 응용 프로그램을 디버깅 하려면 64 비트 버전의 원격 디버거를 사용 하기 때문에이 발생할 수 있습니다. 32 비트 및 64 비트 프로세스는 로컬 컴퓨터 내의 로컬 네트워크를 사용 하 여 통신 합니다. 컴퓨터에서 나가는 네트워크 트래픽이 없지만 타사 보안 소프트웨어가 통신을 차단할 수 있습니다.

### <a name="user_accounts"></a>원격 디버거가 다른 사용자 계정으로 실행 되 

원격 디버거를 기본적으로만 연결을에서 허용할 Administrators 그룹의 구성원과 원격 디버거를 시작한 사용자입니다. 추가 사용자에 게 사용 권한은 명시적으로 부여 되어야 합니다. 
 
다음 방법 중 하나를 사용하여 이 문제를 해결할 수 있습니다.  

-   Visual Studio 사용자를 원격 디버거의 사용 권한에 추가 (원격 디버거 창에서 선택 **도구 > 권한을**).

-   원격 컴퓨터에서 동일한 사용자 계정으로 Visual Studio 컴퓨터에서 사용 하는 암호를 원격 디버거를 다시 시작 합니다.

    > [!NOTE]
    > 원격 서버에 원격 디버거를 실행 하는 경우 원격 디버거 응용 프로그램을 마우스 오른쪽 단추로 클릭 하 고 선택 **관리자 권한으로 실행** (또는 원격 디버거를 서비스로 실행할 수 있습니다). 원격 서버에서 실행 되지 않는 경우 바로 정상적으로 시작 합니다.
  
-   사용 하 여 명령줄에서 원격 디버거를 시작할 수 있습니다는 **허용 / \<사용자 이름 >** 매개 변수: `msvsmon /allow <username@computer>`합니다. 
  
-   또는 모든 사용자가 원격으로 디버깅할 수 있습니다. 원격 디버거 창에서 이동 하 여 **도구 > 옵션** 대화 상자. **인증 안 함**을 선택하는 경우 **모든 사용자가 디버깅할 수 있도록 허용**을 선택할 수 있습니다. 그러나 다른 옵션은 실패 하는 경우에 또는 개인 네트워크에 있는 경우이 옵션을 시도해 야.

### <a name="firewall"></a>원격 컴퓨터의 방화벽이 원격 디버거로 들어오는 연결을 허용 하지 않습니다.  
 Visual Studio와 원격 디버거 간의 통신을 허용하도록 Visual Studio 컴퓨터의 방화벽 및 원격 컴퓨터의 방화벽을 구성해야 합니다. 원격 디버거에서 사용 중인 포트에 대한 자세한 내용은 [Remote Debugger Port Assignments](../debugger/remote-debugger-port-assignments.md)을 참조하세요. Windows 방화벽을 구성하는 방법에 대한 자세한 내용은 [Configure the Windows Firewall for Remote Debugging](../debugger/configure-the-windows-firewall-for-remote-debugging.md)을 참조하세요.
  
### <a name="the-version-of-the-remote-debugger-doesnt-match-the-version-of-visual-studio"></a>버전의 원격 디버거가 Visual Studio의 버전과 일치 하지  
 로컬로 실행하는 Visual Studio 버전이 원격 컴퓨터에서 실행되는 원격 디버깅 모니터 버전과 일치해야 합니다. 이 문제를 해결하려면 일치하는 버전의 원격 디버깅 모니터를 다운로드하여 설치합니다. 올바른 버전의 원격 디버거를 가져오려는 참조 [원격 디버깅](../debugger/remote-debugging.md)합니다.
  
### <a name="the-local-and-remote-machines-have-different-authentication-modes"></a>로컬 및 원격 컴퓨터의 인증 모드가 서로 다름  
 로컬 및 원격 컴퓨터에서 동일한 인증 모드를 사용해야 합니다. 이 문제를 해결하려면 두 컴퓨터에서 모두 동일한 인증 모드를 사용 중인지 확인합니다. 인증 모드를 변경할 수 있습니다. 원격 디버거 창에서 이동 하 여 **도구 > 옵션** 대화 상자.
  
 인증 모드에 대한 자세한 내용은 [Windows 인증 개요](https://technet.microsoft.com/en-us/library/hh831472.aspx)를 참조하세요.   
  
### <a name="anti-virus-software-is-blocking-the-connections"></a>바이러스 백신 소프트웨어가 연결을 차단함  
 Windows 바이러스 백신 소프트웨어는 원격 디버거 연결을 허용하지만 일부 타사 바이러스 백신 소프트웨어가 차단할 수도 있습니다. 이러한 연결을 허용하는 방법을 알아보려면 해당 바이러스 백신 소프트웨어에 대한 설명서를 확인합니다.  
  
### <a name="network-security-policy-is-blocking-communication-between-the-remote-machine-and-visual-studio"></a>네트워크 보안 정책에서 원격 컴퓨터와 Visual Studio 간의 통신을 차단함  
 네트워크 보안을 검토하여 통신을 차단하지 않는지 확인합니다. Windows 네트워크 보안 정책에 대 한 자세한 내용은 참조 [보안 정책 설정](/windows/device-security/security-policy-settings/security-policy-settings)합니다.  
  
### <a name="the-network-is-too-busy-to-support-remote-debugging"></a>네트워크 사용량이 너무 많아 원격 디버깅을 지원할 수 없음  
 다른 시간에 원격 디버깅을 수행하거나 다른 시간에 네트워크 작업을 다시 예약해야 할 수도 있습니다.  
  
## <a name="more-help"></a>자세한 도움말  
 더 많은 원격 디버거 도움말을 가져오려면 원격 디버거의 도움말 페이지를 엽니다 (**도움말 > 사용량** 원격 디버거에서).
  
## <a name="see-also"></a>참고 항목  
 [원격 디버깅](../debugger/remote-debugging.md)