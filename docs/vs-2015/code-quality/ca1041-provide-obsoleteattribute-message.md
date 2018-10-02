---
title: 'CA1041: ObsoleteAttribute 메시지를 제공 합니다. | Microsoft Docs'
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
- CA1041
- ProvideObsoleteAttributeMessage
helpviewer_keywords:
- ProvideObsoleteAttributeMessage
- CA1041
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 298f6d3cbfc8b71443fe9e8e9733e5729963cea8
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47592362"
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041: ObsoleteAttribute 메시지를 제공하십시오.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [CA1041: ObsoleteAttribute 제공 메시지](https://docs.microsoft.com/visualstudio/code-quality/ca1041-provide-obsoleteattribute-message)합니다.

|||
|-|-|
|TypeName|ProvideObsoleteAttributeMessage|
|CheckId|CA1041|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 형식 또는 멤버를 사용 하 여 표시 되는 <xref:System.ObsoleteAttribute?displayProperty=fullName> 하지 않은 특성 해당 <xref:System.ObsoleteAttribute.Message%2A?displayProperty=fullName> 지정 된 속성입니다.

## <a name="rule-description"></a>규칙 설명
 <xref:System.ObsoleteAttribute> 사용 되지 않는 라이브러리 형식 및 멤버를 표시 하는 데 사용 됩니다. 라이브러리 소비자는 모든 형식 또는 obsolete로 표시 되어 있는 멤버의 사용을 피해 야 합니다. 이 지원 되지 않는 경우 해당 라이브러리의 이후 버전에서 제거 됩니다 때문입니다. 형식 또는 멤버를 사용 하 여 표시 하는 경우 <xref:System.ObsoleteAttribute> 컴파일되면는 <xref:System.ObsoleteAttribute.Message%2A> 특성의 속성이 표시 됩니다. 사용되지 않는 형식 또는 멤버에 대한 정보가 사용자에게 제공됩니다. 라이브러리 디자이너가 정보와 대신 사용 하도록에서 지원 되는 멤버 또는이 정보에는 일반적으로 사용 되지 않는 기간 형식 포함 됩니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 추가 합니다 `message` 매개 변수는 <xref:System.ObsoleteAttribute> 생성자입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 때문에이 규칙에서 경고를 표시 하지 마십시오는 <xref:System.ObsoleteAttribute.Message%2A> 속성은 사용 되지 않는 형식 또는 멤버에 대 한 중요 한 정보를 제공 합니다.

## <a name="example"></a>예제
 다음 예제에서는 제대로 선언에 사용 되지 않는 멤버를 <xref:System.ObsoleteAttribute>입니다.

 [!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/cpp/FxCop.Design.ObsoleteAttributeOnMember.cpp#1)]
 [!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/cs/FxCop.Design.ObsoleteAttributeOnMember.cs#1)]
 [!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/vb/FxCop.Design.ObsoleteAttributeOnMember.vb#1)]

## <a name="see-also"></a>참고 항목
 <xref:System.ObsoleteAttribute?displayProperty=fullName>


