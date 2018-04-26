---
title: Visual Studio'da birim testleri oluşturmak için örnek proje
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
ms.openlocfilehash: 0f6ab04990292715932c652e2e275787447761ca
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="sample-project-for-creating-unit-tests"></a>Birim Testleri Oluşturmak için Örnek Proje

Bu örnek kod, aşağıdaki izlenecek kullanım için sağlanır:

- [İzlenecek yol: Oluşturmak ve çalıştırmak için birim testleri yönetilen kod](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md). Bu kılavuzda oluşturmak ve birim testlerini özelleştirme, bunları çalıştırmak ve test sonuçlarını inceleyin adımlarında size yol gösterir.

- [İzlenecek yol: komut satırı test yardımcı programını kullanarak](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867). Bu kılavuzda, testleri çalıştırmak ve sonuçları görüntülemek için MSTest.exe komut satırı yardımcı programını kullanın.

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

## <a name="working-with-the-code"></a>Kodu ile çalışma

Bu kod ile çalışmak için önce bir proje için Visual Studio'da oluşturmanız gerekir. "İzlenecek Yol Hazırlama" bölümündeki adımları [izlenecek yol: yönetilen kod için birim testleri oluşturma ve çalışan](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md).

## <a name="see-also"></a>Ayrıca bkz.

- [İzlenecek yol: Yönetilen Kod için Birim Testleri Oluşturma ve Çalıştırma](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)
- [İzlenecek yol: komut satırı test yardımcı programını kullanma](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867)
