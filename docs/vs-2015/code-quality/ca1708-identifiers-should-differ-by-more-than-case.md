---
title: 'CA1708: 식별자는 대/소문자만 달라 야 합니다. | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IdentifiersShouldDifferByMoreThanCase
- CA1708
helpviewer_keywords:
- CA1708
- IdentifiersShouldDifferByMoreThanCase
ms.assetid: dac0f01d-dd21-484d-add1-c8cd2bf6969f
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: d60c29b7e6a5cec32b8a694bb0b21d7f85538e01
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47592243"
---
# <a name="ca1708-identifiers-should-differ-by-more-than-case"></a>CA1708: 식별자에는 대/소문자만 다른 이름을 사용할 수 없습니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA1708: 식별자는 대/소문자만 달라 야 합니다.](https://docs.microsoft.com/visualstudio/code-quality/ca1708-identifiers-should-differ-by-more-than-case)합니다.

|||
|-|-|
|TypeName|IdentifiersShouldDifferByMoreThanCase|
|CheckId|CA1708|
|범주|Microsoft.Naming|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 두 형식, 멤버, 매개 변수 또는 정규화 된 네임 스페이스의 이름을 소문자로 변환 될 경우 동일 합니다.

## <a name="rule-description"></a>규칙 설명
 공용 언어 런타임을 대상으로 하는 언어는 대/소문자를 구분하지 않으므로 네임스페이스, 형식, 멤버 및 매개 변수의 식별자가 대/소문자만 달라서는 안 됩니다. 예를 들어 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] 은 널리 사용 되는 대/소문자 언어입니다.

 이 규칙은 공개적으로 표시 하는 멤버에만 실행 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 대/소문자 구분 방식으로 다른 식별자를 비교 했을 때 고유 이름을 선택 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다. 라이브러리에서 사용 가능한 모든 언어에서 사용 하지 못할는 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]합니다.

## <a name="example-of-a-violation"></a>위반의 예
 다음 예제에서는이 규칙 위반을 보여 줍니다.

 [!code-csharp[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Naming.IdentifiersShouldDifferByMoreThanCase/cs/FxCop.Naming.IdentifiersShouldDifferByMoreThanCase.cs#1)]

## <a name="related-rules"></a>관련된 규칙
 [CA1709: 식별자는 정확한 대/소문자를 사용해야 합니다.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)


