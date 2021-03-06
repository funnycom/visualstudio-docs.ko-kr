---
title: "dimensions 메서드 (VBArray) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- dimensions
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dimensions method
- VBArray object constant
ms.assetid: ac83589e-85d9-48cb-b28d-c579e65fd604
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9896a5beced00614a825b1921b6046b0ac8a396a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="dimensions-method-vbarray-javascript"></a>dimensions 메서드(VBArray)(JavaScript)
VBArray의 차원 수를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
array.dimensions( )   
```  
  
## <a name="remarks"></a>설명  
 필요한 *array* 는 VBArray 개체입니다.  
  
## <a name="example"></a>예제  
 **dimensions** 메서드는 지정된 VBArray에서 차원 수를 검색하는 방법을 제공합니다.  
  
 다음 예제는 세 부분으로 구성됩니다. 첫 번째 부분은 Visual Basic 안전 배열을 만드는 VBScript 코드입니다. 두 번째 부분은 안전 배열의 차원 수와 각 차원의 상한을 결정하는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 코드입니다. 로 이동 하는 두 부분 모두는 \<H e a d > HTML 페이지의 섹션입니다. 세 번째 부분은 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 에 사용 되는 코드는 \<본문 > 섹션을 두 부분을 실행 합니다.  
  
```JavaScript  
<head>  
<script type="text/vbscript">  
<!--  
Function CreateVBArray()  
   Dim i, j, k  
   Dim a(2, 2)  
   k = 1  
   For i = 0 To 2  
      For j = 0 To 2  
         a(j, i) = k  
         k = k + 1  
      Next  
   Next  
   CreateVBArray = a  
End Function  
-->  
</script>  
  
<script type="text/javascript">  
<!--  
function VBArrayTest(vba)  
{  
   var i;  
   var a = new VBArray(vba);  
   var s = "";  
   for (i = 1; i <= a.dimensions(); i++)  
   {  
      s += "The upper bound of dimension ";  
      s += i + " is ";  
      s += a.ubound(i);  
      s += ".<br />";  
   }  
   return(s);  
}  
-->  
</script>  
</head>  
  
<body>  
<script type="text/javascript">  
   document.write(VBArrayTest(CreateVBArray()));  
</script>  
</body>  
```  
  
## <a name="requirements"></a>요구 사항  
 지원되는 문서 모드: Quirks, Internet Explorer 6 표준, Internet Explorer 7 표준, Internet Explorer 8 표준, Internet Explorer 9 표준 및 Internet Explorer 10 표준 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에서는 지원되지 않습니다. [버전 정보](../../javascript/reference/javascript-version-information.md)를 참조하십시오.  
  
 **적용 대상**: [VBArray Object](../../javascript/reference/vbarray-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getItem 메서드 (VBArray)](../../javascript/reference/getitem-method-vbarray-javascript.md)   
 [lbound 메서드 (VBArray)](../../javascript/reference/lbound-method-vbarray-javascript.md)   
 [toArray 메서드 (VBArray)](../../javascript/reference/toarray-method-vbarray-javascript.md)   
 [ubound 메서드(VBArray)](../../javascript/reference/ubound-method-vbarray-javascript.md)