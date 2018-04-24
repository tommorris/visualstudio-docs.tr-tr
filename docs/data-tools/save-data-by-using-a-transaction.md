---
title: 'Nasıl yapılır: bir işlemi kullanarak veri kaydetme'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- saving data, using transactions
- System.Transactions namespace
- transactions, saving data
- data [Visual Studio], saving
ms.assetid: 8b835e8f-34a3-413d-9bb5-ebaeb87f1198
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 8b4fd7ad7168edc155227f9c26cb6f93454240dd
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-save-data-by-using-a-transaction"></a>Nasıl yapılır: bir işlemi kullanarak veri kaydetme
Kullanarak bir işlemde veri kaydetme <xref:System.Transactions> ad alanı. Kullanım <xref:System.Transactions.TransactionScope> sizin için otomatik olarak yönetilen bir işlemde katılmak için nesne.

İşlemler kullanan projelerin başvuru el ile eklemeniz gerekir böylece projeleri System.Transactions derlemesine başvuru oluşturulmaz.

Örneği oluşturmak için bir işlem uygulamak için en kolay yolu olan bir <xref:System.Transactions.TransactionScope> nesnesinde bir `using` deyimi. (Daha fazla bilgi için bkz: [kullanarak deyimi](/dotnet/visual-basic/language-reference/statements/using-statement), ve [deyimiyle](/dotnet/csharp/language-reference/keywords/using-statement).) İçinde çalışan bir kod `using` deyimi işlemde katılır.

İşlem gerçekleştirmeyi çağrı <xref:System.Transactions.TransactionScope.Complete%2A> yöntemi kullanarak son deyim olarak engelleyin.

İşlem geri almak için bir özel durum çağrılmadan önce throw <xref:System.Transactions.TransactionScope.Complete%2A> yöntemi.

## <a name="to-add-a-reference-to-the-systemtransactionsdll"></a>System.Transactions.dll başvuru eklemek için

1.  Üzerinde **proje** menüsünde, select **Başvuru Ekle**.

2.  Üzerinde **.NET** sekmesinde (**SQL Server** SQL Server projeleri için sekme), select **System.Transactions**ve ardından **Tamam**.

     Bir başvuru System.Transactions.dll projeye eklenir.

## <a name="to-save-data-in-a-transaction"></a>Bir işlemde veri kaydetme

-   Kullanarak içinde verileri kaydetmek için kod ekleme deyimi, işlem içerir. Aşağıdaki kod oluşturma ve örneği gösterir bir <xref:System.Transactions.TransactionScope> kullanarak bir nesne deyimi:

     [!code-vb[VbRaddataSaving#11](../data-tools/codesnippet/VisualBasic/save-data-by-using-a-transaction_1.vb)]
     [!code-csharp[VbRaddataSaving#11](../data-tools/codesnippet/CSharp/save-data-by-using-a-transaction_1.cs)]

## <a name="see-also"></a>Ayrıca bkz.

- [Verileri yeniden veritabanına kaydetme](../data-tools/save-data-back-to-the-database.md)
- [İzlenecek yol: Bir işlemde veri kaydetme](../data-tools/save-data-in-a-transaction.md)