---
title: "Microsoft Visual Studio에서 XML 조각을 사용 하는 방법 | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: article
ms.assetid: 3a27375b-81cc-48f6-a884-e1cb8c4f78f5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3e8e94b799db6572b3aafcbd6bacf826b4a22861
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-use-xml-snippets"></a>방법: 사용 하 여 XML 조각

XML 편집기 바로 가기 메뉴에서 다음 두 명령을 사용하여 XML 조각을 호출할 수 있습니다. **조각 삽입** 명령은 커서 위치에 XML 조각을 삽입 합니다. **감싸기** 명령을 사용 하면 선택한 텍스트 주위의 XML 조각을 래핑합니다. 각 XML 조각에는 조각 형식이 지정되어 있습니다. 조각 형식은 조각으로 사용할 수 있는지 확인은 **조각 삽입** 명령을 **코드 감싸기** 명령 또는 둘 다 합니다.

XML 조각을 편집기에 추가한 후 조각에서 편집 가능한 필드가 노란색으로 강조되며 편집 가능한 첫 번째 필드에 커서가 놓입니다.

## <a name="insert-snippet"></a>코드 조각 삽입

다음 절차는에 액세스 하는 방법을 설명는 **조각 삽입** 명령입니다.

> [!NOTE]
> **조각 삽입** 명령을 바로 가기 키를 통해 사용할 수도 있습니다 (**Ctrl**+**K**, 다음 **Ctrl** + **X**).

### <a name="to-insert-snippets-from-the-shortcut-menu"></a>바로 가기 메뉴에서 조각을 삽입하려면

1. XML 조각을 삽입할 커서의 위치를 지정합니다.

2. 마우스 오른쪽 단추로 클릭 하 고 선택 **조각 삽입**합니다.

   사용 가능한 XML 조각의 목록이 표시됩니다.

3. 목록에서 마우스를 사용 하거나 조각 및 키를 눌러의 이름을 입력 하 여 조각을 선택 **탭** 또는 **Enter**합니다.

### <a name="to-insert-snippets-using-the-intellisense-menu"></a>IntelliSense 메뉴를 사용하여 조각을 삽입하려면

1. XML 조각을 삽입할 커서의 위치를 지정합니다.

2. **편집** 메뉴에서 **IntelliSense**를 선택한 후 **조각 삽입**합니다.

   사용 가능한 XML 조각의 목록이 표시됩니다.

3. 목록에서 마우스를 사용 하거나 조각 및 키를 눌러의 이름을 입력 하 여 조각을 선택 **탭** 또는 **Enter**합니다.

### <a name="to-insert-snippets-through-the-intellisense-complete-word-list"></a>IntelliSense 단어 자동 완성 목록을 통해 조각을 삽입하려면

1. XML 조각을 삽입할 커서의 위치를 지정합니다.

2. 파일에 추가할 XML 조각을 입력하기 시작합니다. 자동 완성 기능이 설정된 경우 IntelliSense의 단어 자동 완성 목록이 표시됩니다. 키를 눌러 표시 되지 않으면 **Ctrl**+**공간** 를 활성화 합니다.

3. 단어 자동 완성 목록에서 XML 조각을 선택합니다.

4. 키를 눌러 **탭**, **탭** 를 XML 조각을 호출 합니다.

> [!NOTE]
> XML 조각이 호출되지 않는 경우도 있습니다. 예를 들어, `xs:complexType` 요소를 `xs:element` 노드 안에 삽입하려고 시도하면 편집기에서 XML 조각이 생성되지 않습니다. `xs:complexType` 노드 안에서 `xs:element` 요소를 사용하면 필수 특성 또는 하위 요소가 없으므로 편집기에서 삽입할 데이터가 없습니다.

### <a name="to-insert-snippets-using-the-shortcut-name"></a>바로 가기 이름을 사용하여 조각을 삽입하려면

1. XML 조각을 삽입할 커서의 위치를 지정합니다.

2. 편집기 창에 `<`를 입력합니다.

3. 키를 눌러 **Esc** 를 IntelliSense 단어 자동 완성 목록을 닫습니다.

4. 코드 조각 및 키를 눌러의 바로 가기 이름을 입력 **탭** 를 XML 조각을 호출 합니다.

## <a name="surround-with"></a>포함

다음 절차는에 액세스 하는 방법을 설명는 **감싸기** 명령입니다.

> [!NOTE]
> **감싸기** 명령을 바로 가기 키를 통해 사용할 수도 있습니다 (**Ctrl**+**K**, 다음 **Ctrl** + **S**).

### <a name="to-use-surround-with-from-the-context-menu"></a>상황에 맞는 메뉴에서 포함 명령을 사용하려면

1. XML 편집기에 포함시킬 텍스트를 선택합니다.

2. 마우스 오른쪽 단추로 클릭 하 고 선택 **감싸기**합니다.

   사용 가능한 XML 조각 포함 항목의 목록이 표시됩니다.

3. 목록에서 마우스를 사용 하거나 조각 및 키를 눌러의 이름을 입력 하 여 조각을 선택 **탭** 또는 **Enter**합니다.

### <a name="to-use-surround-with-from-the-intellisense-menu"></a>IntelliSense 메뉴에서 포함 명령을 사용 하려면

1. XML 편집기에 포함시킬 텍스트를 선택합니다.

2. **편집** 메뉴에서 **IntelliSense**를 선택한 후 **감싸기**합니다.

   사용 가능한 XML 조각 포함 항목의 목록이 표시됩니다.

3. 목록에서 마우스를 사용 하거나 조각 및 키를 눌러의 이름을 입력 하 여 조각을 선택 **탭** 또는 **Enter**합니다.

## <a name="using-xml-snippets"></a>XML 조각 사용

XML 조각을 선택하면 코드 조각의 텍스트가 커서 위치에 자동으로 삽입됩니다. 조각에서 편집 가능한 필드가 강조되며 편집 가능한 첫 번째 필드가 자동으로 선택됩니다. 현재 선택되어 있는 필드는 상자로 둘러싸여 있습니다.

필드를 선택하면 필드의 새 값을 입력할 수 있습니다. 키를 누르면 **탭** 조각의 편집 가능한 필드 순환; 키를 눌러 **Shift**+**탭** 반대 순서로 순환할 합니다. 필드를 클릭하면 필드 안에 커서가 놓이며 필드를 두 번 클릭하면 필드가 선택됩니다. 필드가 강조된 경우 필드에 대한 설명을 제공하는 도구 설명을 볼 수 있습니다.

주어진 필드의 첫 번째 인스턴스만 편집할 수 있습니다. 이 필드를 강조하면 필드의 나머지 인스턴스에는 테두리가 표시됩니다. 편집 가능한 필드의 값을 변경하면 조각에서 이 필드가 사용된 모든 곳에서 변경됩니다.

키를 누르면 **Enter** 또는 **Esc** 필드 편집이 취소 되 고 기본 편집기 돌아갑니다.

코드 조각 필드 설정을 수정 하 여 편집할 수 있는 코드 조각 필드에 대 한 기본 색을 변경할 수 있습니다는 **글꼴 및 색** 의 창 고 **옵션** 대화 상자. 자세한 내용은 참조 [하는 방법: 글꼴 및 색 편집기에서 변경](../ide/reference/how-to-change-fonts-and-colors-in-the-editor.md)합니다.

## <a name="see-also"></a>참고 항목

- [XML 조각](../xml-tools/xml-snippets.md)
- [방법: XML 스키마에서 XML 조각 생성](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md)
- [방법: XML 조각 만들기](../xml-tools/how-to-create-xml-snippets.md)