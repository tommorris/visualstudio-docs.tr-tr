---
title: "Örnek Proje Birim testleri oluşturmak için | Microsoft Docs"
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
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: 500b3a3c28b2ccb07e8fb61552aff9c427d780d6
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="sample-project-for-creating-unit-tests"></a>Birim Testleri Oluşturmak için Örnek Proje
Bu örnek kod, aşağıdaki izlenecek kullanım için sağlanır:  
  
-   [İzlenecek yol: Oluşturmak ve çalıştırmak için birim testleri yönetilen kod](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md). Bu kılavuzda oluşturmak ve birim testlerini özelleştirme, bunları çalıştırmak ve test sonuçlarını inceleyin adımlarında size yol gösterir.  
  
-   [İzlenecek yol: Testleri çalıştırın ve kod kapsamı görüntülemek](http://msdn.microsoft.com/en-us/d4aab8e2-2140-4975-b4e3-41ef3fa944c8). Bu kılavuzda test edilmekte olan projenizin kod oranını gösterir kod kapsamı verilerini görüntülemek nasıl gösterilmektedir.  
  
-   [İzlenecek yol: komut satırı test yardımcı programını kullanarak](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867). Bu kılavuzda, testleri çalıştırmak ve sonuçları görüntülemek için MSTest.exe komut satırı yardımcı programını kullanın.  
  
## <a name="sample-code"></a>Örnek kod  
 Bu örnekte yalnızca maksatlı bir hata içinde borç yöntemi "m_balance += tutar" bir artı oturum önce eşittir işareti eksi olmasıdır.  
  
```  
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
  
 / * Örnek şirketler, kuruluşlar, ürünler, etki alanı adları, e-posta adresleri, logolar, kişiler, yerler ve sahiplerinin kurgusaldır.  Gerçek şirket, kuruluş, ürün, etki alanı adı, e-posta adresi, logo, kişi, yerler veya olayları ile ilişki amaçlanmamıştır veya çıkarılmamalıdır. \*/  
  
## <a name="working-with-the-code"></a>Kodu ile çalışma  
 Bu kod ile çalışmak için önce içinde için bir proje oluşturmak zorunda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. "İzlenecek Yol Hazırlama" bölümündeki adımları [izlenecek yol: yönetilen kod için birim testleri oluşturma ve çalışan](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen kod için birim testleri izlenecek yol: Oluşturma ve çalıştırma](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)   
 [İzlenecek yol: testleri çalıştırın ve kod kapsamı görüntüleyin](http://msdn.microsoft.com/en-us/d4aab8e2-2140-4975-b4e3-41ef3fa944c8)   
 [İzlenecek yol: komut satırı test yardımcı programını kullanma](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867)
