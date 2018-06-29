---
title: Veritabanına yeni kayıtlar ekleme
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- TableAdapters, inserting new records into
- data [Visual Studio], saving
- databases, inserting new records into
- records, inserting
- saving data
ms.assetid: ea118fff-69b1-4675-b79a-e33374377f04
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 515140564d9523c9f1dfe6b3b904aaa3b37df45f
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089577"
---
# <a name="insert-new-records-into-a-database"></a>Veritabanına yeni kayıtlar ekleme
Bir veritabanına yeni kayıtlar eklemek için kullanabileceğiniz `TableAdapter.Update` yöntemi ya da bir TableAdapter'ın DBDirect yöntemleri (özellikle `TableAdapter.Insert` yöntemi). Daha fazla bilgi için bkz: [TableAdapter](../data-tools/create-and-configure-tableadapters.md).

 Uygulamanızı TableAdapters kullanmıyorsa, komut nesneleri kullanabilirsiniz (örneğin, <xref:System.Data.SqlClient.SqlCommand>) veritabanınızdaki yeni kayıtları eklemek için.

 Verileri depolamak için veri kümeleri, uygulamanızın kullanıyorsa kullanın `TableAdapter.Update` yöntemi. `Update` Yöntemi (güncelleştirmeler, ekler ve siler) tüm değişiklikleri veritabanına gönderir.

 Uygulamanızın veri depolamak veya veritabanında yeni kayıtlar oluşturma daha iyi denetleyebilmek isterseniz kullanmak için nesneleri kullanıp kullanmadığını `TableAdapter.Insert` yöntemi.

 TableAdapter yoksa, bir `Insert` yöntemi, geldiğini ya da TableAdapter saklı yordamları kullanmak için yapılandırıldığını veya kendi `GenerateDBDirectMethods` özelliği ayarlanmış `false`. TableAdapter's ayarlamayı deneyin `GenerateDBDirectMethods` özelliğine `true` içinden **veri kümesi Tasarımcısı**ve ardından veri kümesini kaydedin. Bu, TableAdapter yeniden oluşturacak. TableAdapter hala yoksa, bir `Insert` yöntemi, tablo büyük olasılıkla sağlamaz arasında tek tek satırları ayırt etmek için yeterli şema bilgileri (örneğin, olabilir tablosundaki birincil bir anahtar ayarı yok).

## <a name="insert-new-records-by-using-tableadapters"></a>TableAdapters kullanarak yeni kayıtlar ekleme
 TableAdapters, uygulamanızın gereksinimlerine bağlı olarak bir veritabanına yeni kayıtlar eklemek için farklı yollar sağlar.

 Uygulama verilerini depolamak için veri kümeleri kullanıyorsa, yalnızca yeni kayıtları istenen ekleyebileceğiniz <xref:System.Data.DataTable> veri kümesi ve ardından arama `TableAdapter.Update` yöntemi. `TableAdapter.Update` Yöntemi herhangi bir değişiklik gönderir <xref:System.Data.DataTable> (değiştirilen ve silinen kayıtları dahil) veritabanı.

### <a name="to-insert-new-records-into-a-database-by-using-the-tableadapterupdate-method"></a>TableAdapter.Update yöntemi kullanarak bir veritabanına yeni kayıtlar eklemek için

1.  Yeni kayıtlar için istenen eklemek <xref:System.Data.DataTable> yeni oluşturarak <xref:System.Data.DataRow> ve eklemeyi <xref:System.Data.DataTable.Rows%2A> koleksiyonu.

2.  Yeni satırlar eklendikten sonra <xref:System.Data.DataTable>, çağrı `TableAdapter.Update` yöntemi. Ya da tüm geçirerek güncelleştirmek için veri miktarını denetleyebilir <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, bir dizi <xref:System.Data.DataRow>s ya da tek bir <xref:System.Data.DataRow>.

 Aşağıdaki kod, yeni bir kayıt eklemek gösterilmiştir bir <xref:System.Data.DataTable> ve ardından arama `TableAdapter.Update` yeni satır veritabanına kaydetmek için yöntem. (Bu örnekte `Region` Northwind veritabanı tablosunda.)

 [!code-vb[VbRaddataSaving#14](../data-tools/codesnippet/VisualBasic/insert-new-records-into-a-database_1.vb)]
 [!code-csharp[VbRaddataSaving#14](../data-tools/codesnippet/CSharp/insert-new-records-into-a-database_1.cs)]

### <a name="to-insert-new-records-into-a-database-by-using-the-tableadapterinsert-method"></a>TableAdapter.INSERT yöntemi kullanarak bir veritabanına yeni kayıtlar eklemek için
Uygulama verilerini depolamak için nesneleri kullanıyorsa, kullanabileceğiniz `TableAdapter.Insert` doğrudan veritabanında yeni satırlar oluşturmak için yöntemi. `Insert` Yöntemi her sütun değerlerini ayrı ayrı parametre olarak kabul eder. Yeni bir kayıt yöntemini çağırarak geçirilen parametre değerleri ile veritabanına ekler.

- TableAdapter's çağrı `Insert` yöntemi, değerlerin her sütun için parametre olarak geçirme.

 Aşağıdaki yordamı kullanarak gösteren `TableAdapter.Insert` satır eklemek için yöntem. Bu örnek verileri ekler `Region` Northwind veritabanı tablosunda.

 > [!NOTE]
 >  Kullanılabilir bir örnek yoksa, kullanmak istediğiniz TableAdapter örneği oluşturur.

 [!code-vb[VbRaddataSaving#15](../data-tools/codesnippet/VisualBasic/insert-new-records-into-a-database_2.vb)]
 [!code-csharp[VbRaddataSaving#15](../data-tools/codesnippet/CSharp/insert-new-records-into-a-database_2.cs)]

## <a name="insert-new-records-by-using-command-objects"></a>Komut nesneleri kullanarak yeni kayıtlar ekleme
Doğrudan komut nesneleri kullanarak bir veritabanına yeni kayıtlar ekleyebilirsiniz.

### <a name="to-insert-new-records-into-a-database-by-using-command-objects"></a>Komut nesneleri kullanarak bir veritabanına yeni kayıtlar eklemek için

-   Yeni bir komut nesnesi oluşturun ve ardından kendi `Connection`, `CommandType`, ve `CommandText` özellikleri.

 Aşağıdaki örnek komut nesnesi kullanılarak bir veritabanına ekleme kayıtları gösterilmektedir. Verileri ekler `Region` Northwind veritabanı tablosunda.

 [!code-vb[VbRaddataSaving#16](../data-tools/codesnippet/VisualBasic/insert-new-records-into-a-database_3.vb)]
 [!code-csharp[VbRaddataSaving#16](../data-tools/codesnippet/CSharp/insert-new-records-into-a-database_3.cs)]

## <a name="net-framework-security"></a>.NET Framework güvenliği
 İstenen tabloya ekler gerçekleştirme izni yanı sıra, bağlanmaya çalıştığınız veritabanı erişimi olmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

- [Verileri yeniden veritabanına kaydetme](../data-tools/save-data-back-to-the-database.md)