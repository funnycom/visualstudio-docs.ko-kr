---
title: "이라는 이름의&lt;T&gt; 활동 디자이너 | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.RemoveFromCollection`1.UI
ms.assetid: 6617ba26-c8bc-4aed-b746-112bf490d288
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: f097e0d826725d3e3aa899c6137164487cfc5685
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="removefromcollectionlttgt-activity-designer"></a>이라는 이름의&lt;T&gt; 활동 디자이너
**이라는 이름의\<T >** 활동 디자이너는 만들고 구성 하는 데 사용 되는 <xref:System.Activities.Statements.RemoveFromCollection%601> 활동입니다.

## <a name="the-removefromcollectiont-activity"></a>R < T\> 활동
 <xref:System.Activities.Statements.RemoveFromCollection%601> 활동은 지정한 항목을 특정 컬렉션에서 제거합니다.

### <a name="using-the-removefromcollectiont-activity-designer"></a>R을 사용 하 여\<T > 활동 디자이너
 **이라는 이름의\<T >** 활동 디자이너에서 확인할 수 있습니다는 **컬렉션** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구 상자** 탭 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)

 **이라는 이름의\<T >** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 끌어다는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에 나 활동 일반적으로 배치와 같은 내는 <xref:System.Activities.Statements.Sequence>합니다. 그렇기 때문에 <xref:System.Activities.Statements.RemoveFromCollection%601> 기본값 활동 <xref:System.Activities.Activity.DisplayName%2A> 이라는 이름의 < i n t 32\>합니다. <xref:System.Activities.Activity.DisplayName%2A> 헤더의 값을 편집할 수 있습니다는 **이라는 이름의 < T\>**  활동 디자이너 또는 **DisplayName** 속성 표의 상자입니다. 다른 속성은 속성 표에서 편집해야 합니다.

### <a name="the-removefromcollectiont-properties"></a>R < T\> 속성
 다음 표에서는 <xref:System.Activities.Statements.RemoveFromCollection%601> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.RemoveFromCollection%601> 활동의 선택적 이름입니다. 기본값은 r < i n t 32\>합니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Item%2A>|True|에 추가할 항목의 **컬렉션\<T >**합니다. 이 항목은 형식의 *T*가 형식의 *TypeArgument*합니다. 이 항목을 지정하려면 속성 표에 Visual Basic 식을 입력합니다.|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Collection%2A>|True|항목이 추가될 컬렉션입니다. 이 컬렉션은 형식의 **c t i o < TypeArgument\>합니다.** 컬렉션을 지정 하려면 속성 표에 Visual Basic 식을 입력 합니다.|
|*TypeArgument*|True|<xref:System.Collections.Generic.ICollection%601>에 포함된 항목의 형식 T입니다. 기본적으로이 *TypeArgument* 유형이으로 설정 되어 **Int32**합니다. 값을 변경의 종류를 변경 하려면는 *TypeArgument* 속성 표의 콤보 상자에 있습니다.|
|<xref:System.Activities.Activity%601.Result%2A>|False|지정된 항목이 컬렉션에서 제거되었는지 여부를 나타내는 값입니다. 결과에 바인딩할 변수를 지정하려면 속성 표에 변수를 입력합니다.|

## <a name="see-also"></a>참고 항목

- [컬렉션](../workflow-designer/collection-activity-designers.md)
- [AddToCollection\<T>](../workflow-designer/addtocollection-t-activity-designer.md)
- [ClearCollection\<T>](../workflow-designer/clearcollection-t-activity-designer.md)
- [ExistsInCollection\<T>](../workflow-designer/existsincollection-t-activity-designer.md)