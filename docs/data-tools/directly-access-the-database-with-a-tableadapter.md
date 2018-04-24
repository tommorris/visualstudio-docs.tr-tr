---
title: Bir TableAdapter ile veritabanına doğrudan erişim
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- databases [Visual Basic], accessing with a TableAdapter
- DBDirect methods
- datasets [Visual Basic], adding to projects
- data [Visual Studio], saving
- TableAdapter.Delete method
- GenerateDbDirectMethods property
- TableAdapter.Insert method
- TableAdapter.GenerateDBDirectMethods property
- TableAdapter.Update method
- saving data
- TableAdapters
ms.assetid: 012c5924-91f7-4790-b2a6-f51402b7014b
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: b1a3b35cc491ed91e07316444c31cf4a29ef1517
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="directly-access-the-database-with-a-tableadapter"></a>Bir TableAdapter ile veritabanına doğrudan erişim
Ek olarak `InsertCommand`, `UpdateCommand`, ve `DeleteCommand`, TableAdapters doğrudan veritabanına karşı çalışan yöntemleriyle oluşturulur. Bu yöntemler (`TableAdapter.Insert`, `TableAdapter.Update`, ve `TableAdapter.Delete`) doğrudan veritabanındaki verileri işlemek için çağrılabilir.

 Doğrudan bu yöntemleri oluşturmak istemiyorsanız, TableAdapter's ayarlamak `GenerateDbDirectMethods` özelliğine `false` içinde **özellikleri** penceresi. TableAdapter'ın ana sorgu yanı sıra bir TableAdapter sorguları eklenir, bunlar bu DbDirect yöntemleri üretme tek başına sorguları demektir.

## <a name="send-commands-directly-to-a-database"></a>Bir veritabanına doğrudan komut gönderme
 Elde etmeye çalıştığınız görevi gerçekleştiren TableAdapter DbDirect yöntemini çağırın.

#### <a name="to-insert-new-records-directly-into-a-database"></a>Doğrudan bir veritabanına yeni kayıtlar eklemek için

-   TableAdapter's çağrı `Insert` yöntemi, değerlerin her sütun için parametre olarak geçirme. Aşağıdaki yordam kullanır `Region` bir örnek olarak Northwind veritabanı tablosunda.

    > [!NOTE]
    >  Kullanılabilir bir örnek yoksa, kullanmak istediğiniz TableAdapter örneği oluşturur.

     [!code-vb[VbRaddataSaving#15](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_1.vb)]
     [!code-csharp[VbRaddataSaving#15](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_1.cs)]

#### <a name="to-update-records-directly-in-a-database"></a>Doğrudan veritabanındaki kayıtları güncelleştirme

-   TableAdapter's çağrı `Update` yöntemi, yeni ve özgün değerleri her sütun için parametre olarak geçirme.

    > [!NOTE]
    >  Kullanılabilir bir örnek yoksa, kullanmak istediğiniz TableAdapter örneği oluşturur.

     [!code-vb[VbRaddataSaving#18](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_2.vb)]
     [!code-csharp[VbRaddataSaving#18](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_2.cs)]

#### <a name="to-delete-records-directly-from-a-database"></a>Kayıtları doğrudan veritabanından silmek için

-   TableAdapter's çağrısı `Delete` yöntemi, değerlerin her sütun için parametre olarak geçirme `Delete` yöntemi. Aşağıdaki yordam kullanır `Region` bir örnek olarak Northwind veritabanı tablosunda.

    > [!NOTE]
    >  Kullanılabilir bir örnek yoksa, kullanmak istediğiniz TableAdapter örneği oluşturur.

     [!code-vb[VbRaddataSaving#21](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_3.vb)]
     [!code-csharp[VbRaddataSaving#21](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_3.cs)]

## <a name="see-also"></a>Ayrıca bkz.

- [TableAdapters kullanarak veri kümelerini doldurma](../data-tools/fill-datasets-by-using-tableadapters.md)