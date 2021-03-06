---
title: "CA1802: 가능 하면 리터럴을 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UseLiteralsWhereAppropriate
- CA1802
helpviewer_keywords:
- UseLiteralsWhereAppropriate
- CA1802
ms.assetid: 2515e4cd-9e61-486d-b067-58ba1a743ce4
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c2e7841091d3ad5ca093b35b62cca1fdbe6b6a69
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1802-use-literals-where-appropriate"></a>CA1802: 가능하면 리터럴을 사용하십시오.
|||  
|-|-|  
|TypeName|UseLiteralsWhereAppropriate|  
|CheckId|CA1802|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 필드가 선언 되었습니다 `static` 및 `readonly` (`Shared` 및 `ReadOnly` 에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]), 컴파일 타임에 계산할 수 있는 값으로 초기화 됩니다.  
  
## <a name="rule-description"></a>규칙 설명  
 값을 `static``readonly` 필드 선언 형식에 대 한 정적 생성자를 호출 하는 경우 런타임 시 계산 됩니다. 경우는 `static``readonly` 필드는 선언 되 고 정적 생성자 선언 되지 않은 명시적으로 컴파일러에서 필드를 초기화 하는 정적 생성자를 초기화 합니다.  
  
 값을 `const` 필드가 컴파일 타임에 계산 되며 메타 데이터와 비교할 때 런타임 성능이 향상에 `static``readonly` 필드입니다.  
  
 대상된 필드에 할당 된 값은 컴파일 타임에 계산할 수, 선언을 변경 하 여 한 `const` 필드 값이 런타임 대신 컴파일 타임에 계산 되도록 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 대체는 `static` 및 `readonly` 와 함께 한정자는 `const` 한정자입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 성능이 중요 하지 않은 경우이 규칙에서 경고를 표시 하거나 규칙을 사용 하지 않도록 하려면 안전 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 형식 `UseReadOnly`, 규칙을 위반 하는 형식이 있는 `UseConstant`, 규칙을 충족 하 합니다.  
  
 [!code-vb[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/VisualBasic/ca1802-use-literals-where-appropriate_1.vb)]
 [!code-csharp[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/CSharp/ca1802-use-literals-where-appropriate_1.cs)]