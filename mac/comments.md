---
title: "설명"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 0FE5E929-1846-4F48-B5E3-70990FAF9504
ms.openlocfilehash: cb44dc755721f6095c9a07ad3e6fec1f6849e149
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="comments"></a>설명

코드를 디버그하거나 실험하는 경우 일시적 또는 장기적으로 코드 블록을 주석으로 처리하는 것이 유용할 수 있습니다. 

전체 코드 블록을 주석으로 처리하려면

* 코드를 선택하고 상황에 맞는 메뉴에서 **줄 주석 토글**을 선택합니다.

또는

* 선택한 코드에서 `cmd + /` 키 바인딩을 사용합니다.

이러한 방법을 사용하여 코드 섹션을 주석으로 처리하거나 주석 처리를 제거할 수 있습니다. C# 파일에서는 줄 주석 수준을 추가하여 실제 주석을 유지하면서 코드 영역을 주석으로 처리하거나 주석 처리를 제거할 수 있습니다. 

 ![여러 수준의 주석](media/source-editor-image8.png)

주석은 코드를 조작할 수 있는 향후 개발자를 위해 코드를 문서화하는 데에도 유용합니다. 일반적으로 각 언어에서 다음과 같은 방식으로 추가되는 여러 줄 주석의 형태로 수행됩니다.

**C#**

``` cs
/*
 This is a multi-line
 comment in C#
*/
```
**F#**

```fsharp
(*
 This is a multi-line
  comment in F#
*)
```
