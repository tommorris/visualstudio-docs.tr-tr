---
title: TableAdapters kullanarak veri kümelerini doldurma
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- datasets [Visual Basic]
- datasets [Visual Basic], loading data
- data retrieval
- retrieving data
- datasets [Visual Basic], filling
- data [Visual Studio], retrieving
- data [Visual Studio], datasets
ms.assetid: 55f3bfbe-db78-4486-add3-c62f49e6b9a0
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 49f3aad9adf319c09097324a6c40a4aa7b8f6692
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="fill-datasets-by-using-tableadapters"></a>TableAdapters kullanarak veri kümelerini doldurma
Bir TableAdapter bileşeni veritabanından bir veya daha fazla sorgular veya belirttiğiniz saklı yordamlar göre verileri içeren bir veri kümesi doldurur. TableAdapters de gerçekleştirebilir ekler, güncelleştirmeleri ve veri kümesi için yaptığınız değişiklikleri kalıcı hale getirmek için veritabanı üzerinde siler. Ayrıca, belirli bir tabloya ilgisiz Genel komutlar da verebilir.

> [!NOTE]
>  TableAdapters Visual Studio tasarımcıları tarafından üretilir. Veri kümeleri programlı olarak oluşturuyorsanız, .NET Framework sınıf DataAdapter kullanın.

 TableAdapter işlemleri hakkında ayrıntılı bilgi için doğrudan aşağıdaki konulardan birine atlayabilirsiniz:

|Konu|Açıklama|
|-----------|-----------------|
|[TableAdapter’lar oluşturma ve yapılandırma](../data-tools/create-and-configure-tableadapters.md)|Tasarımcılar oluşturmak ve TableAdapters yapılandırmak için kullanma|
|[Parametreleştirilmiş TableAdapter sorguları oluşturma](../data-tools/create-parameterized-tableadapter-queries.md)|TableAdapter yordamları veya sorguları için bağımsız değişkenleri eklemek kullanıcıları etkinleştirme|
|[Bir TableAdapter ile veritabanına doğrudan erişme](../data-tools/directly-access-the-database-with-a-tableadapter.md)|TableAdapters Dbdirect yöntemleri kullanma|
|[Bir veri kümesini doldururken kısıtlamaları kapatma](../data-tools/turn-off-constraints-while-filling-a-dataset.md)|Veri güncelleştirirken yabancı anahtar kısıtlamaları ile çalışma|
|[Bir TableAdapter işlevini genişletme](../data-tools/fill-datasets-by-using-tableadapters.md)|TableAdapters için özel kod ekleme|
|[Bir veri kümesinin içine XML verileri okuma](../data-tools/read-xml-data-into-a-dataset.md)|XML ile çalışma|

<a name="tableadapter-overview"></a>

## <a name="tableadapter-overview"></a>TableAdapter genel bakış
 TableAdapters bir veritabanı, çalışma sorguları ya da saklı yordamları ve bunların DataTable döndürülen verilerle doldurmak tasarımcısı tarafından oluşturulan bileşenleridir. TableAdapters güncelleştirilen verileri veritabanına uygulamanızdan de gönderir. TableAdapter ilişkili olduğu tablo şemaya uyan veri döndürmeleri sürece bir TableAdapter üzerinde istediğiniz tüm sorguları çalıştırabilirsiniz. Aşağıdaki diyagramda, veritabanları ve diğer nesnelerle bellekte TableAdapters nasıl etkileşim kurduğu gösterilmektedir:

 ![Bir istemci uygulamasında veri akışı](../data-tools/media/clientdatadiagram.gif "ClientDataDiagram")

 TableAdapters ile tasarlanmıştır sırada **veri kümesi Tasarımcısı**, TableAdapter sınıfları iç içe geçmiş sınıflar oluşturulmaz <xref:System.Data.DataSet>. Bunlar her veri kümesi için belirli ayrı ad alanları bulunur. Adlı bir veri varsa, örneğin, `NorthwindDataSet`, ilişkili TableAdapters <xref:System.Data.DataTable>s `NorthwindDataSet` içinde olacaktır `NorthwindDataSetTableAdapters` ad alanı. Belirli bir TableAdapter bağdaştırıcısına program aracılığıyla erişmek için TableAdapter'ın yeni bir örneğini bildirmeniz gerekir. Örneğin:

 [!code-csharp[VbRaddataTableAdapters#7](../data-tools/codesnippet/CSharp/fill-datasets-by-using-tableadapters_1.cs)]
 [!code-vb[VbRaddataTableAdapters#7](../data-tools/codesnippet/VisualBasic/fill-datasets-by-using-tableadapters_1.vb)]

## <a name="associated-datatable-schema"></a>İlişkili DataTable şeması
 Bir TableAdapter oluşturduğunuzda, ilk sorguyu kullanın veya TableAdapter şemasını tanımlamak için saklı yordam ilişkili <xref:System.Data.DataTable>. Bu ilk sorguyu çalıştırmak veya saklı yordam TableAdapter's çağırarak `Fill` yöntemi (TableAdapter doldurur ilişkili <xref:System.Data.DataTable>). TableAdapter'ın ana sorguya yapılan değişiklikleri ilişkili veri tablosu şemada yansıtılır. Örneğin, ana sorgudan bir sütun kaldırma da sütun ilişkili veriler tablodan kaldırır. TableAdapter üzerinde herhangi bir ek sorgu ana sorguda olmayan sütunları dönüş SQL deyimlerini kullanırsanız, ana sorgu ve ek sorgular arasında sütun değişiklikleri eşitlemek Tasarımcı çalışır.

## <a name="tableadapter-update-commands"></a>TableAdapter güncelleştirme komutları
 Bir TableAdapter güncelleştirme işlevselliğini ne kadar bilgi TableAdapter Sihirbazı'nı ana sorgusunda kullanılabilir olduğuna bağlıdır. Örneğin, değerleri birden çok tablodan (JOIN), skalar değerden veya görünümden ya da toplu işlevlerin sonuçlarından alacak şekilde yapılandırılan TableAdapter bağdaştırıcıları, başlangıçta güncelleştirmeleri temel alınan veritabanına geri gönderebilme özelliğiyle oluşturulmaz. Ancak, INSERT, UPDATE ve DELETE komutları el ile yapılandırabilirsiniz **özellikleri** penceresi.

## <a name="tableadapter-queries"></a>TableAdapter sorguları
 ![Birden çok sorguyla TableAdapter](../data-tools/media/tableadapter.gif "TableAdapter")

 TableAdapters ilişkili veri tablolarıyla doldurmak için birden çok sorgu içerebilir. Bir TableAdapter için, her sorgu ilişkili olduğu veri tablosunun şemasına uyan veriler döndürdüğü sürece, uygulamanızın gerektirdiği sayıda sorgu tanımlayabilirsiniz. Bu özellik farklı ölçütlere göre farklı sonuçlar yüklemek bir TableAdapter sağlar.

 Örneğin, uygulamanızın müşteri adları içeren bir tablo içeriyorsa, aynı durumda bulunan tüm müşterilerle tabloyu doldurur tablo belirli bir harfle başlayan her müşteri adı ve başka ile doldurur. bir sorgu oluşturabilirsiniz. Doldurmak için bir `Customers` tablo belirli bir durumda olan müşteriler, oluşturduğunuz bir `FillByState` gibi durum değeri için bir parametre alan sorgu: `SELECT * FROM Customers WHERE State = @State`. Çağırarak sorgusu `FillByState` yöntemi ve parametre değeri bilgilerinde gibi bu: `CustomerTableAdapter.FillByState("WA")`.

 TableAdapter'ın veri tablosu aynı şemasının veri döndüren sorgular ekleme ek olarak, skaler (tek) değerler döndüren sorgular ekleyebilirsiniz. Örneğin, müşteriler sayısını döndüren bir sorgu (`SELECT Count(*) From Customers`) için geçerli bir `CustomersTableAdapter,` rağmen döndürülen verileri tablonun şemaya uygun değil.

## <a name="clearbeforefill-property"></a>ClearBeforeFill özelliği
 Varsayılan olarak, her zaman bir TableAdapter'ın veri tablosu doldurmak için bir sorgu çalıştırın, varolan veriler silinir ve yalnızca sorgu sonuçlarını tabloya yüklenir. TableAdapter's ayarlamak `ClearBeforeFill` özelliğine `false` eklemek veya var olan verilere veri tablosunda bir sorgudan döndürülen verileri birleştirmek istiyorsanız. Bunları kalıcı hale getirmek istiyorsanız verileri silmek mi bağımsız olarak, açıkça güncelleştirmeleri veritabanına geri göndermek için gerekir. Bu nedenle herhangi bir değişiklik tablodaki verileri için tabloyu doldurur başka bir sorgu çalıştırmadan önce kaydetmeyi unutmayın. Daha fazla bilgi için bkz: [TableAdapter kullanarak veri güncelleştirme](../data-tools/update-data-by-using-a-tableadapter.md).

## <a name="tableadapter-inheritance"></a>TableAdapter devralma
 TableAdapters genişletme standart veri bağdaştırıcıları işlevselliğini yapılandırılan bir kapsülleyerek <xref:System.Data.Common.DataAdapter> sınıfı. Varsayılan olarak, TableAdapter devraldığı <xref:System.ComponentModel.Component> sınıfı ve yayınlanamıyor <xref:System.Data.Common.DataAdapter> sınıfı. Bir TableAdapter atama <xref:System.Data.Common.DataAdapter> sınıf sonuçlarında bir <xref:System.InvalidCastException> hata. Bir TableAdapter temel sınıfını değiştirmek için türeyen bir sınıf belirtebilirsiniz <xref:System.ComponentModel.Component> içinde **temel sınıf** TableAdapter içinde özelliğinin **veri kümesi Tasarımcısı**.

## <a name="tableadapter-methods-and-properties"></a>TableAdapter yöntemleri ve özellikleri
 TableAdapter sınıfı değil parçası [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Bu, olamaz aramak onu belgelerindeki anlamına gelir veya **Nesne Tarayıcısı**. Daha önce bahsedilen sihirbazlardan birini kullandığınızda tasarım zamanında oluşturulur. Oluşturduğunuzda bir TableAdapter atadığınız ad çalıştığınız tablonun adını temel alır. Örneğin, adlı bir veritabanı tablosunda dayalı bir TableAdapter oluşturduğunuzda `Orders`, TableAdapter adlı `OrdersTableAdapter`. TableAdapter sınıf adı kullanılarak değiştirilebilir **adı** özelliğinde **veri kümesi Tasarımcısı**.

 TableAdapters özelliklerini ve yaygın olarak kullanılan yöntemler şunlardır:

|Üye|Açıklama|
|------------|-----------------|
|`TableAdapter.Fill`|TableAdapter bağdaştırıcısının ilişkili veri tablosunu TableAdapter'ın SELECT komutunun sonuçlarıyla doldurur.|
|`TableAdapter.Update`|Değişiklikler veritabanına geri gönderir ve güncelleştirme tarafından etkilenen satırların sayısını temsil eden bir tamsayı döndürür. Daha fazla bilgi için bkz: [TableAdapter kullanarak veri güncelleştirme](../data-tools/update-data-by-using-a-tableadapter.md).|
|`TableAdapter.GetData`|Yeni bir döndürür <xref:System.Data.DataTable> verilerle doldurulur.|
|`TableAdapter.Insert`|Veri tablosunda yeni bir satır oluşturur. Daha fazla bilgi için bkz: [bir veritabanına yeni kayıtlar ekleme](../data-tools/insert-new-records-into-a-database.md).|
|`TableAdapter.ClearBeforeFill`|`Fill` yöntemlerinden birini çağırmadan önce veri tablosunun boşaltılıp boşaltılmadığını belirler.|

## <a name="tableadapter-update-method"></a>TableAdapter güncelleştirme yöntemi
 TableAdapter bağdaştırıcıları veritabanından okuma ve yazma yapmak için veri komutlarını kullanır. TableAdapter ilk `Fill` (ana) sorgu ilişkili veriler tablonun şeması oluşturmak için temel olarak kullanılır yanı sıra `InsertCommand`, `UpdateCommand`, ve `DeleteCommand` ilişkili komutları `TableAdapter.Update` yöntemi. TableAdapter's çağırma `Update` yöntemi çalışır TableAdapter ilk kez yüklendiğinde, oluşturulan deyimleri yapılandırılmış, ile eklenen ek sorguların bir **TableAdapter sorgu Yapılandırma Sihirbazı'nı**.

 Bir TableAdapter kullandığınızda, aynı işlemleri genelde uyguladığınız komutlarla etkin bir şekilde gerçekleştirir. Örneğin, bağdaştırıcının çağırdığınızda `Fill` yöntemi, bağdaştırıcı veri komutu çalıştırır kendi `SelectCommand` özelliği ve bir veri okuyucu kullanır (örneğin, <xref:System.Data.SqlClient.SqlDataReader>) sonuç veri tabloya kümesini yüklemek için. Benzer şekilde, bağdaştırıcının çağırdığınızda `Update` yöntemi, uygun komutu çalıştırır (içinde `UpdateCommand`, `InsertCommand`, ve `DeleteCommand` özellikleri) her biri için veri tablosu kaydında değiştirildi.

> [!NOTE]
>  Ana sorguda yeterli bilgi varsa `InsertCommand`, `UpdateCommand` ve `DeleteCommand` komutları TableAdapter oluşturulduğunda varsayılan olarak oluşturulur. TableAdapter'ın ana sorgu birden çok tek tablo SELECT deyimi ise, Tasarımcı oluşturmak mümkün olmayacak mümkündür `InsertCommand`, `UpdateCommand`, ve `DeleteCommand`. Bu komutlar oluşturulmaz, çalışırken bir hata alabilirsiniz `TableAdapter.Update` yöntemi.

## <a name="tableadapter-generatedbdirectmethods"></a>TableAdapter GenerateDBDirectMethods Özelliği
 Ek olarak `InsertCommand`, `UpdateCommand`, ve `DeleteCommand`, TableAdapters doğrudan veritabanına karşı çalışan yöntemleriyle oluşturulur. Bu yöntemler (`TableAdapter.Insert`, `TableAdapter.Update` ve `TableAdapter.Delete`) veritabanındaki verileri işlemek için doğrudan çağrılabilir. Bu kodunuzdan çağırmak yerine bu tek tek yöntemleri çağırabilir anlamına gelir `TableAdapter.Update` ekler, güncelleştirmeleri ve bekleyen silme işlemek için ilişkili veri tablosu için.

 Doğrudan bu yöntemleri oluşturmak istemiyorsanız, TableAdapter's ayarlamak **GenerateDbDirectMethods** özelliğine `false` (içinde **özellikleri** penceresi). TableAdapter eklenen ek sorgular olan tek başına sorguları — bu yöntemleri üretme.

## <a name="tableadapter-support-for-nullable-types"></a>Boş değer atanabilir türler TableAdapter desteği
 TableAdapters destek boş değer atanabilir türler `Nullable(Of T)` ve `T?`. Visual Basic'te boş değer atanabilir türler hakkında daha fazla bilgi için bkz: [boş değer atanabilir değer türlerinin](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types). C# boş değer atanabilir türler hakkında daha fazla bilgi için bkz: [kullanarak boş değer atanabilir türler](/dotnet/csharp/programming-guide/nullable-types/using-nullable-types).

<a name="tableadaptermanager-reference"></a>

## <a name="tableadaptermanager-reference"></a>TableAdapterManager başvurusu
 Varsayılan olarak, bir `TableAdapterManager` sınıfı ilişkili tabloları içeren bir veri kümesi oluşturduğunuzda oluşturulur. Sınıf oluşturulmasını önler önlemek için değerini değiştirme `Hierarchical Update` özelliği false veri kümesi. Windows Form veya WPF sayfasının tasarım yüzeyine bir ilişkisi olan bir tabloda sürüklediğinizde, Visual Studio sınıfının üye değişkeni bildirir. Veri bağlama kullanmıyorsanız, el ile değişkeni bildirmeniz gerekir.

 `TableAdapterManager` Sınıfı değil parçası [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Bu nedenle, onu belgelerindeki bakarak olamaz. Veri kümesi oluşturma işleminin bir parçası olarak tasarım zamanında oluşturulur.

 Sık kullanılan yöntemleri ve özellikleri şunlardır `TableAdapterManager` sınıfı:

|Üye|Açıklama|
|------------|-----------------|
|`UpdateAll` Yöntemi|Tüm veri tablolarından tüm verileri kaydeder.|
|`BackUpDataSetBeforeUpdate` Özelliği|Veri kümesi yedek bir kopyasını yürütmeden önce oluşturulup oluşturulmayacağını belirler `TableAdapterManager.UpdateAll` yöntemi. Boole değeri.|
|*tableName* `TableAdapter` özelliği|Temsil eden bir `TableAdapter`. Oluşturulan `TableAdapterManager` her biri için bir özellik içeriyor `TableAdapter` yönettiği. Örneğin, müşteriler ve siparişler bir tablo içeren bir veri kümesi ile oluşturulan bir `TableAdapterManager` içeren `CustomersTableAdapter` ve `OrdersTableAdapter` özellikleri.|
|`UpdateOrder` Özelliği|Tek tek INSERT, update ve delete komutları sırasını denetler. Bu ayarlar değerlerden birine `TableAdapterManager.UpdateOrderOption` numaralandırması.<br /><br /> Varsayılan olarak, `UpdateOrder` ayarlanır **InsertUpdateDelete**. Ekler, sonra güncelleştirir ve ardından siler deyişle kümesindeki tüm tablolar için gerçekleştirilir.|

## <a name="security"></a>Güvenlik
Ayarlanan CommandType özelliği ile veri komutları kullandığınızda <xref:System.Data.CommandType.Text>, dikkatlice veritabanınıza geçirmeden önce bir istemciden gönderilen bilgilere bakın. Kötü niyetli kullanıcılar göndermeyi deneyin (Ekle) yetkisiz erişim elde veya veritabanının zarar verecek çaba değiştirilmiş veya ek SQL deyimlerinde. Bir veritabanı için kullanıcı girişi aktarmadan önce her zaman bilgilerin geçerli olduğunu doğrulayın. Her zaman parametreli sorgular veya saklı yordamlar mümkün olduğunda kullanmak iyi bir uygulamadır.

## <a name="see-also"></a>Ayrıca bkz.

- [Veri kümesi araçları](../data-tools/dataset-tools-in-visual-studio.md)