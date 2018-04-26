---
title: Visual Studio'da nesne bağlama
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], object binding
- data [Visual Studio], binding to objects
- object binding
- binding, to objects
ms.assetid: ed743ce6-73af-45e5-a8ff-045eddaccc86
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 1713221c56fe29357e708e3790aa292d456c4519
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="bind-objects-in-visual-studio"></a>Visual Studio'da nesne bağlama
Visual Studio, uygulamanızdaki veri kaynağı olarak özel nesneler ile çalışmak için tasarım zamanı araçlar sağlar. UI denetimlerine bağlamanıza bir nesne bir veritabanındaki verileri depolamak istediğiniz zaman, önerilen yaklaşım Entity Framework sınıfları ve sınıf oluşturmak için kullanmaktır. Entity Framework otomatik-DbSet nesnesinde AcceptChanges çağırdığınızda yerel nesneleri değişiklikleri otomatik olarak veritabanına kalıcı yapıldığını Bunun anlamı tüm ortak değişiklik izleme kodunu üretir. Daha fazla bilgi için bkz: [Entity Framework belgelerine](https://ef.readthedocs.org/en/latest/).

> [!TIP]
>  Uygulamanızın veri kümelerinin zaten bağlıysa bu makalede nesne bağlama yaklaşımları yalnızca dikkate alınmalıdır. Bu yaklaşım, veri kümeleriyle bilginiz ve, işleme veri tablo ve çok karmaşık ya da çok büyük ise kullanılabilir. DataReader kullanarak ve el ile bağlama, olmadan UI güncelleştirme nesnelerini doğrudan veri yükleme ile ilgili bile daha basit bir örnek için bkz: [ADO.NET kullanarak basit veri uygulaması oluşturma](../data-tools/create-a-simple-data-application-by-using-adonet.md).

## <a name="object-requirements"></a>Nesne gereksinimleri
 Visual Studio Araçları tasarım verilerle çalışmak özel nesneler için tek gereksinim nesnenin en az bir ortak özellik gereğidir.

 Genellikle, özel nesneleri herhangi bir belirli arabirimleri, Oluşturucular veya bir uygulama için bir veri kaynağı olarak görev yapması için öznitelikler gerektirmez. Ancak, nesneden sürükleyin istiyorsanız **veri kaynakları** veri bağlama denetimi oluşturmak için tasarım yüzeyi penceresine ve nesne uyguluyorsa <xref:System.ComponentModel.ITypedList> veya <xref:System.ComponentModel.IListSource> arabirimi, varsayılan bir nesne olmalıdır Oluşturucu. Aksi takdirde, Visual Studio veri kaynağı nesnesi başlatılamıyor ve öğeyi tasarım yüzeyine sürükleyin olduğunda bir hata görüntüler.

## <a name="examples-of-using-custom-objects-as-data-sources"></a>Veri kaynakları olarak özel nesneleri kullanma örnekleri
 Nesneler ile bir veri kaynağı olarak çalışırken, uygulama mantığını uygulamak için sayısız yollar olsa da, SQL için var. TableAdapter Visual Studio tarafından oluşturulan nesneleri kullanılarak Basitleştirilmiş birkaç standart işlemleri veritabanlarıdır. Bu sayfa bu standart işlemleri uygulamak üzere açıklanmaktadır TableAdapters.It kullanarak tasarlanmamıştır bir kılavuz olarak, özel nesneler oluşturmak için. Örneğin, genellikle aşağıdaki standart belirli uygulamadan bağımsız olarak, nesne veya uygulamanın mantığı işlemleri yapar:

-   Veri nesneleri (genellikle bir veritabanından) içine yükleniyor.

-   Nesnelerin türü belirtilmiş bir koleksiyon oluşturuluyor.

-   Nesne eklemeyi ve koleksiyondan nesneleri kaldırılıyor.

-   Bir form üzerinde kullanıcılara nesne verilerini görüntüleme.

-   Değiştirme/nesnedeki verileri düzenleme.

-   Verileri nesneden veritabanına kaydetme.

### <a name="load-data-into-objects"></a>Nesnelere veri yükleme
 Bu örnekte, TableAdapters kullanarak nesnelerinizi veri yükleyin. Varsayılan olarak, bir veritabanından veri getirebilir ve veri tabloları doldurmak yöntemleri iki tür TableAdapters oluşturulur.

-   `TableAdapter.Fill` Yöntemi döndürülen veriler ile varolan bir veri tablosu doldurur.

-   `TableAdapter.GetData` Yöntemi verilerle doldurmuş yeni bir veri tablosu döndürür.

 En kolay yolu, özel nesneleri verilerle yük çağırmaktır `TableAdapter.GetData` yöntemi, döngü döndürülen veri tablosundaki satırları koleksiyonu aracılığıyla ve her nesnenin her satırda değerlerle doldurmak. Oluşturabileceğiniz bir `GetData` bir TableAdapter eklenen herhangi bir sorgu için girilmiş veriler tablo döndüren yöntemi.

> [!NOTE]
>  Visual Studio adları TableAdapter sorguları `Fill` ve `GetData` varsayılan olarak, ancak bu adları için herhangi bir geçerli yöntemi ad değiştirilebilir.

 Aşağıdaki örnek, bir veri tablosundaki satırları döngü ve nesneyi verilerle doldurmak gösterilmektedir:

 [!code-csharp[VbRaddataConnecting#4](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_1.cs)]
 [!code-vb[VbRaddataConnecting#4](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_1.vb)]

### <a name="create-a-typed-collection-of-objects"></a>Nesnelerin türü belirtilmiş bir koleksiyon oluşturma
 Koleksiyon sınıfları için nesneleri oluşturmak veya tarafından otomatik olarak sağlanan yazılan koleksiyonları kullanın [BindingSource bileşeni](/dotnet/framework/winforms/controls/bindingsource-component).

 Nesneler için özel toplama sınıfı oluştururken öğesinden devralmalı önerdiğimiz <xref:System.ComponentModel.BindingList%601>. Bu genel bir sınıf özelliği Windows Forms veri bağlama altyapısında bildirim göndermek olaylarını yanı sıra, koleksiyonunuzu yönetmek için işlevsellik sağlar.

 Otomatik olarak oluşturulan koleksiyonunda <xref:System.Windows.Forms.BindingSource> kullanan bir <xref:System.ComponentModel.BindingList%601> yazılı koleksiyon için. Uygulamanızı ek işlevsellik gerektirmez sonra koleksiyonunuzu içine koruyabilirsiniz <xref:System.Windows.Forms.BindingSource>. Daha fazla bilgi için bkz: <xref:System.Windows.Forms.BindingSource.List%2A> özelliği <xref:System.Windows.Forms.BindingSource> sınıfı.

> [!NOTE]
>  Koleksiyonunuz temel uygulaması tarafından sağlanmayan işlevsellik gerektiriyorsa <xref:System.ComponentModel.BindingList%601>, gerektiğinde sınıfa ekleyebilmek için özel bir koleksiyona oluşturmanız gerekir.

 Aşağıdaki kod sınıfı için kesin türü belirtilmiş bir koleksiyonunu oluşturmak nasıl gösterir `Order` nesneler:

 [!code-csharp[VbRaddataConnecting#8](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_2.cs)]
 [!code-vb[VbRaddataConnecting#8](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_2.vb)]

### <a name="add-objects-to-a-collection"></a>Bir koleksiyona Nesne Ekle
 Nesneleri çağırarak bir koleksiyona eklemek `Add` yöntemi özel koleksiyon sınıfınızın veya, <xref:System.Windows.Forms.BindingSource>.


> [!NOTE]
>  `Add` Öğesinden devralmalı zaman yöntemi özel koleksiyonunuz için otomatik olarak sağlanan <xref:System.ComponentModel.BindingList%601>.

 Aşağıdaki kod, yazılı koleksiyonunda nesneleri eklemek gösterilmiştir bir <xref:System.Windows.Forms.BindingSource>:

 [!code-csharp[VbRaddataConnecting#5](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_3.cs)]
 [!code-vb[VbRaddataConnecting#5](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_3.vb)]

 Aşağıdaki kod devraldığı belirtilmiş bir koleksiyon nesneleri eklemek nasıl gösterir <xref:System.ComponentModel.BindingList%601>:

> [!NOTE]
>  Bu örnekte `Orders` koleksiyonudur özelliği `Customer` nesnesi.

 [!code-csharp[VbRaddataConnecting#6](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_4.cs)]
 [!code-vb[VbRaddataConnecting#6](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_4.vb)]

### <a name="remove-objects-from-a-collection"></a>Nesneleri bir koleksiyondan Kaldır
 Nesneleri çağırarak koleksiyondan çıkarmak `Remove` veya `RemoveAt` yöntemi özel koleksiyon sınıfınızın veya, <xref:System.Windows.Forms.BindingSource>.

> [!NOTE]
>  `Remove` Ve `RemoveAt` yöntemleri otomatik olarak sağlanan özel koleksiyonunuz için öğesinden devralmalı zaman <xref:System.ComponentModel.BindingList%601>.

 Aşağıdaki kodu bulun ve yazılı koleksiyonunda nesneleri kaldırmak gösterilmektedir bir <xref:System.Windows.Forms.BindingSource> ile <xref:System.Windows.Forms.BindingSource.RemoveAt%2A> yöntemi:

 [!code-csharp[VbRaddataConnecting#7](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_5.cs)]
 [!code-vb[VbRaddataConnecting#7](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_5.vb)]

### <a name="display-object-data-to-users"></a>Nesne verileri için kullanıcıları görüntüle
 Veri kullanıcılarına nesneleri görüntülemek için bir nesne veri kaynağı kullanarak oluşturduğunuz **veri kaynağı yapılandırması** Sihirbazı'nı ve ardından nesnenin tamamı veya ayrı ayrı özellikler formdan sürükleyin **veri kaynakları**penceresi.

### <a name="modify-the-data-in-objects"></a>Nesne verileri değiştirme
 Verilere Windows Forms denetimlerine bağlı özel nesneleri verileri düzenlemek için yalnızca verileri bağımlı denetimi (veya nesnenin özelliklerinde doğrudan) düzenleyin. Veri bağlama mimarisi nesnedeki verileri güncelleştirir.

 Uygulamanızı değişiklikleri izleme ve özgün değerlerine arkasına önerilen değişiklikleri çalışırken gerektiriyorsa, bu işlev, nesne modelinde uygulamalıdır. Nasıl veri tabloları önerilen değişiklikleri izlemek örnekler için bkz: <xref:System.Data.DataRowState>, <xref:System.Data.DataSet.HasChanges%2A>, ve <xref:System.Data.DataTable.GetChanges%2A>.

### <a name="save-data-in-objects-back-to-the-database"></a>Veri nesneleri veritabanına kaydedin
 Veri değerleri, nesnesinden'ın TableAdapter DBDirect yöntemleri geçirerek veritabanına geri kaydedin.

 Visual Studio doğrudan veritabanına karşı yürütülen DBDirect yöntemleri oluşturur. Bu yöntemler, veri kümesi ya da DataTable nesneleri gerektirmez.

|TableAdapter DBDirect yöntemi|Açıklama|
|----------------------------------|-----------------|
|`TableAdapter.Insert`|Yöntem parametreleri olarak tek tek sütun değerlerini geçirin olanak tanıyan bir veritabanına yeni kayıtlar ekler.|
|`TableAdapter.Update`|Veritabanındaki kayıtları mevcut güncelleştirir. Update yöntemi yöntem parametreleri olarak özgün ve yeni sütun değerlerini alır. Özgün değerler özgün kayıt bulmak için kullanılır ve yeni değerler o kaydını güncelleştirmek üzere kullanılır.<br /><br /> `TableAdapter.Update` Yöntemi gerçekleştirerek bir veri kümesinde değişiklikleri veritabanına geri mutabık kılmak için kullanılan aynı zamanda bir <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, <xref:System.Data.DataRow>, veya dizi <xref:System.Data.DataRow>s yöntem parametreleri olarak.|
|`TableAdapter.Delete`|Yöntem parametreleri olarak geçirilen özgün sütun değerleri temel alarak veritabanından kayıtları varolan siler.|

 Veri nesneleri koleksiyonundan kaydetmek için (örneğin, bir sonraki için döngü kullanarak) nesneleri koleksiyonu döngü. Değerlerin her nesne için'ın TableAdapter DBDirect yöntemleri kullanarak veritabanına gönderin.

 Aşağıdaki örnekte nasıl kullanılacağını gösterir `TableAdapter.Insert` DBDirect yöntemi yeni bir müşteri doğrudan veritabanına eklemek için:

 [!code-csharp[VbRaddataSaving#23](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_6.cs)]
 [!code-vb[VbRaddataSaving#23](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_6.vb)]

## <a name="see-also"></a>Ayrıca Bkz.

- [Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md)