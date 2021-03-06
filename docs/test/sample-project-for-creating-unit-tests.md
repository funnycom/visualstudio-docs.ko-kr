---
title: "단위 테스트를 만들기 위한 샘플 프로젝트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unit test sample [Visual Studio]
- unit tests, samples
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b1b92a223a54c48dd08cce2fc02904f1b66606bc
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="sample-project-for-creating-unit-tests"></a>단위 테스트를 만들기 위한 샘플 프로젝트

이 샘플 코드는 다음 연습에서 사용할 수 있도록 제공됩니다.

- [연습: 관리 코드에 대한 단위 테스트 만들기 및 실행](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md). 이 연습에서는 단위 테스트를 작성, 사용자 지정 및 실행하고 테스트 결과를 검사하는 단계를 안내합니다.

- [연습: 명령줄 테스트 유틸리티 사용](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867). 이 연습에서는 MSTest.exe 명령줄 유틸리티를 사용하여 테스트를 실행하고 결과를 확인합니다.

## <a name="sample-code"></a>샘플 코드

이 샘플에서 의도적으로 발생시켜야 하는 오류는 Debit 메서드 "m_balance += amount"의 등호 앞에 더하기 기호가 아닌 빼기 기호가 있어야 한다는 것뿐입니다.

```csharp
using System;   
  
namespace BankAccountNS  
{  
    /// <summary>   
    /// Bank Account demo class.   
    /// </summary>   
    public class BankAccount  
    {  
        private string m_customerName;  
  
        private double m_balance;  
  
        private bool m_frozen = false;  
  
        private BankAccount()  
        {  
        }  
  
        public BankAccount(string customerName, double balance)  
        {  
            m_customerName = customerName;  
            m_balance = balance;  
        }  
  
        public string CustomerName  
        {  
            get { return m_customerName; }  
        }  
  
        public double Balance  
        {  
            get { return m_balance; }  
        }  
  
        public void Debit(double amount)  
        {  
            if (m_frozen)  
            {  
                throw new Exception("Account frozen");  
            }  
  
            if (amount > m_balance)  
            {  
                throw new ArgumentOutOfRangeException("amount");  
            }  
  
            if (amount < 0)  
            {  
                throw new ArgumentOutOfRangeException("amount");  
            }  
  
            m_balance += amount; // intentionally incorrect code  
        }  
  
        public void Credit(double amount)  
        {  
            if (m_frozen)  
            {  
                throw new Exception("Account frozen");  
            }  
  
            if (amount < 0)  
            {  
                throw new ArgumentOutOfRangeException("amount");  
            }  
  
            m_balance += amount;  
        }  
  
        private void FreezeAccount()  
        {  
            m_frozen = true;  
        }  
  
        private void UnfreezeAccount()  
        {  
            m_frozen = false;  
        }  
  
        public static void Main()  
        {  
            BankAccount ba = new BankAccount("Mr. Bryan Walton", 11.99);   
  
            ba.Credit(5.77);  
            ba.Debit(11.22);  
            Console.WriteLine("Current balance is ${0}", ba.Balance);  
        }
    }
}
```

/* 이 문서에 사용된 예제 회사, 조직, 제품, 도메인 이름, 전자 메일 주소, 로고, 사람, 장소 및 이벤트는 실제 데이터가 아닙니다. 어떠한 실제 회사, 기관, 제품, 도메인 이름, 전자 메일 주소, 로고, 사람, 장소 또는 이벤트와도 연관시킬 의도가 없으며 그렇게 유추해서도 안 됩니다. \*/

## <a name="working-with-the-code"></a>코드 작업

이 코드로 작업하려면 먼저 Visual Studio에서 이를 위한 프로젝트를 만들어야 합니다. [연습: 관리 코드에 대한 단위 테스트 만들기 및 실행](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)에서 "연습 준비" 섹션의 단계를 따르세요.

## <a name="see-also"></a>참고 항목

[연습: 관리 코드에 대한 단위 테스트 만들기 및 실행](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)  
[연습: 명령줄 테스트 유틸리티 사용](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867)
