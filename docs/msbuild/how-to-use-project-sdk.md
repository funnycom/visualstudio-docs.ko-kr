---
title: "방법: MSBuild 프로젝트 SDK 참조 | Microsoft Docs"
ms.custom: 
ms.date: 01/25/2018
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, SDKs, SDK
author: jeffkl
ms.author: jeffkl
manager: angerlic
ms.workload:
- multiple
ms.openlocfilehash: 28027b21d3f562e3eda94dc91de16ddb38362d3c
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-use-msbuild-project-sdks"></a>방법: MSBuild 프로젝트 SDK 사용
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 15.0은 속성 및 대상을 가져오는 데 필요한 소프트웨어 개발 키트 사용을 간소화하는 “프로젝트 SDK”의 개념을 도입했습니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
        <TargetFramework>net46</TargetFramework>
    </PropertyGroup>
</Project>
```  
  
프로젝트 평가 중에 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]는 프로젝트의 맨 위 및 맨 아래에 암시적 가져오기를 추가합니다.

```xml
<Project>
    <!-- Implicit top import -->
    <Import Project="Sdk.props" Sdk="Microsoft.NET.Sdk" />

    <PropertyGroup>
        <TargetFramework>net46</TargetFramework>
    </PropertyGroup>

    <!-- Implicit bottom import -->
    <Import Project="Sdk.targets" Sdk="Microsoft.NET.Sdk" />
</Project>  
```  

## <a name="referencing-a-project-sdk"></a>프로젝트 SDK 참조
 프로젝트 SDK를 참조하는 세 가지 방법이 있습니다.

1. `Sdk` 요소에서 `<Project/>` 특성을 사용합니다.
    ```xml
    <Project Sdk="My.Custom.Sdk">
        ...
    </Project>
    ```
    암시적 가져오기는 위에서 설명한 대로 프로젝트의 맨 위 및 맨 아래에 추가됩니다.  `Sdk` 특성의 형식은 `Name[/Version]`입니다. 여기서 Version은 선택 사항입니다.  예를 들어 `My.Custom.Sdk/1.2.3`을 지정할 수 있습니다.

2. 최상위 수준 `<Sdk/>` 요소를 사용합니다.
    ```xml
    <Project>
        <Sdk Name="My.Custom.Sdk" Version="1.2.3" />
        ...
    </Project>
   ```
   암시적 가져오기는 위에서 설명한 대로 프로젝트의 맨 위 및 맨 아래에 추가됩니다.  `Version` 특성이 필요하지 않습니다.

3. 프로젝트의 어디에나 `<Import/>` 요소를 사용합니다.
    ```xml
    <Project>
        <PropertyGroup>
            <MyProperty>Value</MyProperty>
        </PropertyGroup>
        <Import Project="Sdk.props" Sdk="My.Custom.Sdk" />
        ...
        <Import Project="Sdk.targets" Sdk="My.Custom.Sdk" />
    </Project>
   ```
   프로젝트의 가져오기를 명시적으로 포함하면 순서를 완전히 제어할 수 있습니다.

   `<Import/>` 요소를 사용하는 경우 선택적인 `Version` 특성도 지정할 수 있습니다.  예를 들어 `<Import Project="Sdk.props" Sdk="My.Custom.Sdk" Version="1.2.3" />`을 지정할 수 있습니다.

## <a name="how-project-sdks-are-resolved"></a>프로젝트 SDK를 확인하는 방법
가져오기를 평가할 때 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]는 지정한 이름 및 버전에 따라 프로젝트 SDK의 경로를 동적으로 확인합니다.  [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에는 컴퓨터에서 프로젝트 SDK를 찾는 플러그 인인 등록된 SDK 확인자의 목록도 있습니다.  이러한 플러그 인은 다음과 같습니다.

1. 지정한 SDK의 ID 및 버전과 일치하는 NuGet 패키지에 대해 구성된 패키지 피드를 쿼리하는 NuGet 기반 확인자.<br/>
   이 확인자는 선택적 버전을 지정한 경우에만 활성화되며 모든 사용자 지정 프로젝트 SDK에 사용할 수 있습니다.  
2. .NET CLI와 함께 설치되는 SDK를 확인하는 .NET CLI 확인자.<br/>
   이 확인자는 제품의 일부인 `Microsoft.NET.Sdk` 및 `Microsoft.NET.Sdk.Web`와 같은 프로젝트 SDK를 찾습니다.
3. MSBuild에 설치된 SDK를 확인하는 기본 확인자.

NuGet 기반 SDK 확인자는 개별 프로젝트 각각이 아닌 한 곳에서 프로젝트 SDK 버전을 제어할 수 있는 [global.json](https://docs.microsoft.com/en-us/dotnet/core/tools/global-json)에서 버전을 지정하도록 지원합니다.

```json
{
    "msbuild-sdks": {
        "My.Custom.Sdk": "5.0.0",
        "My.Other.Sdk": "1.0.0-beta"
    }
}
```
빌드 중에는 각 프로젝트 SDK 버전을 하나만 사용할 수 있습니다.  동일한 프로젝트 SDK의 두 가지 버전을 참조하는 경우 MSBuild에서 경고를 생성합니다.  `global.json`에 버전이 지정된 경우 프로젝트에서 버전을 지정하지 **않는** 것이 좋습니다.  

## <a name="see-also"></a>참고 항목  
 [MSBuild 개념](../msbuild/msbuild-concepts.md)   
 [빌드 사용자 지정](../msbuild/customize-your-build.md)   
