---
title: "CA2241: 올바른 인수를 제공 하십시오. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2241
- Provide correct arguments to formatting methods
- ProvideCorrectArgumentsToFormattingMethods
helpviewer_keywords:
- ProvideCorrectArgumentsToFormattingMethods
- CA2241
ms.assetid: 83639bc4-4c91-4a07-a40e-dc5e49a84494
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f5f71926705169d4ed7dc40318e83f265e8603f5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2241-provide-correct-arguments-to-formatting-methods"></a>CA2241: 형식 메서드에 올바른 인수를 제공하십시오.
|||  
|-|-|  
|TypeName|ProvideCorrectArgumentsToFormattingMethods|  
|CheckId|CA2241|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 `format` 문자열 인수 같은 메서드에 전달 된 <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, 또는 <xref:System.String.Format%2A?displayProperty=fullName> 형식 항목 또는 그 반대로 각 개체 인수에 해당 하는 포함 되지 않습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 인수 같은 메서드에 <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, 및 <xref:System.String.Format%2A> 뒤에 여러 개의 형식 문자열 구성 <xref:System.Object?displayProperty=fullName> 인스턴스. 텍스트와 폼의 항목이 포함된 형식의 형식 문자열이 구성 된 {인덱스 [, 맞춤] [: formatString]을 (를). 'index'는 형식을 지정할 개체 부분을 나타내는 0부터 시작하는 정수입니다. 개체에 해당 하는 인덱스가 형식 문자열에서 개체는 무시 됩니다. 'Index'로 지정 된 개체가 있는 경우는 <xref:System.FormatException?displayProperty=fullName> 런타임 시 throw 됩니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 각 개체 인수에 대 한 서식 항목을 제공 하 고 각 형식 항목에 대 한 개체 인수를 제공 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 두 개의 규칙을 위반 경우를 보여 줍니다.  
  
 [!code-vb[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/VisualBasic/ca2241-provide-correct-arguments-to-formatting-methods_1.vb)]
 [!code-csharp[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/CSharp/ca2241-provide-correct-arguments-to-formatting-methods_1.cs)]