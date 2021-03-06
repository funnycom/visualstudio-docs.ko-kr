---
title: "PropertyGroup 요소(MSBuild) | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#PropertyGroup
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <PropertyGroup> element [MSBuild]
- PropertyGroup element [MSBuild]
ms.assetid: ff1e6c68-b9a1-4263-a1ce-dc3b829a64d4
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e19722c1da702684200d848eb62d1dd46a900590
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="propertygroup-element-msbuild"></a>PropertyGroup 요소(MSBuild)
사용자 정의 [Property](../msbuild/property-element-msbuild.md) 요소 집합을 포함합니다. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트에서 사용되는 모든 `Property`요소는 `PropertyGroup` 요소의 자식이어야 합니다.  

 \<Project>  
 \<PropertyGroup>  

## <a name="syntax"></a>구문  

```  
<PropertyGroup Condition="'String A' == 'String B'">  
    <Property1>...</Property1>  
    <Property2>...</Property2>  
</PropertyGroup>  
```  

## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  

### <a name="attributes"></a>특성  

|특성|설명|  
|---------------|-----------------|  
|조건|선택적 특성입니다.<br /><br /> 평가할 조건입니다. 자세한 내용은 [조건](../msbuild/msbuild-conditions.md)을 참조하세요.|  

### <a name="child-elements"></a>자식 요소  

|요소|설명|  
|-------------|-----------------|  
|[Property](../msbuild/property-element-msbuild.md)|선택적 요소입니다.<br /><br /> 속성값을 포함하는 사용자 정의 속성 이름입니다. `PropertyGroup` 요소에는 *Property* 요소가 없을 수도 있고 하나 이상 있을 수도 있습니다.|  

### <a name="parent-elements"></a>부모 요소  

|요소|설명|  
|-------------|-----------------|  
|[프로젝트](../msbuild/project-element-msbuild.md)|[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트 파일의 필수 루트 요소입니다.|  

## <a name="example"></a>예  
 다음 코드 예제에서는 조건에 따라 속성을 설정하는 방법을 보여 줍니다. 이 예제에서 `CompileConfig` 속성값이 `DEBUG`이면 `PropertyGroup` 요소 내에서 `Optimization`, `Obfuscate` 및 `OutputPath` 속성이 설정됩니다.  

```xml  
<PropertyGroup Condition="'$(CompileConfig)' == 'DEBUG'" >  
    <Optimization>false</Optimization>  
    <Obfuscate>false</Obfuscate>  
    <OutputPath>$(OutputPath)\debug</OutputPath>  
</PropertyGroup>  
```  

## <a name="see-also"></a>참고 항목  
 [프로젝트 파일 스키마 참조](../msbuild/msbuild-project-file-schema-reference.md)  
 [MSBuild 속성](../msbuild/msbuild-properties.md)
