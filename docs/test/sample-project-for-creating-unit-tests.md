---
title: Birim testleri oluşturmak için örnek kod
description: Bu makalede, Visual Studio birim testleri ile test örnek kodu sağlıyor.
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: sample
helpviewer_keywords:
- unit test sample [Visual Studio]
- unit tests, samples
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 93a6627b96daefa48c9a72fd84726775fc449bde
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704609"
---
# <a name="sample-code-for-testing"></a>Test etmek için örnek kod

Bu örnek kod bir sınıf içerir *BankAccount*, çeşitli yöntemlerle ile birim testleri test edilebilir.

Bu kod, aşağıdaki yönergelerde kullanılır:

- [Yönetilen kod için birim testleri oluşturma ve çalıştırma](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md). Bu kılavuzda oluşturmak ve birim testlerini özelleştirme, bunları çalıştırmak ve test sonuçlarını inceleyin adımlarında size yol gösterir.
- [Komut satırı test yardımcı programını kullanarak](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867). Bu kılavuzda, testleri çalıştırmak ve sonuçları görüntülemek için MSTest.exe komut satırı yardımcı programını kullanın.

## <a name="sample-code"></a>Örnek kod

Bu örnekte yalnızca maksatlı bir hata içinde borç yöntemi "m_balance += tutar" bir artı oturum önce eşittir işareti eksi olmasıdır.

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

/ * Örnek şirketler, kuruluşlar, ürünler, etki alanı adları, e-posta adresleri, logolar, kişiler, yerler ve sahiplerinin kurgusaldır. Gerçek şirket, kuruluş, ürün, etki alanı adı, e-posta adresi, logo, kişi, yerler veya olayları ile ilişki amaçlanmamıştır veya çıkarılmamalıdır. \*/

## <a name="create-the-project"></a>Projeyi oluşturma

Bu kod ile çalışmak için önce bir proje için Visual Studio'da oluşturun. Projede oluşturmak için aşağıdaki adımları izleyin [izlenecek yol: yönetilen kod için birim testleri oluşturma ve çalıştırma](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#create-a-project-to-test).

## <a name="see-also"></a>Ayrıca bkz.

- [İzlenecek yol: Oluşturma ve yönetilen kod için birim testleri çalıştırma](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)
- [İzlenecek yol: komut satırı test yardımcı programını kullanma](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867)
