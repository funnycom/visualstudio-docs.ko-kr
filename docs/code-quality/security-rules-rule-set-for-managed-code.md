---
title: "관리 코드에 대 한 보안 규칙 규칙 집합 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 564aeac6-03fa-41b0-b655-88179f0ab01b
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 3085eaabd5725a158c7099015adbe940ea5bd61c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="security-rules-rule-set-for-managed-code"></a>관리 코드에 대한 보안 규칙 규칙 집합
Microsoft 보안 규칙 규칙 집합을 보고 되는 잠재적 보안 문제의 수를 최대화 하기 위해 포함 되어야 합니다.  
  
|규칙|설명|  
|----------|-----------------|  
|[CA2100](../code-quality/ca2100-review-sql-queries-for-security-vulnerabilities.md)|보안상 취약한 부분이 있는지 SQL 쿼리를 검토하십시오.|  
|[CA2102](../code-quality/ca2102-catch-non-clscompliant-exceptions-in-general-handlers.md)|일반 처리기에서 비 CLSCompliant 예외를 catch 합니다.|  
|[CA2103](../code-quality/ca2103-review-imperative-security.md)|명령적 보안을 검토|  
|[CA2104](../code-quality/ca2104-do-not-declare-read-only-mutable-reference-types.md)|읽기 전용 참조 형식을 선언 하지 마십시오|  
|[CA2105](../code-quality/ca2105-array-fields-should-not-be-read-only.md)|만 배열 필드는 읽기 수|  
|[CA2106](../code-quality/ca2106-secure-asserts.md)|보안 어설션|  
|[CA2107](../code-quality/ca2107-review-deny-and-permit-only-usage.md)|Deny 및 permitonly 사용을 검토|  
|[CA2108](../code-quality/ca2108-review-declarative-security-on-value-types.md)|값 형식에서 선언적 보안을 검토하십시오.|  
|[CA2109](../code-quality/ca2109-review-visible-event-handlers.md)|표시 되는 이벤트 처리기를 검토 하십시오|  
|[CA2111](../code-quality/ca2111-pointers-should-not-be-visible.md)|포인터는 노출되면 안 됩니다.|  
|[CA2112](../code-quality/ca2112-secured-types-should-not-expose-fields.md)|보안 형식은 필드를 노출하면 안 됩니다.|  
|[CA2114](../code-quality/ca2114-method-security-should-be-a-superset-of-type.md)|메서드 보안은 형식의 상위 집합이어야 합니다.|  
|[CA2115](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)|GC를 호출 합니다. KeepAlive 네이티브 리소스를 사용 하는 경우|  
|[CA2116](../code-quality/ca2116-aptca-methods-should-only-call-aptca-methods.md)|APTCA 메서드는 APTCA 메서드만 호출해야 합니다.|  
|[CA2117](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)|APTCA 형식은 APTCA 기본 형식만 확장해야 합니다.|  
|[CA2118](../code-quality/ca2118-review-suppressunmanagedcodesecurityattribute-usage.md)|SuppressUnmanagedCodeSecurityAttribute 사용을 검토 합니다.|  
|[CA2119](../code-quality/ca2119-seal-methods-that-satisfy-private-interfaces.md)|Private 인터페이스를 만족 하는 메서드를 봉인 하십시오|  
|[CA2120](../code-quality/ca2120-secure-serialization-constructors.md)|Serialization 생성자|  
|[CA2121](../code-quality/ca2121-static-constructors-should-be-private.md)|정적 생성자는 private 이어야 합니다.|  
|[CA2122](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)|링크 요청이 있는 메서드를 간접적으로 노출하지 마십시오.|  
|[CA2123](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)|재정의 링크 요청은 기본 링크 요청과 같아야 합니다.|  
|[CA2124](../code-quality/ca2124-wrap-vulnerable-finally-clauses-in-outer-try.md)|취약한 finally 절을 외부 try에 래핑하십시오.|  
|[CA2126](../code-quality/ca2126-type-link-demands-require-inheritance-demands.md)|형식 링크 요청에는 상속 요청이 필요합니다.|  
|[CA2130](../code-quality/ca2130-security-critical-constants-should-be-transparent.md)|보안에 중요 한 상수는 투명 해야 합니다.|  
|[CA2131](../code-quality/ca2131-security-critical-types-may-not-participate-in-type-equivalence.md)|보안에 중요한 형식은 형식 동등에 참여할 수 없습니다.|  
|[CA2132](../code-quality/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors.md)|기본 생성자는 최소한 기본 형식 기본 생성자 만큼 중요 해야 합니다.|  
|[CA2133](../code-quality/ca2133-delegates-must-bind-to-methods-with-consistent-transparency.md)|대리자는 투명도가 일관된 메서드에 바인딩되어야 합니다.|  
|[CA2134](../code-quality/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods.md)|메서드는 기본 메서드를 재정의할 때 일관된 투명도를 유지해야 합니다.|  
|[CA2135](../code-quality/ca2135-level-2-assemblies-should-not-contain-linkdemands.md)|수준 2 어셈블리는 LinkDemands를 사용할 수 없습니다.|  
|[CA2136](../code-quality/ca2136-members-should-not-have-conflicting-transparency-annotations.md)|멤버에는 충돌 하는 투명도 주석을 사용 해야 합니다.|  
|[CA2137](../code-quality/ca2137-transparent-methods-must-contain-only-verifiable-il.md)|투명 메서드에는 확인할 수 있는 IL만 포함되어야 합니다.|  
|[CA2138](../code-quality/ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute.md)|투명 메서드는 SuppressUnmanagedCodeSecurity 특성을 사용하여 메서드를 호출해서는 안 됩니다.|  
|[CA2139](../code-quality/ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute.md)|투명 메서드는 HandleProcessCorruptingExceptions 특성을 사용할 수 없습니다.|  
|[CA2140](../code-quality/ca2140-transparent-code-must-not-reference-security-critical-items.md)|투명 코드는 보안에 중요한 항목을 참조해서는 안 됩니다.|  
|[CA2141](../code-quality/ca2141-transparent-methods-must-not-satisfy-linkdemands.md)|투명 메서드는 LinkDemands를 충족해서는 안 됩니다|  
|[CA2142](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)|투명 코드는 LinkDemands로 보호 되지 않습니다.|  
|[CA2143](../code-quality/ca2143-transparent-methods-should-not-use-security-demands.md)|투명 한 메서드는 보안 요청을 사용 하지 않아야|  
|[CA2144](../code-quality/ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays.md)|투명 코드 바이트 배열에서 어셈블리를 로드 해서는|  
|[CA2145](../code-quality/ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute.md)|투명 한 메서드는 SuppressUnmanagedCodeSecurityAttribute로 데코레이팅 해서는 안|  
|[CA2146](../code-quality/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces.md)|종류는 최소한 기본 형식 및 인터페이스 만큼 중요 해야 합니다.|  
|[CA2147](../code-quality/ca2147-transparent-methods-may-not-use-security-asserts.md)|투명 메서드는 보안 어설션을 사용할 수 없습니다.|  
|[CA2149](../code-quality/ca2149-transparent-methods-must-not-call-into-native-code.md)|투명 메서드는 네이티브 코드를 호출해서는 안 됩니다.|  
|[CA2210](../code-quality/ca2210-assemblies-should-have-valid-strong-names.md)|어셈블리에는 올바른 강력한 이름을 사용 해야 합니다.|