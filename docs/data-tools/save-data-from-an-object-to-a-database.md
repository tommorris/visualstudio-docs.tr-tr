---
title: Verileri bir nesneden veritabanına kaydetme
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], saving
- data access [Visual Studio], objects
- saving data
ms.assetid: efd6135a-40cf-4b0d-8f8b-41a5aaea7057
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 641b598eb855fb1f2c3a7ca38d966630fbac15bb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31924723"
---
# <a name="save-data-from-an-object-to-a-database"></a>Verileri bir nesneden veritabanına kaydetme
Değerleri, nesneden bir TableAdapter'ın DBDirect yöntemleri geçirerek bir veritabanı nesneleri veri kaydedebilirsiniz (örneğin, `TableAdapter.Insert`). Daha fazla bilgi için bkz: [TableAdapter](../data-tools/create-and-configure-tableadapters.md).

 Veri nesneleri, nesneler (örneğin, bir sonraki için döngü), koleksiyonunun döngü koleksiyonundan kaydedip TableAdapter'ın DBDirect yöntemlerden birini kullanarak her nesnenin değerlerini veritabanına göndermek için.

 Varsayılan olarak, doğrudan veritabanına karşı çalıştırılabilir bir TableAdapter DBDirect yöntemleri oluşturulur. Bu yöntem doğrudan çağrılamaz ve gerektirmeyen <xref:System.Data.DataSet> veya <xref:System.Data.DataTable> bir veritabanına güncelleştirmeleri göndermek için değişiklikleri karşılaştırmak üzere nesneleri.

> [!NOTE]
>  Bir TableAdapter yapılandırırken ana sorgu oluşturulacak DBDirect yöntemleri için yeterli bilgi sağlamanız gerekir. Örneğin, bir TableAdapter sorgu veri tanımlı bir birincil anahtar sütunu yok. bir tablodan yapılandırdıysanız, DBDirect yöntemleri oluşturmaz.

|TableAdapter DBDirect yöntemi|Açıklama|
|----------------------------------|-----------------|
|`TableAdapter.Insert`|Bir veritabanına yeni kayıtlar ekler ve tek sütun değerleri yöntemi parametre olarak geçirmek sağlar.|
|`TableAdapter.Update`|Veritabanındaki kayıtları mevcut güncelleştirir. `Update` Yöntemi özgün ve yeni sütun değerleri yöntemi parametre olarak alır. Özgün değerler özgün kayıt bulmak için kullanılır ve yeni değerler o kaydını güncelleştirmek üzere kullanılır.<br /><br /> `TableAdapter.Update` Yöntemi gerçekleştirerek bir veri kümesinde değişiklikleri veritabanına geri mutabık kılmak için kullanılan aynı zamanda bir <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, <xref:System.Data.DataRow>, veya bir dizi <xref:System.Data.DataRow>s yöntem parametreleri olarak.|
|`TableAdapter.Delete`|Yöntem parametreleri olarak geçirilen özgün sütun değerleri temel alarak veritabanından kayıtları varolan siler.|

### <a name="to-save-new-records-from-an-object-to-a-database"></a>Yeni kayıtlar bir nesneden veritabanına kaydetmek için

-   Değerlere geçirerek kayıtları oluşturma `TableAdapter.Insert` yöntemi.

     Aşağıdaki örnek yeni bir müşteri kaydı oluşturur `Customers` değerlerde geçirerek tablo `currentCustomer` nesnesinin `TableAdapter.Insert` yöntemi.

     [!code-csharp[VbRaddataSaving#23](../data-tools/codesnippet/CSharp/save-data-from-an-object-to-a-database_1.cs)]
     [!code-vb[VbRaddataSaving#23](../data-tools/codesnippet/VisualBasic/save-data-from-an-object-to-a-database_1.vb)]

### <a name="to-update-existing-records-from-an-object-to-a-database"></a>Bir veritabanı için bir nesneden varolan kayıtları güncelleştirmek için

-   Çağırarak kayıtlarını değiştirme `TableAdapter.Update` kaydı güncelleştirmek için yeni değerleri geçirme ile kaydı bulmak için özgün değerleri geçirme yöntemi.

    > [!NOTE]
    >  Bunları geçirmek için özgün değerler korumak, nesnenin gerekiyor `Update` yöntemi. Bu örnek ile özelliklerini kullanır bir `orig` özgün değerlerini depolamak için önek.

     Aşağıdaki örnek uygulamasında varolan bir kayıt güncelleştirmeleri `Customers` yeni ve özgün değerleri geçirerek tablo `Customer` nesnesinin `TableAdapter.Update` yöntemi.

     [!code-csharp[VbRaddataSaving#24](../data-tools/codesnippet/CSharp/save-data-from-an-object-to-a-database_2.cs)]
     [!code-vb[VbRaddataSaving#24](../data-tools/codesnippet/VisualBasic/save-data-from-an-object-to-a-database_2.vb)]

### <a name="to-delete-existing-records-from-a-database"></a>Varolan kayıtlarını veritabanından silmek için

-   Çağırarak kayıtlarını Sil `TableAdapter.Delete` yöntemi ve kaydı bulmak için orijinal değerleri geçirme.

    > [!NOTE]
    >  Bunları geçirmek için özgün değerler korumak, nesnenin gerekiyor `Delete` yöntemi. Bu örnek ile özelliklerini kullanır bir `orig` özgün değerlerini depolamak için önek.

     Aşağıdaki örnek, bir kayıttan siler `Customers` özgün değerleri geçirerek tablo `Customer` nesnesinin `TableAdapter.Delete` yöntemi.

     [!code-csharp[VbRaddataSaving#25](../data-tools/codesnippet/CSharp/save-data-from-an-object-to-a-database_3.cs)]
     [!code-vb[VbRaddataSaving#25](../data-tools/codesnippet/VisualBasic/save-data-from-an-object-to-a-database_3.vb)]

## <a name="net-framework-security"></a>.NET Framework Güvenliği
 Seçili Ekle gerçekleştirmek için izni olmalıdır UPDATE veya DELETE veritabanı tablosunda.

## <a name="see-also"></a>Ayrıca bkz.

- [Verileri yeniden veritabanına kaydetme](../data-tools/save-data-back-to-the-database.md)