---
title: "CA1404: P Invoke 다음에 바로 GetLastError를 호출 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
helpviewer_keywords:
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
ms.assetid: 52ae9eff-50f9-4b2f-8039-ca7e49fba88e
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c12d90fe9ae453f3b02c9e6c3f961e54084081aa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1404-call-getlasterror-immediately-after-pinvoke"></a>CA1404: P/Invoke 다음에 바로 GetLastError를 호출하십시오.
|||  
|-|-|  
|TypeName|CallGetLastErrorImmediatelyAfterPInvoke|  
|CheckId|CA1404|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 호출할는 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A?displayProperty=fullName> 메서드 또는 해당 하는 Win32 `GetLastError` 함수와 호출 하였으며 직전 플랫폼에 없는 메서드를 호출 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 플랫폼 비관리 코드에 액세스 메서드를 호출 하 고 사용 하 여 정의 된 `Declare` 키워드 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 또는 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> 특성입니다. 일반적으로 Win32 호출 관리 되지 않는 함수 실패 시 `SetLastError` 오류와 연결 된 오류 코드를 설정 하는 함수입니다. 실패 한 함수별의 호출자는 Win32 호출 `GetLastError` 오류 코드를 검색 한 오류의 원인을 확인 하는 함수입니다. 오류 코드는 스레드 단위 별로 관리 및 다음 호출 하 여 덮어쓸 `SetLastError`합니다. 실패 한 플랫폼에 대 한 호출 메서드를 호출한 후 관리 코드를 호출 하 여 오류 코드를 검색할 수는 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> 메서드. 오류 코드는 다른 관리 되는 클래스 라이브러리 메서드 내부 호출에 의해 덮어쓸 수 있으므로 `GetLastError` 또는 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> 플랫폼 호출 메서드 호출 후에 즉시 메서드를 호출 해야 합니다.  
  
 다음에 대 한 호출을 무시 하는 규칙은 플랫폼에 대 한 호출 간에 발생 하는 경우 관리 되는 멤버 메서드 및에 대 한 호출을 호출 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A>합니다. 이러한 멤버는 오류를 변경 하지 마십시오 메서드 호출을 호출 코드와는 일부 플랫폼의 성공 여부를 결정 하는 데 유용 합니다.  
  
-   <xref:System.IntPtr.Zero?displayProperty=fullName>  
  
-   <xref:System.IntPtr.op_Equality%2A?displayProperty=fullName>  
  
-   <xref:System.IntPtr.op_Inequality%2A?displayProperty=fullName>  
  
-   <xref:System.Runtime.InteropServices.SafeHandle.IsInvalid%2A?displayProperty=fullName>  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면에 대 한 호출을 이동 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> 플랫폼에 대 한 호출 바로 뒤에 오도록 메서드를 호출 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 플랫폼 간 코드 호출 메서드를 호출할 경우이 규칙에서는 경고를에서 표시 하지 않는를 안전 하 게 및 <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> 메서드 호출 수 없는 명시적 또는 암시적으로 인해 변경 하는 오류 코드입니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 규칙을 위반 하는 메서드 및 규칙을 충족 하는 메서드를 보여 줍니다.  
  
 [!code-vb[FxCop.Interoperability.LastErrorPInvoke#1](../code-quality/codesnippet/VisualBasic/ca1404-call-getlasterror-immediately-after-p-invoke_1.vb)]
 [!code-csharp[FxCop.Interoperability.LastErrorPInvoke#1](../code-quality/codesnippet/CSharp/ca1404-call-getlasterror-immediately-after-p-invoke_1.cs)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1060: 이동 P/Invoke를 NativeMethods 클래스로](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)  
  
 [P/Invoke 진입점 ca1400:](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)  
  
 [CA1401: P/Invoke는 노출 되지](../code-quality/ca1401-p-invokes-should-not-be-visible.md)  
  
 [CA2101: P/Invoke 문자열 인수에 대해 마샬링을 지정 하십시오.](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)  
  
 [CA2205: Win32 API에 있는 동일한 기능의 관리되는 항목을 사용하십시오.](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)