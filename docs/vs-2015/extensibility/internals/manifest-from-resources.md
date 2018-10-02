---
title: 리소스에서 매니페스트 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0234109b-5dcb-4d9d-acb9-a63f8bd5699c
caps.latest.revision: 5
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fba4d5ca7611bab24488ed5c48247241a2b74bf1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551764"
---
# <a name="manifest-from-resources"></a>Manifest from Resources
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [리소스에서 매니페스트](https://docs.microsoft.com/visualstudio/extensibility/internals/manifest-from-resources)합니다.  
  
리소스 도구에서 매니페스트는 이미지 리소스 (.png 또는.xaml 파일)의 목록을 사용 하 고 이러한 이미지는 Visual Studio 이미지 서비스와 함께 사용할 수 있도록.imagemanifest 파일을 생성 하는 콘솔 응용 프로그램. 또한 이미지를 기존.imagemanifest 추가할이 도구를 사용할 수 있습니다. 이 도구는 높은 DPI 및 테마를 Visual Studio 확장에는 이미지에 대 한 지원을 추가 하는 데 유용 합니다. 생성 된.imagemanifest 파일에 포함 되어 있고 Visual Studio 확장 (.vsix)의 일부로 배포 합니다.  
  
## <a name="how-to-use-the-tool"></a>이 도구를 사용 하는 방법  
 **구문**  
  
 ManifestFromResources /resources:\<Dir1 >;\< Img1 > /assembly:\<AssemblyName > \<선택적 인수 >  
  
 **인수**  
  
||||  
|-|-|-|  
|**스위치 이름**|**참고**|**필수 또는 선택**|  
|/resources|이미지 또는 디렉터리의 세미콜론으로 구분 된 목록입니다. 항상이 목록에는 매니페스트가 포함 될 이미지의 전체 목록을 포함 되어 있어야 합니다. 하나만 부분 목록을 지정 된 경우 제외 항목이 손실 됩니다.<br /><br /> 이미지 스트립 지정 된 리소스 파일을 사용 하는 경우 도구는 분할 별도 이미지로 각 subimage 매니페스트를 추가 하기 전에 합니다.<br /><br /> 이미지.png 파일로 이면 도구는 이미지에 대 한 올바른 특성을 채울 수 있도록 이름을 다음과 같이 형식는 것이 좋습니다: \<이름 >.\< 너비 >. \<높이 >.png입니다.|필수|  
|/assembly|이름 (확장명 포함 안), 관리 되는 어셈블리 또는 리소스 (간의 상대적 매니페스트의 런타임 위치)를 호스트 하는 네이티브 어셈블리의 런타임 경로입니다.|필수|  
|/manifest|생성 된.imagemanifest 파일에 부여할 이름입니다. 이 다른 위치에 파일을 만들려면 절대 또는 상대 경로 포함할 수도 있습니다. 기본 이름은 어셈블리 이름에 일치 합니다.<br /><br /> 기본값: \<현재 디렉터리 >\\< 어셈블리\>.imagemanifest|Optional|  
|/guidName|모든 생성 된 매니페스트에서 이미지에 대 한 GUID 기호에 부여할 이름입니다.<br /><br /> 기본값: AssetsGuid|Optional|  
|/rootPath|관리 되는 리소스 Uri를 만들기 전에 여러분이 해야 하는 루트 경로입니다. (이 플래그는 도구를 가져오는 위치 상대 URI 경로 리소스 로드 실패를 일으키는 잘못 된 경우에 도움이 되도록 합니다.)<br /><br /> 기본값: \<현재 디렉터리 >|Optional|  
|/recursive|재귀적으로이 플래그를 설정 /resources 인수에 모든 디렉터리를 검색 합니다. 이 플래그를 생략 하면 디렉터리의 최상위 level만 검색 됩니다.|Optional|  
|/isNative|어셈블리 인수가 네이티브 어셈블리에 대 한 경로 하는 경우이 플래그를 설정 합니다. 관리 되는 어셈블리의 이름은 어셈블리 인수의 경우이 플래그를 생략 합니다. (이 플래그에 대 한 자세한 내용은 참고 섹션을 참조 하세요.)|Optional|  
|/newGuids|이 플래그를 설정의 기존 매니페스트를 병합 하는 대신 이미지의 GUID 기호에 대 한 새 값을 만드는 도구를 알립니다.|Optional|  
|/newIds|이 플래그를 설정 합니다. 기존 매니페스트에서 값을 병합 하는 대신 모든 이미지에 대 한 새 ID 기호 값을 만드는 도구를 알립니다.|Optional|  
|/noLogo|인쇄에서 제품 및 저작권 정보를 중지이 플래그를 설정 합니다.|Optional|  
|/?|도움말 정보를 인쇄 합니다.|Optional|  
|/help|도움말 정보를 인쇄 합니다.|Optional|  
  
 **예제**  
  
-   ManifestFromResources /resources:D:\Images /assembly:My.Assembly.Name /isNative  
  
-   ManifestFromResources /resources:D:\Images\Image1.png;D:\Images\Image1.xaml /assembly:My.Assembly.Name /manifest:MyImageManifest.imagemanifest  
  
-   ManifestFromResources /resources:D:\Images\Image1.png;D:\Images\Image1.xaml /assembly:My.Assembly.Name /guidName:MyImages /newGuids /newIds  
  
## <a name="notes"></a>노트  
  
-   이 도구는만.png 및.xaml 파일을 지원합니다. 다른 이미지 또는 파일 형식이 무시 됩니다. 리소스 구문 분석 하는 동안 발생 하는 모든 지원 되지 않는 형식에 대 한 경고가 생성 됩니다. 도구가 완료 되 면 이미지 발견 되는 경우를 지원 하지 않습니다 리소스 구문 분석 오류가 생성 됩니다  
  
-   .Png 이미지에 대 한 제안 된 형식에 따라 도구는는.png 크기/차원 값 형식으로 지정 된 크기로 설정, 이미지의 실제 크기와 다른 경우에 합니다.  
  
-   .Png 이미지 너비/높이 형식을 생략할 수 있습니다 하지만 도구는 이미지의 실제 너비/높이 읽고 이미지의 크기/차원 값에 대 한 역할을 사용 합니다.  
  
-   여러 번 동일한.imagemanifest에 동일한 이미지 스트립에서이 도구를 실행 도구를 독립 실행형 이미지를 이미지 스트립을 분할 하 고 기존 매니페스트를 추가 하려고 하기 때문에 중복 된 매니페스트 항목이 발생 합니다.  
  
-   도구에서 생성 된 매니페스트에 대 한 병합 (/newGuids 또는 /newIds 생략)만 수행 해야 합니다. 사용자 지정 또는 다른 수단을 통해 생성 된 매니페스트를 제대로 병합 될 수 있습니다.  
  
-   네이티브 어셈블리에 대 한 생성 된 매니페스트 리소스 네이티브 어셈블리의.rc 파일에서 Id와 일치 하는 ID 기호를 확인 하기 위해 생성 한 후 직접 편집할 수 해야 합니다.  
  
## <a name="sample-output"></a>샘플 출력  
 **간단한 이미지 매니페스트**  
  
 이미지 매니페스트는이.xml 파일에 유사한 됩니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<!-- This file was generated by the ManifestFromResources tool.-->  
<!-- Version: 14.0.15197 -->  
<ImageManifest xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/VisualStudio/ImageManifestSchema/2014">  
  <Symbols>  
    <String Name="Resources" Value="/My.Assembly.Name;Component/Resources/Images" />  
    <Guid Name="AssetsGuid" Value="{fb41b7ef-6587-480c-aa27-5b559d42cfc9}" />  
    <ID Name="MyImage" Value="0" />  
  </Symbols>  
  <Images>  
    <Image Guid="$(AssetsGuid)" ID="$(MyImage)">  
      <Source Uri="$(Resources)/Xaml/MyImage.xaml" />  
      <Source Uri="$(Resources)/Png/MyImage.16.16.png">  
        <Size Value="16" />  
      </Source>  
    </Image>  
  </Images>  
  <ImageLists />  
</ImageManifest>  
```  
  
 **이미지 스트립에 대 한 이미지 매니페스트**  
  
 이미지 스트립에 대 한 이미지 매니페스트가.xml 파일에 유사한 됩니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<!-- This file was generated by the ManifestFromResources tool.-->  
<!-- Version: 14.0.15197 -->  
<ImageManifest xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/VisualStudio/ImageManifestSchema/2014">  
  <Symbols>  
    <String Name="Resources" Value="/My.Assembly.Name;Component/Resources/ImageStrip" />  
    <Guid Name="AssetsGuid" Value="{fb41b7ef-6587-480c-aa27-5b559d42cfc9}" />  
    <ID Name="MyImageStrip_0" Value="1" />  
    <ID Name="MyImageStrip_1" Value="2" />  
    <ID Name="MyImageStrip" Value="3" />  
  </Symbols>  
  <Images>  
    <Image Guid="$(AssetsGuid)" ID="$(MyImageStrip_0)">  
      <Source Uri="$(Resources)/MyImageStrip_0.png">  
        <Size Value="16" />  
      </Source>  
    </Image>  
    <Image Guid="$(AssetsGuid)" ID="$(MyImageStrip_1)">  
      <Source Uri="$(Resources)/MyImageStrip_1.png">  
        <Size Value="16" />  
      </Source>  
    </Image>  
  </Images>  
  <ImageLists>  
    <ImageList Guid="$(AssetsGuid)" ID="$(MyImageStrip)">  
      <ContainedImage Guid="$(AssetsGuid)" ID="$(MyImageStrip_0)" />  
      <ContainedImage Guid="$(AssetsGuid)" ID="$(MyImageStrip_1)" />  
    </ImageList>  
  </ImageLists>  
</ImageManifest>  
```  
  
 **네이티브 어셈블리 이미지 리소스에 대 한 이미지 매니페스트**  
  
 네이티브 이미지에 대 한 이미지 매니페스트가.xml 파일에 유사한 됩니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<!-- This file was generated by the ManifestFromResources tool.-->  
<!-- Version: 14.0.15198 -->  
<ImageManifest xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/VisualStudio/ImageManifestSchema/2014">  
  <Symbols>  
    <String Name="Resources" Value="..\Assembly\Folder\My.Assembly.Name" />  
    <Guid Name="AssetsGuid" Value="{442d8739-efde-46a4-8f29-e3a1e5e7f8b4}" />  
    <ID Name="MyImage1" Value="0" />  
    <ID Name="MyImage2" Value="1" />  
  </Symbols>  
  <Images>  
    <Image Guid="$(AssetsGuid)" ID="$(MyImage1)">  
      <Source Uri="$(Resources)">  
        <Size Value="16" />  
        <NativeResource ID="$(MyImage1)" Type="PNG" />  
      </Source>  
    </Image>  
    <Image Guid="$(AssetsGuid)" ID="$(MyImage2)">  
      <Source Uri="$(Resources)">  
        <Size Value="16" />  
        <NativeResource ID="$(MyImage2)" Type="PNG" />  
      </Source>  
    </Image>  
  </Images>  
  <ImageLists />  
</ImageManifest>  
```
