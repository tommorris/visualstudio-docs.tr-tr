---
title: Hiyerarşik güncelleştirme
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- saving data, changed data
- data [Visual Basic], hierarchical update
- saving updated data
- datasets [Visual Basic], hierarchical update
- hierarchical update
- saving data, hierarchical update
- modified data saving
- updated data saving
- related tables, saving
ms.assetid: 68bae3f6-ec9b-45ee-a33a-69395029f54c
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 31bee5d824b612ddaeb264fe2f944746cdda68fa
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="hierarchical-update"></a>Hiyerarşik güncelleştirme
*Hiyerarşik güncelleştirme* bilgi tutarlılığı kuralları korurken (kümesindeki iki veya daha fazla ilişkili tabloları ile) güncelleştirilmiş verileri bir veritabanına geri kaydetme işlemi başvuruyor. *Başvuru bütünlüğü* bir veritabanında ve ekleme, güncelleştirme ve ilgili kayıtları silme davranışını denetleyen kısıtlamalar tarafından sağlanan tutarlık kuralları başvuruyor. Örneğin, o müşteri için siparişleri oluşturulmasına izin vermeden önce bir müşteri kaydı oluşturulmasını zorlar başvuru bütünlüğü olur.  Veri kümelerindeki ilişkiler hakkında daha fazla bilgi için bkz: [kümelerindeki ilişkiler](../data-tools/relationships-in-datasets.md)

 Hiyerarşik güncelleştirme özelliğini kullanan bir `TableAdapterManager` yönetmek için `TableAdapter`türü belirtilmiş veri kümesi s. `TableAdapterManager` Bileşeni bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]-sınıfı, bu nedenle oluşturulan parçası [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Bir tablo veri kaynakları penceresinden bir Windows Form veya WPF sayfasına sürüklediğinizde, Visual Studio TableAdapterManager türünde bir değişken form veya sayfasına ekler ve Bileşen tasarımcısında bölümüne bakın. Hakkında ayrıntılı bilgi için `TableAdapterManager` sınıfı, TableAdapterManager başvuru bölümüne bakın [TableAdapters](../data-tools/create-and-configure-tableadapters.md).

 Varsayılan olarak, bir veri kümesi ilişkili tabloları "ilişkileri yalnızca" yabancı anahtar kısıtlamaları zorunlu olmayan başka bir deyişle, değerlendirir. Veri kümesi Tasarımcısı kullanarak tasarım zamanında bu ayarı değiştirebilirsiniz. Ortaya çıkarmak için iki tablo arasında ilişki satırı seçin **ilişkisi** iletişim kutusu. Burada yaptığınız değişiklikler TableAdapterManager ne zaman nasıl davranacağını belirleyen göndermeden değişiklikleri ilgili tablolarda veritabanına geri.

## <a name="enable-hierarchical-update-in-a-dataset"></a>Bir veri kümesinde hiyerarşik güncelleştirmeyi etkinleştirme
 Varsayılan olarak, eklenen veya bir proje ile oluşturulan tüm yeni veri kümeleri için hiyerarşik güncelleştirme etkindir. Ayarlayarak hiyerarşik güncelleştirme açma veya kapatma **hiyerarşik güncelleştirme** özelliği için kümesindeki türü belirtilmiş veri kümesinin **True** veya **False**:

 ![Hiyerarşik güncelleştirme ayarını](../data-tools/media/hierarchical-update-setting.png "hiyerarşik güncelleştirme ayarı")

## <a name="create-a-new-relation-between-tables"></a>Yeni tablolar arasında ilişki oluşturma
 İki tablo arasında yeni bir ilişki oluşturmak için veri kümesi Tasarımcısı'nda her tablonun başlık çubuğu seçin, sonra sağ tıklatın ve seçin **ilişki ekleyin**.

 ![Hiyerarşik güncelleştirme ekleme ilişkisi menüsü](../data-tools/media/hierarchical-update-add-relation-menu.png "hiyerarşik güncelleştirme ilişkisi menüsü ekleme")

## <a name="understand-foreign-key-constraints-cascading-updates-and-deletes"></a>Yabancı anahtar kısıtlamaları, geçişli güncelleştirme ve silme anlama
 Nasıl yabancı anahtar kısıtlamaları anlamak önemlidir ve davranışı veritabanındaki basamaklı üretilen veri kümesi kodda oluşturulur.

 Varsayılan olarak, bir veri kümesinde veri tabloları ilişkileri ile oluşturulur (<xref:System.Data.DataRelation>) veritabanında ilişkileri eşleşmesi. Ancak, veri kümesi ilişkisinde bir yabancı anahtar kısıtlaması oluşturulmaz. <xref:System.Data.DataRelation> Olarak yapılandırılan **yalnızca ilişkisi** olmadan <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> veya <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> etkin.

 Varsayılan olarak, geçişli güncelleştirmeleri ve art arda silme veritabanı ilişkisi basamaklı güncelleştirmeleriyle ayarlanır ve/veya siler basamaklı açık olsa bile devre dışı bırakılmıştır. Örneğin, yeni bir müşteri ve yeni bir sıra oluşturma ve veri kaydetmeye çalışırken bir çakışma veritabanında tanımlı yabancı anahtar kısıtlamaları ile neden olabilir. Daha fazla bilgi için bkz: [bir veri kümesini doldururken kısıtlamaları kapatma kapatma](turn-off-constraints-while-filling-a-dataset.md).

## <a name="set-the-order-to-perform-updates"></a>Güncelleştirmeleri gerçekleştirmek için sırasını ayarlama
 Güncelleştirmeleri gerçekleştirmek için sırasını ayarlama tek tek sırasını ekler, güncelleştirmeleri ve, siler kümeleri değiştirilmiş tüm verileri bir veri kümesinin tüm tablolarda kaydetmek için gereklidir. Hiyerarşik güncelleştirme etkinleştirildiğinde, eklemeleri ilk olarak, gerçekleştirilen sonra güncelleştirir ve sonra siler. `TableAdapterManager` Sağlayan bir `UpdateOrder` özelliği ilk olarak, güncelleştirmeleri gerçekleştirmek için kümesi sonra ekler ve siler olabilir.

> [!NOTE]
>  Güncelleştirme sırasını tüm dahil olduğunu anlamak önemlidir. Güncelleştirmeleri gerçekleştirildiğinde, diğer bir deyişle, ekleme ve silme kümesindeki tüm tablolar için gerçekleştirilir.

 Ayarlamak için `UpdateOrder` öğelerinden Sürüklemeyi sonra özellik [veri kaynakları penceresi](add-new-data-sources.md) bir forma seçin `TableAdapterManager` bileşen olarak ayarlayın ve ardından içinde `UpdateOrder` özelliğinde **özellikleri** penceresi.

## <a name="create-a-backup-copy-of-a-dataset-before-performing-a-hierarchical-update"></a>Hiyerarşik güncelleştirme gerçekleştirmeden önce bir veri kümesi yedek bir kopyasını oluşturun
 Veri kaydettiğinizde (çağırarak `TableAdapterManager.UpdateAll()` yöntemi), `TableAdapterManager` tek bir işlemde her tablo için verileri güncelleştirmek çalışır. Herhangi bir kısmını herhangi bir tablo güncelleştirmesi başarısız olursa, tüm işlem geri alındı. Çoğu durumda, uygulamanızın özgün durumuna geri döndürür.

 Ancak, bazen dataset yedek kopyadan geri yüklemek isteyebilirsiniz. Bunun bir örneği otomatik artım değerleri kullanılırken oluşabilir. Örneğin, kaydetme, işlem başarılı değil, otomatik artım değerleri kümesinde sıfırlanır ve otomatik artırma değerleri oluşturmak üzere veri kümesi devam eder. Bu, bir boşluk numaralandırmayı uygulamanızda kabul edilebilir olmayabilecek bırakır. Durumlarda bu bir sorun olduğu `TableAdapterManager` sağlayan bir `BackupDataSetBeforeUpdate` işlem başarısız olursa, bir yedek kopya ile mevcut veri kümesini değiştirir özelliği.

> [!NOTE]
>  Yalnızca sırasında bellekte yedek kopyasıdır `TableAdapterManager.UpdateAll` yöntemi çalışır. Bu nedenle, programlı erişimi yoktur yedekleme bu veri kümesi için özgün veri kümesini değiştirir veya kapsamının dışına gider olmadığından hemen `TableAdapterManager.UpdateAll` yöntemi tamamlandıktan çalışıyor.

## <a name="modify-the-generated-save-code-to-perform-the-hierarchical-update"></a>Hiyerarşik güncelleştirme gerçekleştirmek için kod oluşturulan değiştirme
 Değişiklikleri kümesindeki ilgili verileri tablolardan veritabanına çağırarak kaydetmek `TableAdapterManager.UpdateAll` yöntemi ve ilişkili tabloları içeren veri kümesi adına geçirme. Örneğin, çalıştırın `TableAdapterManager.UpdateAll(NorthwindDataset)` arka uç veritabanı NorthwindDataset tüm tablolardan güncelleştirmeleri göndermek için yöntem.

 Öğelerden bıraktıktan sonra **veri kaynakları** penceresinde kodu otomatik olarak eklenir `Form_Load` her tabloyu doldurmak için olay ( `TableAdapter.Fill` yöntemleri). Kodu da eklenir **kaydetmek** düğmesini olayı <xref:System.Windows.Forms.BindingNavigator> veri kümesinden veritabanına kaydetmek için ( `TableAdapterManager.UpdateAll` yöntemi).

 Oluşturulan kod kaydetmek de çağırır kod satırını içeren `CustomersBindingSource.EndEdit` yöntemi. Daha belirgin olarak çağırır <xref:System.Windows.Forms.BindingSource.EndEdit%2A> yöntemi ilk <xref:System.Windows.Forms.BindingSource>forma eklenir. Diğer bir deyişle, bu kod yalnızca gelen sürüklenen ilk tablo için oluşturulan **veri kaynakları** forma penceresi. <xref:System.Windows.Forms.BindingSource.EndEdit%2A> Çağrısı şu anda düzenlenmekte olan tüm verilere bağlı denetimler işleminde değişiklikleri kaydeder. Odak ve bu nedenle, bir veri bağlama denetimi hala varsa tıklatın **kaydetmek** denetim kaydedilir, gerçek kaydetme önce bekleyen tüm düzenlemeleri düğmesine ( `TableAdapterManager.UpdateAll` yöntemi).

> [!NOTE]
>  Veri kümesi Tasarımcısı yalnızca ekler `BindingSource.EndEdit` forma bırakılan ilk tablo için kod. Bu nedenle, bir çağırmak için kod satırı eklemeniz gerekir `BindingSource.EndEdit` yöntemi form üzerinde ilgili her tablo için. Bu kılavuz için bu bir çağrı ekleyin zorunda anlamına gelir `OrdersBindingSource.EndEdit` yöntemi.

#### <a name="to-update-the-code-to-commit-changes-to-the-related-tables-before-saving"></a>Değişiklikleri kaydetmeden önce ilişkili tabloları yürütmek için kodu güncelleştirmek için

1.  Çift **kaydetmek** düğmesini <xref:System.Windows.Forms.BindingNavigator> açmak için **Form1** Kod Düzenleyicisi'nde.

2.  Çağrılacak kod satırını ekleyin `OrdersBindingSource.EndEdit` yöntemi çağırır satırdan `CustomersBindingSource.EndEdit` yöntemi. Kodda **kaydetmek** düğmesini tıklatın olay aşağıdaki benzer:

     [!code-vb[VSProDataOrcasHierarchicalUpdate#1](../data-tools/codesnippet/VisualBasic/hierarchical-update_1.vb)]
     [!code-csharp[VSProDataOrcasHierarchicalUpdate#1](../data-tools/codesnippet/CSharp/hierarchical-update_1.cs)]

Verileri bir veritabanına kaydetme önce ilgili alt tabloda değişiklikleri işleme ek olarak, bir veri kümesine yeni alt kayıtlar eklemeden önce yeni oluşturulan yürütme üst kayıtlar için de sahip olabilir. Yeni alt kayıt kümesine eklenecek (siparişleri) yabancı anahtar kısıtlamaları etkinleştirmeden önce başka bir deyişle, yeni üst kaydı (müşteri) eklemek kümesine olabilir. Bunu başarmak için alt kullanabilirsiniz `BindingSource.AddingNew` olay.

> [!NOTE]
> Yeni üst kayıtları tamamlamaya yüklü olup olmadığını veri kaynağınıza bağlamak için kullanılan denetimin türüne bağlıdır. Bu kılavuzda, üst tablo bağlamak için tek denetimleri kullanın. Bu, yürütme yeni üst kaydı için ek kod gerektirir. Üst kayıtlar bunun yerine bir karmaşık bağlama denetiminde görüntülenen her hoşlanıyorsanız <xref:System.Windows.Forms.DataGridView>, bu ek <xref:System.Windows.Forms.BindingSource.EndEdit%2A> üst kaydı gerekli olmaz için çağırın. Yeni kayıtları teslim etme denetimi temel alınan veri bağlama işlevselliğini işleme olmasıdır.

#### <a name="to-add-code-to-commit-parent-records-in-the-dataset-before-adding-new-child-records"></a>Yeni alt kayıtlar eklemeden önce üst kayıtlar kümesindeki yürütmek üzere kod eklemek için

1.  İçin bir olay işleyicisi oluşturun `OrdersBindingSource.AddingNew` olay.

    -   Açık **Form1** Tasarım görünümünde seçin **OrdersBindingSource** bileşen tepsisinde seçin **olayları** içinde **özellikleri** penceresinde ve ardından **AddingNew** olay.

2.  Çağıran olay işleyicisi için kod satırını ekleyin `CustomersBindingSource.EndEdit` yöntemi. Kodda `OrdersBindingSource_AddingNew` olay işleyicisi aşağıdaki benzer:

     [!code-vb[VSProDataOrcasHierarchicalUpdate#2](../data-tools/codesnippet/VisualBasic/hierarchical-update_2.vb)]
     [!code-csharp[VSProDataOrcasHierarchicalUpdate#2](../data-tools/codesnippet/CSharp/hierarchical-update_2.cs)]

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

## <a name="see-also"></a>Ayrıca bkz.

- [Verileri yeniden veritabanına kaydetme](../data-tools/save-data-back-to-the-database.md)