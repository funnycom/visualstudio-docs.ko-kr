---
title: "명령줄 캡처 도구 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db75b3a7-80b2-4a74-91d2-fd6e0f73b45d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4290ccb1184f658d04d6903520f709384e58e837
ms.sourcegitcommit: 342e5ec5cec4d07864d65379c2add5cec247f3d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2018
---
# <a name="command-line-capture-tool"></a>명령줄 캡처 도구
DXCap.exe는 그래픽 진단 캡처 및 재생을 위한 명령줄 도구로, 모든 기능 수준에서 Direct3D 10 - Direct3D 12를 지원합니다.  
  
## <a name="syntax"></a>구문  
  
```ms-dos  
DXCap.exe [-file filename] [-frame frames | -period periods | -manual] -c app [args...]  
DXCap.exe -p [filename] [-debug | -warp | -hw] [-config] [-rawmode]  
DXCap.exe -p [filename] -screenshot [-frame frames]  
DXCap.exe -p [filename] -toXML [xml_filename]  
DXCap.exe -v [-file filename] [-examine events] [-haltonfail | -exitonfail] [-showprogress]  
DXCap.exe -e [search_string]  
DXCap.exe -info  
```  
  
#### <a name="parameters"></a>매개 변수  
 `-file` `filename`  
 캡처 모드 (`-c`), `filename` 그래픽 정보를 기록 된 그래픽 로그 파일의 이름을 지정 합니다. 경우 `filename` 를 지정 하지 않으면 그래픽 정보는 라는 파일에 기록 `<appname>-<date>-<time>.vsglog` 기본적으로 합니다.  
  
 유효성 검사(-v) 모드에서 `filename`은 유효성을 검사할 그래픽 로그 파일의 이름을 지정합니다. `filename`을 지정하지 않으면 마지막으로 유효성을 검사한 그래픽 로그를 다시 사용합니다.  
  
 `-frame` `frames`  
 캡처 모드에서 `frames`는 캡처하려는 프레임을 지정합니다. 첫 번째 프레임은 1입니다. 쉼표 및 범위를 사용하여 여러 프레임을 지정할 수 있습니다. 예를 들어 경우 `frames` 은 `2, 5, 7-9, 15`, 프레임 `2`, `5`, `7`, `8`, `9`, 및 `15` 캡처됩니다.  

> [!TIP]
> 사용 하 여 `-frame` `manual` Print Screen 키를 눌러 프레임을 수동으로 캡처될를 지정할 수 있습니다. 앱이 시작될 때 프레임을 캡처할 수 있습니다. 프레임 캡처를 중지하려면 명령줄 인터페이스로 돌아가서 Enter 키를 누릅니다.  
  
 `-period` `periods`  
 캡처 모드에서 `periods`는 프레임을 캡처할 시간 범위를 초 단위로 지정합니다. 쉼표 및 범위를 사용하여 여러 기간을 지정할 수 있습니다. 예를 들어 경우 `periods` 은 `2.1-5, 7.0-9.3`, 사이 렌더링 된 프레임 `2.1` 및 `5` 초,`7` 및 `9.3` 초 캡처됩니다.  
  
 `-c` `app` [`args...`]  
 캡처 모드입니다. 캡처 모드에서 `app`은 그래픽 정보를 캡처할 앱의 이름을 지정하고 `args...`는 해당 앱에 대한 추가 명령줄 매개 변수를 지정합니다.  
  
 `-p` [`filename`]  
 재생 모드 (`-p`). 재생 모드에서 `filename`은 재생할 그래픽 로그 파일의 이름을 지정합니다. `filename`을 지정하지 않으면 마지막으로 재생한 그래픽 로그를 다시 사용합니다.  
  
 `-debug`  
 재생 모드에서 `-debug` 재생을 사용 하도록 설정 하는 Direct3D 디버그 계층으로 수행 하도록 지정 합니다.  
  
 `-warp`  
 재생 모드에서 `-warp` WARP 소프트웨어 렌더러를 사용 하 여 재생을 수행 하도록 지정 합니다.  
  
 `-hw`  
 재생 모드에서 `-hw` GPU 하드웨어를 사용 하 여 재생을 수행 하도록 지정 합니다.  
  
 `-config`  
 재생 모드에서 `-config` 이 정보는 로그에 기록 된 경우 그래픽 로그 파일을 캡처하는 데 사용 된 컴퓨터에 대 한 정보를 표시 합니다.  
  
 `-rawmode`  
 재생 모드에서 `-rawmode` 기록된 된 이벤트를 수정 하지 않고 재생을 수행 하도록 지정 합니다. 일반 작업 시 재생 모드에서는 디버깅을 간소화하고 재생 속도를 높이기 위해 약간의 변경이 수행될 수 있습니다. 예를 들어 스왑 체인 명령을 실행하지 않고 스왑 체인 출력을 시뮬레이트할 수 있습니다. 이러한 변경은 일반적으로 문제가 되지 않지만 기록된 이벤트에 보다 적합한 방식으로 재생을 수행해야 할 수 있습니다. 예를 들어 이 옵션을 사용하면 전체 화면 모드로 실행하는 동안 캡처된 앱에 대해 전체 화면 렌더링 동작을 복원할 수 있습니다.  
  
 `-toXML` [`xml_filename`]  
 재생 모드에서 `xml_filename`은 재생의 XML 표현이 기록되는 파일의 이름을 지정합니다. `xml_filename`을 지정하지 않으면 XML 표현은 재생 중인 파일과 이름이 같은 파일에 기록되며 `.xml` 확장명이 지정됩니다.  
  
 `-v`  
 유효성 검사 모드입니다. 유효성 검사 모드에서 캡처된 프레임은 하드웨어와 WARP 둘 다에서 재생되며 이미지 비교 기능을 통해 해당 결과를 비교합니다. 이 기능을 사용하여 렌더링에 영향을 주는 드라이버 문제를 신속하게 파악할 수 있습니다.  
  
 `-examine` `events`  
 유효성 검사 모드에서 `events`는 즉각적인 결과를 비교할 그래픽 이벤트 집합을 지정합니다. 예를 들어 `-examine present,draw,copy,clear` 비교 하려면 해당 범주에 속하는 이벤트에만 제한 합니다.  
  
> [!TIP]
>  로 시작 하는 것이 좋습니다 `-examine present,draw,copy,clear` 때문에이 대부분의 문제를 표시 하지만 더 광범위 한 이벤트 집합이 보다 훨씬 더 적은 시간이 소요 됩니다. 필요한 경우 더 많은 이벤트 집합 또는 다른 이벤트 집합을 지정하여 해당 이벤트의 유효성을 검사하고 다른 종류의 문제를 확인할 수 있습니다.  
  
 `-haltonfail`  
 유효성 검사 모드에서 `-haltonfail` 하드웨어와 WARP 렌더러 간에 차이점이 검색 되 면 유효성 검사를 중지 합니다. 키를 누르면 유효성 검사를 다시 시작합니다.  
  
 `-exitonfail`  
 유효성 검사 모드에서 `-exitonfail` 은 하드웨어와 WARP 렌더러 간에 차이점이 검색 되 면 즉시 유효성 검사를 종료 합니다. 반환이 방식으로 종료 된 프로그램, `0` 환경; 그렇지 않으면 반환 `1`합니다.  
  
 `-showprogress`  
 유효성 검사 모드에서 `-showprogress` 유효성 검사 세션에 대 한 진행률 정보를 표시 합니다. 왼쪽에는 WARP 진행률이 표시되고 오른쪽에는 하드웨어 진행률이 표시됩니다.  
  
 `-e` `search_string`  
 설치 된 UWP 앱을 열거 합니다. UWP 앱으로 명령줄 캡처를 수행 하려면이 정보를 사용할 수 있습니다.  
  
 `-info`  
 컴퓨터 및 캡처 DLL에 대한 정보를 표시합니다.  
  
## <a name="remarks"></a>설명  
 DXCap.exe는 다음의 세 가지 모드로 작동합니다.  
  
 캡처 모드(-c)  
 실행 중인 앱에서 그래픽 정보를 캡처하여 그래픽 로그 파일에 기록합니다. 캡처 기능 및 파일 형식은 Visual Studio와 같습니다.  
  
 재생 모드(-p)  
 기존 그래픽 로그 파일에서 이전에 캡처한 그래픽 이벤트를 재생합니다. 기본적으로는 전체 화면 앱에서 그래픽 로그 파일을 캡처했더라도 재생은 창에서 수행됩니다. 전체 화면 앱에서 파일을 캡처한 그래픽 로그에 전체 화면에서 재생이 수행 및 `-rawmode` 지정 됩니다.  
  
 유효성 검사 모드 (`-v`)  
 하드웨어와 WARP 둘 다에서 캡처된 프레임을 재생한 다음 이미지 비교 기능을 사용하여 해당 결과를 비교하는 방법으로 렌더링 동작의 유효성을 검사합니다. 이 기능을 사용하여 렌더링에 영향을 주는 드라이버 문제를 신속하게 파악할 수 있습니다.  
  
 이러한 모드 이외에 dxcap.exe는 그래픽 정보 캡처 또는 재생을 수행하지 않는 두 가지 기타 기능을 수행합니다.  
  
 열거형 함수 (`-e`)  
 컴퓨터에 설치 하는 UWP 앱에 대 한 세부 정보를 표시 합니다. 이러한 세부 정보는 UWP 앱에서 실행 파일을 식별 하는 appid 및 패키지 이름이 포함 됩니다. DXCap.exe를 사용하여 windows 스토어 앱에서 그래픽 정보를 캡처하려면 데스크톱 앱을 캡처할 때 사용한 실행 파일 이름 대신 패키지 이름과 appid를 사용합니다.  
  
 정보 함수 (`-info)`  
 컴퓨터 및 캡처 DLL에 대한 세부 정보를 표시합니다.  
  
## <a name="examples"></a>예제  
  
### <a name="capture-graphics-information-from-a-desktop-app"></a>데스크톱 앱에서 그래픽 정보 캡처  
 사용 하 여 `-c` 그래픽 정보를 캡처할 앱을 지정할 수 있습니다.  
  
```ms-dos  
DXCap.exe -c BasicHLSL11.exe  
```  
  
 기본적으로 그래픽 정보는 라는 파일에 기록 `<appname>-<date>-<time>.vsglog`합니다. 사용 하 여 `-file` 를 기록할 다른 파일을 지정 합니다.  
  
```ms-dos  
DXCap.exe -file regression_test_12.vsglog -c BasicHLSL11.exe  
```  
  
 캡처할 앱에 대해 추가 명령줄 매개 변수를 지정하려면 앱 파일 이름 뒤에 해당 매개 변수를 포함합니다.  
  
```ms-dos  
DXCap.exe -c "C:\Program Files\Internet Explorer\iexplorer.exe" "www.fishgl.com"  
```  
  
 위의 예제에서 명령은 WebGL API를 사용 하 여 3 차원 콘텐츠를 렌더링 하는 www.fishgl.com에 있는 웹 페이지를 보는 동안 데스크톱 버전의 Internet Explorer에서 그래픽 정보를 캡처합니다.  
  
> [!NOTE]
>  사용 하기 전에 DXCap.exe 용 인수를 지정 해야 하므로 앱 다음에 표시 되는 명령줄 인수에 전달 하는 것은 `-c` 옵션입니다.  
  
### <a name="capture-graphics-information-from-a-uwp-app"></a>UWP 앱에서 그래픽 정보를 캡처하십시오.  
 UWP 앱에서 그래픽 정보를 캡처할 수 있습니다.  
  
```ms-dos  
DXCap.exe -c Microsof.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe,AppexMaps  
```  
  
 UWP 앱에서 캡처할 DXCap.exe를 사용 하는 것은 Windows 데스크톱 앱에서 캡처할 사용 방식과 비슷하지만 다음과 하지만 대신 UWP 앱 패키지 이름 및 이름으로 식별 데스크톱 응용 프로그램을 식별 하기 파일 이름으로, 또는 내의 실행 파일을 패키지의 id  캡처하십시오. 컴퓨터에 설치 된 UWP 앱을 식별 하는 방법을 알아보려면 좀 더 쉽게 사용 하 여는 `-e` DXCap.exe 옵션을 열거 합니다.  
  
```ms-dos  
DXCap.exe -e  
```  
  
 원하는 앱을 찾기 위해 선택적 검색 문자열을 입력할 수 있습니다. 검색 문자열을 입력 하면 DXCap.exe 패키지 이름, 응용 프로그램 이름 또는 앱 Id 검색 문자열과 일치 하는 UWP 앱을 열거 합니다. 검색은 대/소문자를 구분합니다.  
  
```ms-dos  
DXCap.exe -e map  
```  
  
 위의 명령은 "map"와 일치 하는 UWP 앱을 열거 출력은 다음과 같습니다.  
  
 **Package "Microsoft.BingMaps":**  
 **InstallDirectory : C:\Program Files\WindowsApps\Microsoft.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe**  
 **FullName         : Microsoft.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe**  
 **UserSID          : S-1-5-21-2127521184-1604012920-1887927527-5603533**  
 **Name             : Microsoft.BingMaps**  
 **Publisher        : CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US**  
 **버전: 2.1.2914.1734**  
 **시작 가능한 응용 프로그램:**  
 **Id   : AppexMaps**  
 **Exe  : C:\Program Files\WindowsApps\Microsoft.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe\Map.exe**  
 **IsWWA: No**  
 * * (시작)를 AppSpec: **DXCap.exe-c Microsoft.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe,AppexMaps*** 열거 된 각 응용 프로그램에 대 한 출력의 마지막 줄에서 그래픽 정보 캡처를 사용할 수 있습니다 명령이 표시 됩니다.  
  
### <a name="capture-specific-frames-or-frames-between-specific-times"></a>특정 프레임 또는 특정 시간 사이의 프레임 캡처  
 사용 하 여 `-frame` 쉼표 및 범위를 사용 하 여 캡처할 프레임 지정 하려면:  
  
```ms-dos  
DXCap.exe -frame 2,5,7-9,15 -c SimpleBezier11.exe  
```  
  
 또는 사용 하 여 `-period` 집합이 한 프레임을 캡처할 시간 범위를 지정할 수 있습니다. 시간 범위는 초로 지정되며 여러 범위를 지정할 수 있습니다.  
  
```ms-dos  
DXCap.exe -period 2.1-5, 7.0-9.3 -c SimpleBezier11.exe  
```  
  
### <a name="capture-frames-interactively"></a>대화형으로 프레임 캡처  
 사용 하 여 `-manual` 대화형으로 프레임을 캡처할 수 있습니다. 캡처를 시작하려면 Enter 키를 누릅니다. Enter 키를 다시 누르면 캡처가 중지됩니다.  
  
```ms-dos  
DXCap.exe -manual -c SimpleBezier11.exe  
```  
  
### <a name="play-back-a-graphics-log-file"></a>그래픽 로그 파일 재생  
 사용 하 여 `-p` 이전에 캡처한 그래픽 로그 파일을 재생 합니다.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog  
```  
  
 가장 최근에 캡처한 그래픽 로그를 재생하려면 파일 이름을 생략합니다.  
  
```ms-dos  
DXCap.exe -p  
```  
  
### <a name="play-back-in-raw-mode"></a>원시 모드에서 재생  
 사용 하 여 `-rawmode` 발생 했던 대로 정확 하 게 캡처된 명령을 재생 합니다. 일반 재생 시 특정 명령은 에뮬레이트됩니다. 예를 들어 전체 화면 앱에서 캡처한 그래픽 로그 파일이 창에서 재생됩니다. 그러나 원시 모드를 사용하도록 설정하면 동일한 파일이 전체 화면에서 재생됩니다.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog -rawmode  
```  
  
### <a name="play-back-using-warp-or-a-hardware-device"></a>WARP 또는 하드웨어 장치를 사용하여 재생  
 하드웨어 장치에서 캡처된 그래픽 로그 파일 재생 시 WARP를 사용하거나 WARP에서 캡처된 로그 재생 시 하드웨어 장치를 사용하도록 강제 지정할 수 있습니다. 사용 하 여 `-warp` WARP를 사용 하 여 재생할 수 있습니다.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog -warp  
```  
  
 사용 하 여 `-hw` 하드웨어를 사용 하 여 재생 합니다.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog -hw  
```  
  
### <a name="validate-a-graphics-log-file-against-warp"></a>WARP에 대해 그래픽 로그 파일 유효성 검사  
 유효성 검사 모드에서는 그래픽 로그 파일을 하드웨어와 WARP 둘 다에서 재생한 다음 해당 결과를 비교합니다. 따라서 드라이버에 의해 발생하는 렌더링 오류를 파악할 수 있습니다. WARP에 대해 그래픽 하드웨어의 올바른 동작 유효성을 검사 하려면-v를 사용 합니다.  
  
```ms-dos  
DXCap.exe -v regression_test_12.vsglog  
```  
  
 비교되는 결과의 양을 줄이려면 유효성 검사에 대해 비교할 명령 하위 집합을 지정할 수 있습니다. 그러면 다른 명령은 무시됩니다. -사용 하 여 결과 비교할 명령을 지정 하려면 검사 합니다.  
  
```ms-dos  
DXCap.exe -v regression_test_12.vsglog -examine present,draw,copy,clear  
```  
  
### <a name="convert-a-graphics-log-file-to-pngs"></a>그래픽 로그 파일을 PNG로 변환  
 그래픽 로그 파일에서 프레임을 확인하거나 분석하려는 경우 DXCap.exe에서 캡처한 프레임을 .png(이동식 네트워크 그래픽) 이미지 파일로 저장할 수 있습니다. 사용 하 여 `-screenshot` 에 출력 하려면 재생 모드에서 캡처된 프레임을.png 파일입니다.  
  
```ms-dos  
DXCap.exe -p BasicHLSL11.vsglog -screenshot  
```  
  
 사용 하 여 `-frame` 와 `-screenshot` 출력할 프레임을 지정할 수 있습니다.  
  
```ms-dos  
DXCap.exe -p BasicHLSL11.vsglog -screenshot -frame 5, 7-9  
```  
  
### <a name="convert-a-graphics-log-file-to-xml"></a>그래픽 로그 파일을 XML로 변환  
 FindStr, XSLT 등의 익숙한 도구를 사용하여 그래픽 로그를 처리 및 분석하려는 경우 DXCap.exe에서 그래픽 로그 파일을 XML로 변환할 수 있습니다. 사용 하 여 `-toXML` 로그를 재생 하는 대신 XML로 변환 하려면 재생 모드에서 다시 합니다.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog -toXML  
```  
  
 기본적으로 XML 출력은 그래픽 로그와 이름이 같은 파일에 기록되지만 확장명이 .xml로 지정됩니다. XML 파일의 이름은 위의 예제에서 **regression_test_12.xml**합니다. XML 파일에 다른 이름을 지정 하려면 후에 메서드를 지정 `-toXML`합니다.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog -toXML temp.xml  
```  
  
 결과 파일에는 다음과 같은 XML이 포함됩니다.  
  
```xml  
<Moment value="67"/>  
<Method name="CreateDXGIFactory1" >  
    <Return type="HRESULT" value="S_OK" />  
    <Parameter name="riid" type="IID" value="770AAE78-F26F-4DBA-A829-253C83D1B387" />  
    <Parameter name="ppFactory" type="void" handle="1" isOutput="true" />  
</Method>  
  
<Moment value="167"/>  
<Method name="D3D11CreateDevice" >  
    <Return type="HRESULT" value="S_OK" />  
    <Parameter name="pAdapter" type="IDXGIAdapter" handle="34" />  
    <Parameter name="DriverType" type="D3D_DRIVER_TYPE" value="D3D_DRIVER_TYPE_UNKNOWN" />  
    <Parameter name="Software" type="HMODULE" value="pointer" />  
    <Parameter name="Flags" type="UINT" value="0" />  
    <Parameter name="pFeatureLevels" type="D3D_FEATURE_LEVEL" arrSize="1" >  
        <Element value="D3D_FEATURE_LEVEL_11_0" />  
    </Parameter>  
    <Parameter name="FeatureLevels" type="UINT" value="1" />  
    <Parameter name="SDKVersion" type="UINT" value="7" />  
    <Parameter name="ppDevice" type="ID3D11Device" handle="35" isOutput="true" />  
    <Parameter name="pFeatureLevel" type="D3D_FEATURE_LEVEL" value="D3D_FEATURE_LEVEL_11_0" isOutput="true" />  
    <Parameter name="ppImmediateContext" type="ID3D11DeviceContext" value="nullptr" isOutput="true" />  
</Method>  
```  
  
## <a name="requirements"></a>요구 사항