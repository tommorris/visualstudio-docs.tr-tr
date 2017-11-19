---
title: "TableAdapter kullanarak veri güncelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], saving
- data [Visual Studio], TableAdapters
- updating data, TableAdapters
- TableAdapters, updating data
- data [Visual Studio], updating
- saving data
ms.assetid: 5e32e10e-9bac-4969-9bdd-b8f6919d3516
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 7d49f0ddc965327334aea471b1276b4e78987ec2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="update-data-by-using-a-tableadapter"></a>TableAdapter kullanarak veri güncelleştirme
Veri kümenizi verilerde değişiklik ve doğrulanmış sonra güncelleştirilen verileri bir veritabanına geri çağırarak gönderebilirsiniz `Update` yöntemi bir [TableAdapter](../data-tools/create-and-configure-tableadapters.md). `Update` Yöntemi bir tek veri tablosunu güncelleştirir ve göre doğru komutu (INSERT, UPDATE veya DELETE) çalıştıran <xref:System.Data.DataRow.RowState%2A> tablosundaki her veri satırının. Bir veri kümesi ilişkili tabloları, Visual Studio güncelleştirmeler yapmak için kullandığınız bir TableAdapterManager sınıfı oluşturur. TableAdapterManager sınıfı güncelleştirmeleri veritabanında tanımlı yabancı anahtar kısıtlamaları göre doğru sırada yapılan sağlar. Verilere bağlı denetimler kullandığınızda, veri bağlama mimarisi tableAdapterManager adlı TableAdapterManager sınıfının üye değişkeni oluşturur. 
  
> [!NOTE]
>  Bir veri kaynağı bir veri kümesi içeriğini güncelleştirmeye çalıştığınızda hata alabilirsiniz. Hataları önlemek için bağdaştırıcının çağıran kodu put öneririz `Update` yönteminin içinde bir `try` / `catch` bloğu.  
  
 Bir veri kaynağını güncelleme tam yordamı iş gereksinimlerine bağlı olarak farklılık gösterebilir, ancak aşağıdaki adımları içerir:  
  
1.  Bağdaştırıcının çağrısı `Update` yönteminde bir `try` / `catch` bloğu.  
  
2.  Bir özel durum yakalandı, hatanın nedeni veri satırı bulun. 
  
3.  Veri sorunu mutabık kılmak (programlı olarak yapabiliyorsanız veya geçersiz bir satır için değişiklik kullanıcıya sunarak) satırın ve güncelleştirmeyi yeniden deneyin (<xref:System.Data.DataRow.HasErrors%2A>, <xref:System.Data.DataTable.GetErrors%2A>).  
  
## <a name="save-data-to-a-database"></a>Verileri bir veritabanına kaydetme  
 Çağrı `Update` bir TableAdapter yöntemi. Veritabanına yazılan değerleri içeren veri tablonun adını geçirin.  
  
#### <a name="to-update-a-database-by-using-a-tableadapter"></a>TableAdapter kullanarak bir veritabanını güncelleştirmek için  
  
-   TableAdapter's içine`Update` yönteminde bir `try` / `catch` bloğu. Aşağıdaki örnek, içeriği güncelleştirmek gösterilmiştir `Customers` tablosundaki `NorthwindDataSet` içinden bir `try` / `catch` bloğu.  
  
     [!code-csharp[VbRaddataSaving#9](../data-tools/codesnippet/CSharp/update-data-by-using-a-tableadapter_1.cs)]
     [!code-vb[VbRaddataSaving#9](../data-tools/codesnippet/VisualBasic/update-data-by-using-a-tableadapter_1.vb)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veritabanına veri kaydetme](../data-tools/save-data-back-to-the-database.md)