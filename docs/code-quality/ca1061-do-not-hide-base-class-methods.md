---
title: "CA1061: 기본 클래스 메서드를 숨기지 마십시오 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1061
- DoNotHideBaseClassMethods
helpviewer_keywords:
- DoNotHideBaseClassMethods
- CA1061
ms.assetid: 0bda9dc8-87b4-4038-ab9d-563298387466
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d7eb4db46697e7f4cbb54d9ee11e4289b5a2ba2c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1061-do-not-hide-base-class-methods"></a>CA1061: 기본 클래스 메서드를 숨기지 마십시오.
|||  
|-|-|  
|TypeName|DoNotHideBaseClassMethods|  
|CheckId|CA1061|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 파생 된 형식; 기본 메서드 중 하나로 매개 변수 수가 같은 동일한 이름으로 메서드를 선언합니다. 하나 이상의 매개 변수는 기본 메서드;에서 해당 매개 변수의 기본 형식 및 모든 나머지 매개 변수는 기본 메서드의 해당 매개 변수와 동일 유형의 제공 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 파생 된 메서드의 매개 변수 시그니처에 기본 메서드의 매개 변수 시그니처에 있는 해당 형식 보다 더 약하게 파생 된 형식만 다른 경우 기본 형식의 메서드 파생된 된 형식에서 동일한 이름의 메서드에 의해 숨겨집니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 또는 메서드, 이름 바꾸기 변경 하거나 제거할 매개 변수 시그니처에 하는 메서드는 기본 메서드를 숨기지 않습니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 규칙을 위반 하는 메서드를 보여 줍니다.  
  
 [!code-csharp[FxCop.Design.HideBaseMethod#1](../code-quality/codesnippet/CSharp/ca1061-do-not-hide-base-class-methods_1.cs)]