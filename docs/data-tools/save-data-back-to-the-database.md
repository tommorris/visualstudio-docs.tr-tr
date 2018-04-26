---
title: Veritabanına veri kaydetme
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- datasets [Visual Basic], validating data
- data validation, datasets
- data [Visual Studio], saving
- row version
- updating datasets, constraints
- datasets [Visual Basic], about datasets
- datasets [Visual Basic], merging
- updates, constraints in datasets
- saving data, about saving data
- datasets [Visual Basic], constraints
- TableAdapters
ms.assetid: afe6cb8a-dc6a-428b-b07b-903ac02c890b
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: ee004af6cb130167789cac022ae1c04beef8dbe6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="save-data-back-to-the-database"></a>Veritabanına veri kaydetme
Veri kümesi, veri bir bellek içi kopyasıdır. Bu verileri değiştirirseniz, bu değişiklikleri veritabanına kaydetmek için iyi bir uygulamadır. Bu üç yöntemden birini yapın:

-   Bir TableAdapter güncelleştirme yöntemlerden birini çağırarak

-   TableAdapter DBDirect yöntemleri birini çağırarak

-   Veri kümesi kümesindeki diğer tablolarla ilişkili tabloları içerdiğinde UpdateAll yöntemi üzerinde TableAdapterManager çağıran Visual Studio sizin için oluşturur

Veri bağlama mimarisi tüm iş verileri Windows Form veya XAML sayfası denetimlere dataset tabloları bağladığınızda, sizin için yapar.

TableAdapters ile sahibiyseniz, doğrudan aşağıdaki konulardan birine atlayabilirsiniz:

|Konu|Açıklama|
|-----------|-----------------|
|[Veritabanına yeni kayıtlar ekleme](../data-tools/insert-new-records-into-a-database.md)|Nasıl gerçekleştirileceği güncelleştirir ve TableAdapters ya da komut nesneleri kullanarak ekler|
|[TableAdapter kullanarak verileri güncelleştirme](../data-tools/update-data-by-using-a-tableadapter.md)|TableAdapters güncelleştirmeleriyle gerçekleştirme|
|[Hiyerarşik güncelleştirme](../data-tools/hierarchical-update.md)|İki veya daha fazla ilgili tablo ile bir veri kümesinden güncelleştirmeleri gerçekleştirme|
|[Bir eşzamanlılık özel durumunu işleme](../data-tools/handle-a-concurrency-exception.md)|İki kullanıcı aynı anda aynı verileri bir veritabanındaki değiştirmeye kalkıştığında özel durumları işleme|
|[Nasıl yapılır: bir işlemi kullanarak veri kaydetme](../data-tools/save-data-by-using-a-transaction.md)|System.Transactions ad alanı ve TransactionScope nesnesini kullanarak bir işlemde veri kaydetme|
|[İzlenecek yol: Bir işlemde veri kaydetme](../data-tools/save-data-in-a-transaction.md)|Bir işlemin içindeki veritabanına veri kaydetme göstermek için bir Windows Forms uygulaması oluşturur gözden geçirme|
|[Bir veritabanına (birden çok tablo) veri kaydetme](../data-tools/save-data-to-a-database-multiple-tables.md)|Kayıtları düzenleme ve veritabanına birden çok tablolardaki değişiklikleri kaydetme|
|[Verileri bir nesneden veritabanına kaydetme](../data-tools/save-data-from-an-object-to-a-database.md)|Bir veritabanı için bir veri kümesinde bir TableAdapter DbDirect yöntemi kullanarak değil bir nesne veri geçirmek nasıl|
|[TableAdapter DBDirect metotlarıyla veri kaydetme](../data-tools/save-data-with-the-tableadapter-dbdirect-methods.md)|TableAdapter doğrudan veritabanına SQL sorguları göndermek için nasıl kullanılacağını|
|[Bir veri kümesini XML olarak kaydetme](../data-tools/save-a-dataset-as-xml.md)|Bir veri kümesi için bir XML belgesi kaydetme|

## <a name="two-stage-updates"></a>İki aşamalı güncelleştirmeleri
 Bir veri kaynağını güncelleme iki adımlı bir işlemdir. Yeni kayıtlar, kayıtlar ya da silinmiş kayıtlar ile dataset güncelleştirmek için ilk adımdır bakın. Uygulamanız, bu değişiklikleri hiç veri kaynağına geri gönderir. ardından, güncelleştirme ile tamamlanmış demektir.

 Değişiklikler veritabanına geri göndermek istediğinizde, ikinci bir adım gereklidir. Verilere bağlı denetimler kullanmıyorsanız, el ile veri kümesini doldurmak için kullanılan güncelleştirme yöntemini aynı TableAdapter (veya veri bağdaştırıcısı) çağırın sahip. Ancak, aynı zamanda farklı bağdaştırıcıları bir veri kaynağından verileri taşımak için veya birden fazla veri kaynağını güncelleştirmek için kullanabilirsiniz. Veri bağlama kullanmadığınız ve ilişkili tablolar için değişiklikler kaydediliyor, el ile bir değişkeni otomatik olarak oluşturulan TableAdapterManager sınıfının örneği ve ardından UdpateAll yöntemini çağırın gerekir.

 ![Visual Basic veri kümesi güncelleştirmeleri](../data-tools/media/vbdatasetupdates.gif "vbDatasetUpdates") iki aşamalı işlemi ve başarılı bir güncelleştirme DataRowVersion rol güncelleştirme

 Bir veri kümesi satır koleksiyonları içeren tablolar koleksiyonları içerir. Veri kaynağındaki daha sonra güncelleştirme yapmak istiyorsanız, DataTable.DataRowCollection özelliği eklerken veya satır kaldırmayı yöntemlerini kullanmanız gerekir. Bu yöntem, veri kaynağını güncelleştirmek için gerekli olan değişiklik izleme gerçekleştirin. Satır özelliği RemoveAt koleksiyonu çağırırsanız, silme veritabanına geri bildirilmesi olmaz.

## <a name="merge-datasets"></a>Veri kümeleri birleştirme
 Bir veri kümesi tarafından içeriğini güncelleştirebilirsiniz *birleştirme* başka bir veri kümesi ile. Bu içeriği kopyalama içerir bir *kaynak* arama dataset kümesine (olarak adlandırılan *hedef* veri kümesi). Veri kümeleri birleştirdiğinizde, kaynak veri kümesinde yeni kayıtlar hedef veri kümesine eklenir. Ayrıca, kaynak veri kümesinde ek sütunlar hedef veri kümesine eklenir. Veri kümeleri birleştirme yerel bir veri kümeniz ve ikinci bir veri kümesinin başka bir uygulamadan elde yararlıdır. Ayrıca bir XML web hizmeti gibi bir bileşenin ikinci bir veri kümesi aldığınızda veya birden çok veri kümelerinden veri tümleştirme gerektiğinde yararlı olacaktır.

 Veri kümeleri birleştirilirken Boolean bir bağımsız değişken geçirebilirsiniz (`preserveChanges`), söyler <xref:System.Data.DataSet.Merge%2A> yöntemi hedef veri kümesi mevcut değişikliklerini bekletileceğini. Veri kümeleri kayıtları birden fazla sürümünü korumak için kayıtların birden fazla sürümünü birleştirilmiş olduğunu göz önünde bulundurmanız önemlidir. Aşağıdaki tabloda, iki veri kümesi bir kayıtta nasıl birleştirileceğini gösterir:

|DataRowVersion|Hedef veri kümesi|Kaynak veri kümesi|
|--------------------|--------------------|--------------------|
|Özgün|Ahmet Wilson|Ahmet C. Wilson|
|Geçerli|Jim Wilson|Ahmet C. Wilson|

 Çağırma <xref:System.Data.DataSet.Merge%2A> yöntemi olan önceki tabloda `preserveChanges=false targetDataset.Merge(sourceDataset)` aşağıdaki sonuçları:

|DataRowVersion|Hedef veri kümesi|Kaynak veri kümesi|
|--------------------|--------------------|--------------------|
|Özgün|Ahmet C. Wilson|Ahmet C. Wilson|
|Geçerli|Ahmet C. Wilson|Ahmet C. Wilson|

 Çağırma <xref:System.Data.DataSet.Merge%2A> yöntemiyle `preserveChanges = true targetDataset.Merge(sourceDataset, true)` aşağıdaki sonuçları:

|DataRowVersion|Hedef veri kümesi|Kaynak veri kümesi|
|--------------------|--------------------|--------------------|
|Özgün|Ahmet C. Wilson|Ahmet C. Wilson|
|Geçerli|Jim Wilson|Ahmet C. Wilson|

> [!CAUTION]
>  İçinde `preserveChanges = true` senaryosu, varsa <xref:System.Data.DataSet.RejectChanges%2A> yöntemi hedef veri kümesi bir kayıtta çağrılır ve özgün veriler için döner *kaynak* veri kümesi. Bu, özgün veri kaynağına hedef veri kümesi ile güncelleştirmeye çalıştığınızda, onu güncelleştirmek için özgün satır bulmak kuramamış olabilir, anlamına gelir. Veri kaynağından güncelleştirilmiş kayıtları başka bir veri kümesi doldurma ve bir eşzamanlılık ihlali önlemek için birleştirme işlemi, bir eşzamanlılık ihlali engelleyebilirsiniz. (Bir eşzamanlılık ihlali dataset doldurulmuş sonra başka bir kullanıcı kaydı veri kaynağındaki değiştirdiğinde oluşur.)

## <a name="update-constraints"></a>Güncelleştirme kısıtlamaları
 Varolan bir veri satırı değişiklik yapmak için ekleyin veya bireysel sütunlardaki verileri güncelleştirin. Veri kümesi (örneğin, yabancı anahtarların veya null kısıtlamaları) kısıtlamalarını içeriyorsa, bu güncelleştirme kayıt geçici olarak bir hata durumunda olabilir mümkündür. Diğer bir deyişle, bir sütunu güncelleştirme işlemini tamamladıktan sonra ancak bir ulaşmadan önce bu bir hata durumunda olabilir.

 Erken sabiti ihlallerini önlemek için güncelleştirme kısıtlamaları geçici olarak askıya alabilirsiniz. Bu iki amaca hizmet eder:

-   Hata bir sütunu güncelleştirme bitirdikten sonra ancak başka bir güncelleştirme başlamamış sonra oluşturulan engeller.

-   Bazı güncelleştirme engelleyen engeller olayları (genellikle doğrulama için kullanılan olayları) oluşur.

> [!NOTE]
>  Windows Forms datagrid içinde yerleşik veri bağlama mimarisi odağı dışında bir satır taşır ve açıkça çağırın gerekmez kadar denetleme kısıtlaması askıya <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, veya <xref:System.Data.DataRow.CancelEdit%2A> yöntemleri.

 Kısıtlamaları olan otomatik olarak devre dışı <xref:System.Data.DataSet.Merge%2A> yöntemi, bir veri kümesine çağrılır. Birleştirme tamamlandığında etkinleştirilemez, veri kümesi üzerinde kısıtlamalar varsa bir <xref:System.Data.ConstraintException> oluşturulur. Bu durumda, <xref:System.Data.DataSet.EnforceConstraints%2A> özelliği ayarlanmış `false,` ve tüm bir kısıtlama ihlali sıfırlamadan önce çözümlenmelidir <xref:System.Data.DataSet.EnforceConstraints%2A> özelliğine `true`.

 Güncelleştirme tamamlandıktan sonra kısıtlama denetimi, hangi da güncelleştirme olaylarını yeniden etkinleştirir ve bunları başlatır yeniden etkinleştirebilirsiniz.

 Olayları askıya alma hakkında daha fazla bilgi için bkz: [bir veri kümesini doldururken kısıtlamaları kapatma kapatma](../data-tools/turn-off-constraints-while-filling-a-dataset.md).

## <a name="dataset-update-errors"></a>Veri kümesi güncelleştirme hataları
 Bir kayıt kümesindeki güncelleştirdiğinizde, hata olasılığını yoktur. Örneğin, bir sütuna, yanlış türde veri veya çok uzun veri ya da başka bir bütünlük sorun olan verilerin yanlışlıkla yazabilirsiniz. Veya özel hatalar herhangi bir güncelleştirme olay aşamasında yükseltebilirsiniz uygulamaya özgü doğrulama denetimlerini olabilir. Daha fazla bilgi için bkz: [veri kümelerindeki verileri doğrulama](../data-tools/validate-data-in-datasets.md).

## <a name="maintaining-information-about-changes"></a>Değişiklikler hakkında bilgi koruma
 Bir veri kümesinde değişiklikleri hakkında bilgi iki yolla saklanır: Bunlar değişmiş belirtmek satırları işaretlemesini tarafından (<xref:System.Data.DataRow.RowState%2A>) ve bir kayıt birden çok kopyasını keserek (<xref:System.Data.DataRowVersion>). Bu bilgileri kullanarak işlemleri kümesinde nelerin değiştiğini belirleyebilir ve uygun güncelleştirmeleri veri kaynağına gönderebilirsiniz.

### <a name="rowstate-property"></a>RowState özelliği
 <xref:System.Data.DataRow.RowState%2A> Özelliği bir <xref:System.Data.DataRow> nesne belirli bir satır veri durumu hakkında bilgi sağlayan bir değerdir.

 Aşağıdaki tabloda olası değerlerini ayrıntıları <xref:System.Data.DataRowState> numaralandırma:

|DataRowState değeri|Açıklama|
|------------------------|-----------------|
|<xref:System.Data.DataRowState.Added>|Satır için bir öğe olarak eklenen bir <xref:System.Data.DataRowCollection>. (Bunu mevcut olmadığından bu durumdaki bir satır karşılık gelen bir özgün sürümü yok olduğunda son <xref:System.Data.DataRow.AcceptChanges%2A> yöntemi çağrıldı).|
|<xref:System.Data.DataRowState.Deleted>|Satır kullanarak silindi <xref:System.Data.DataRow.Delete%2A> , bir <xref:System.Data.DataRow> nesnesi.|
|<xref:System.Data.DataRowState.Detached>|Satır oluşturuldu, ancak herhangi bir parçası değil <xref:System.Data.DataRowCollection>. A <xref:System.Data.DataRow> nesne oluşturulduktan sonra önce onu bir koleksiyona eklenmiş durumda hemen ve koleksiyondan kaldırıldıktan sonra bu durumda olduğundan.|
|<xref:System.Data.DataRowState.Modified>|Bir sütun değeri satırda başka bir yolla değişti.|
|<xref:System.Data.DataRowState.Unchanged>|Satır bu yana değişmemiştir <xref:System.Data.DataRow.AcceptChanges%2A> son çağrıldı.|

### <a name="datarowversion-enumeration"></a>DataRowVersion numaralandırması
Veri kümeleri kayıtları birden fazla sürümünü koruyun. <xref:System.Data.DataRowVersion> Bulunan değeri alınırken zaman alanlar kullanılabilir bir <xref:System.Data.DataRow> kullanarak <xref:System.Data.DataRow.Item%2A> özelliği veya <xref:System.Data.DataRow.GetChildRows%2A> yöntemi <xref:System.Data.DataRow> nesnesi.

Aşağıdaki tabloda olası değerlerini ayrıntıları <xref:System.Data.DataRowVersion> numaralandırma:

|DataRowVersion değeri|Açıklama|
|--------------------------|-----------------|
|<xref:System.Data.DataRowVersion.Current>|Bir kayıt geçerli sürümünü kaydında son yedeklemeden bu yana gerçekleştirilen tüm değişiklikler içeren <xref:System.Data.DataRow.AcceptChanges%2A> çağrıldı. Satır sildiyseniz geçerli sürümü yoktur.|
|<xref:System.Data.DataRowVersion.Default>|Veri kümesi şema veya veri kaynağı tarafından tanımlandığı şekilde bir kayıt, varsayılan değeri.|
|<xref:System.Data.DataRowVersion.Original>|Son zaman değişiklikleri kümesinde kaydedilmiş haliyle bir kaydın özgün sürümünün kaydı kopyasıdır. Pratikteki, bu genellikle bir kayıt okundu olarak bir veri kaynağından sürümüdür.|
|<xref:System.Data.DataRowVersion.Proposed>|Bir güncelleştirme ortasında durumdayken kullanılabilir olan bir kaydın önerilen sürümünün — diğer bir deyişle, arasındaki süre aradığınız <xref:System.Data.DataRow.BeginEdit%2A> yöntemi ve <xref:System.Data.DataRow.EndEdit%2A> yöntemi. Genellikle bir olay işleyicisi kaydında önerilen sürümünü erişim gibi <xref:System.Data.DataTable.RowChanging>. Çağırma <xref:System.Data.DataRow.CancelEdit%2A> yöntemi değişiklikleri geri alır ve veri satırı önerilen sürümünü siler.|

 Bir veri kaynağı için güncelleştirme bilgileri iletilirken özgün ve geçerli sürümleri yararlı olur. Veri kaynağına gönderilen bir güncelleştirme olduğunda, genellikle, yeni veritabanı için bir kayıt geçerli sürümde bilgilerdir. Özgün sürüm bilgilerini güncelleştirmek için kaydı bulmak için kullanılır.

 Örneğin, burada bir kaydın birincil anahtarı değiştirilmiş bir durumda, değişiklikleri güncelleştirmek için veri kaynağında doğru kayıt bulmak için bir yol gerekir. Hiçbir özgün sürüm varsa, daha sonra kayıt büyük olasılıkla yalnızca bir ek istenmeyen kaydındaki ancak yanlış ve güncel bir kayıtta kaynaklanan veri kaynağına eklenmesi. İki sürümü de tutarlılık denetimi kullanılır. Bir kayıt kümesine yüklendiğinden bu yana kaydı değişip değişmediğini belirlemek için veri kaynağındaki karşı özgün sürümü karşılaştırabilirsiniz.

 Önerilen sürüm, aslında değişiklikleri kümesine gerçekleştirmeden önce doğrulama gerçekleştirmek gereken yararlıdır.

 Kayıtları değiştirilmiş olsa bile yok her zaman özgün ya da geçerli satır sürümleri. Yeni bir satır tabloya eklediğinizde, özgün sürümü, geçerli bir sürüm yoktur. Benzer şekilde, bir satır tablo çağırarak silerseniz `Delete` yöntemi, özgün sürümü, ancak hiçbir geçerli sürümü yok.

 Veri satırın sorgulayarak bir kayıt belirli bir sürümü olup olmadığını sınayabilirsiniz <xref:System.Data.DataRow.HasVersion%2A> yöntemi. Geçirerek bir kayıt her iki sürümü de erişebilir bir <xref:System.Data.DataRowVersion> bir sütunun değerini istediğinde isteğe bağlı bağımsız değişken olarak numaralandırma değeri.

## <a name="getting-changed-records"></a>Kayıtlar alma
 Her bir veri kümesi kaydında yükseltmemeye yaygın bir uygulamadır. Örneğin, bir kullanıcı bir Windows Forms ile çalışmıyor olabilir <xref:System.Windows.Forms.DataGridView> çok sayıda kayıt görüntüleyen denetim. Ancak, kullanıcı yalnızca birkaç kayıtlarını güncelleştirmek, silmek ve yeni bir tane ekleyin. Veri kümeleri ve veri tabloları bir yöntem sunar (`GetChanges`) değiştirilmiş satırları döndürmek için.

 Kullanarak değiştirilen kayıt kümelerine oluşturabilirsiniz `GetChanges` veri tablosunun yöntemi (<xref:System.Data.DataTable.GetChanges%2A>) veya veri kümesinin (<xref:System.Data.DataSet.GetChanges%2A>) kendisi. Veri tablosu için yöntemini çağırırsanız, yalnızca değiştirilen kayıtları tabloyla kopyasını döndürür. Veri kümesine yöntemini çağırırsanız, benzer şekilde, yalnızca değiştirilen kayıtları sahip yeni bir veri kümesi içinde alırsınız.

 `GetChanges` tek başına, tüm kayıtlar döndürür. Buna karşılık, geçirerek istenen <xref:System.Data.DataRowState> bir parametre olarak `GetChanges` yöntemi, hangi alt istediğiniz değiştirilen kayıt kümesinin belirtebilirsiniz: yeni kayıtlar, silinmek üzere işaretlenmiş kayıtları ayrılmış kayıtları eklenemez veya kayıtları değiştirilemez.

 Değiştirilen kayıtların bir alt kümesini alma işleme için başka bir bileşen kayıtları göndermek istediğinizde kullanışlıdır. Tüm veri kümesinin göndermek yerine yalnızca bir bileşeni gerektiren kayıtları alarak diğer bileşeniyle iletişim ek yükü azaltabilir.

## <a name="committing-changes-in-the-dataset"></a>Veri kümesinde değişiklikleri işleme
 Veri kümesinde yapılan değişiklikler gibi <xref:System.Data.DataRow.RowState%2A> değiştirilen satırları özelliği ayarlanmış. Kayıtları özgün ve geçerli sürümleri kurulan, saklanır ve tarafından sunulan <xref:System.Data.DataRowView.RowVersion%2A> özelliği. Bu değiştirilen satırları özelliklerinde depolanan meta veriler, veri kaynağına doğru güncelleştirmeleri göndermek için gereklidir.

 Veri kaynağı geçerli durumu değişiklikleri yansıtmak, artık bu bilgileri korumak için gerekir. Genellikle, veri kümesi ve kaynağı eşit olduğunda iki kez vardır:

-   Hemen sonra kaynak sunucudan verileri okurken gibi kümesine bilgi yüklemiş olduğunuz.

-   Veri kaynağına veri kümesinden değişiklikleri gönderdikten sonra (ancak önce değil değişiklikleri veritabanına göndermek için gerekli olan değişiklik bilgileri kaybeder nedeniyle).

Çağırarak veri kümesine ilişkin bekleyen değişiklikleri tamamlayabilir <xref:System.Data.DataSet.AcceptChanges%2A> yöntemi. Genellikle, <xref:System.Data.DataSet.AcceptChanges%2A> şu saatlerde adı verilir:

-   Sonra veri kümesi yükleyin. TableAdapter's çağırarak bir veri kümesi yük durumunda `Fill` yöntemi sonra bağdaştırıcı otomatik olarak tamamlar değişiklikleri sizin için. Bir veri kümesinin başka bir veri kümesi içine birleştirerek yüklerseniz, ancak, ardından, değişiklikleri el ile uygulamanız gerekir.

    > [!NOTE]
    >  Çağırdığınızda otomatik olarak değişiklikleri yürütmeyi gelen bağdaştırıcı engelleyebilirsiniz `Fill` ayarlayarak yöntemi `AcceptChangesDuringFill` bağdaştırıcıya özelliğinin `false`. Bu ayarlanırsa `false`, sonra <xref:System.Data.DataRow.RowState%2A> doldurma sırasında eklenen her bir satır kümesine <xref:System.Data.DataRowState.Added>.

-   XML Web hizmeti gibi başka bir işlem için veri kümesi değişiklikleri gönderdikten sonra.

    > [!CAUTION]
    >  Bu şekilde değişikliği uygulamayı herhangi bir değişiklik bilgi siler. Değil değişiklikleri kadar çalıştırdıktan sonra kümesinde hangi değişiklikler yapılmıştır öğrenmek için uygulamanızın gerektiren işlemler gerçekleştirme son.

Bu yöntem aşağıdakileri gerçekleştirir:

-   Yazar <xref:System.Data.DataRowVersion.Current> bir kayıtta sürümü kendi <xref:System.Data.DataRowVersion.Original> sürümü ve özgün sürümü üzerine yazar.

-   Herhangi bir satır kaldırır nerede <xref:System.Data.DataRow.RowState%2A> özelliği ayarlanmış <xref:System.Data.DataRowState.Deleted>.

-   Ayarlar <xref:System.Data.DataRow.RowState%2A> bir kayıt özelliği <xref:System.Data.DataRowState.Unchanged>.

<xref:System.Data.DataSet.AcceptChanges%2A> Yöntemi üç düzeyde kullanılabilir. Üzerinde çağrısı bir <xref:System.Data.DataRow> işlemeleri nesnesine yalnızca söz konusu satır için değiştirir. Üzerinde da çağırabilirsiniz bir <xref:System.Data.DataTable> tablodaki tüm satırları yürütmek için nesne. Üzerinde çağrı son olarak, <xref:System.Data.DataSet> tüm tabloların kümesinin tüm kayıtlardaki tüm bekleyen değişiklikleri yürütmek için nesne.

Aşağıdaki tabloda, ne üzerinde çağrılan yöntemi nesnesi üzerinde göre hangi değişiklikler uygulandıktan açıklanmaktadır.

|Yöntem|Sonuç|
|------------|------------|
|<xref:System.Data.DataRow.AcceptChanges%2A?displayProperty=fullName>|Değişiklikler yalnızca belirli satırındaki çalışıyoruz.|
|<xref:System.Data.DataTable.AcceptChanges%2A?displayProperty=fullName>|Değişiklikleri belirli tablodaki tüm satırları adamış bulunuyoruz.|
|<xref:System.Data.DataSet.AcceptChanges%2A?displayProperty=fullName>|Değişiklik kümesinin tüm tablolardaki tüm satırları adamış bulunuyoruz.|

> [!NOTE]
>  TableAdapter's çağırarak bir veri kümesi yük durumunda `Fill` yöntemi, siz açıkça değişiklikleri kabul etmek zorunda değilsiniz. Varsayılan olarak, `Fill` yöntem çağrılarını `AcceptChanges` veri tablosu doldurma bittikten sonra yöntemi.

 İlgili yöntem <xref:System.Data.DataSet.RejectChanges%2A>, kopyalayarak değişikliklerin etkisini alır <xref:System.Data.DataRowVersion.Original> sürümüne geri <xref:System.Data.DataRowVersion.Current> kayıtları sürümü. Ayrıca ayarlar <xref:System.Data.DataRow.RowState%2A> , her kayıt geri <xref:System.Data.DataRowState.Unchanged>.

## <a name="data-validation"></a>Veri doğrulama
 Uygulamanızdaki verileri için geçirilen işlemlerin gereksinimlerini karşıladığını doğrulamak için genellikle doğrulama eklemeniz gerekir. Bu formdaki bir kullanıcının giriş uygulamanıza başka bir uygulama tarafından gönderilen verileri doğrulama ya da devre dışı bile bileşeniniz içinde hesaplanan bilgi veri kaynağınız kısıtlamaları içinde kalan denetimi doğru olduğunu denetleme gerektirebilir ve uygulama gereksinimleri.

 Verileri çeşitli yöntemlerle doğrulayabilirsiniz:

-   Verileri doğrulamak için uygulamanıza kod ekleyerek iş katmanında. Veri kümesi, bunu yapmak için bir yerdir. Veri kümesi bazı arka uç doğrulama faydaları sağlar: sütun ve satır değerlerini değiştirme gibi değişiklikleri doğrulama olanağı gibi. Daha fazla bilgi için bkz: [veri kümelerindeki verileri doğrulama](../data-tools/validate-data-in-datasets.md).

-   Doğrulama için formlar ekleyerek sunu katmanındaki. Daha fazla bilgi için bkz: [Windows Forms'ta kullanıcı girdisi doğrulama](/dotnet/framework/winforms/user-input-validation-in-windows-forms).

-   Veri kaynağına veri göndererek arka uç, verileri — Örneğin, veritabanı — ve kabul edin veya verileri reddetmek etkinleştirilebilir. Verileri doğrulama ve hata bilgilerini sağlama özellikleri, Gelişmiş bir veritabanı ile çalışıyorsanız, burada alanından gelir olsun verileri doğrulamak için bu pratik bir yaklaşım olabilir. Ancak, bu yaklaşım uygulamaya özgü doğrulama gereksinimlerini karşılamak değil. Ayrıca, veri doğrulama veri kaynağı içinde çok sayıda gidiş dönüş nasıl uygulamanızın arka ucu tarafından gerçekleştirilen doğrulama hatalarını çözümleme kolaylaştıran bağlı olarak veri kaynağına neden olabilir.

    > [!IMPORTANT]
    >  Veri komutları ile kullanırken bir <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> ayarlamak için özellik <xref:System.Data.CommandType.Text>, dikkatlice veritabanınıza geçirmeden önce bir istemciden gönderilen bilgilere bakın. Kötü niyetli kullanıcılar göndermeyi deneyin (Ekle) yetkisiz erişim elde veya veritabanının zarar verecek çaba değiştirilmiş veya ek SQL deyimlerinde. Bir veritabanı için kullanıcı girişi aktarmadan önce her zaman bilgilerin geçerli olduğunu doğrulayın. Parametreli sorgular veya saklı yordam mümkün olduğunda her zaman kullanmak için en iyi bir uygulamadır.

## <a name="transmitting-updates-to-the-data-source"></a>Veri kaynağına aktaran güncelleştirmeleri
Bir veri kümesinde değişiklikler yapıldıktan sonra bir veri kaynağına yapılan iletebilir. En yaygın olarak, çağırarak bunu `Update` yöntemi bir TableAdapter (veya veri bağdaştırıcısı). Bir veri tablosunda her kayıt aracılığıyla yöntemi döngüler belirler hangi güncelleştirme türünü gereklidir (güncelleştirme, ekleme veya silme), varsa, ve ardından uygun komutu çalıştırır.

 Güncelleştirmeleri nasıl yapılacağını çizim, uygulamanızın tek veri tablosu içeren bir veri kümesi kullandığını varsayın. Uygulama veritabanından iki satır getirir. Sonra alma, bellek içi veri tablosu şöyle görünür:

```
(RowState)     CustomerID   Name             Status
(Unchanged)    c200         Robert Lyon      Good
(Unchanged)    c400         Nancy Buchanan    Pending
```

 Uygulamanızı Nancy Buchanan'ın durumunu "Tercih edilen olarak." değiştirir. Değeri, bu değişikliğin sonucu olarak <xref:System.Data.DataRow.RowState%2A> ilgili satır özelliğini değiştirir <xref:System.Data.DataRowState.Unchanged> için <xref:System.Data.DataRowState.Modified>. Değeri <xref:System.Data.DataRow.RowState%2A> ilk satırın özelliğinin kalır <xref:System.Data.DataRowState.Unchanged>. Veri tablosu şimdi şöyle görünür:

```
(RowState)     CustomerID   Name             Status
(Unchanged)    c200         Robert Lyon      Good
(Modified)     c400         Nancy Buchanan    Preferred
```

 Uygulamayı şimdi çağrılarınızı `Update` dataset veritabanına aktarmak için yöntem. Yöntem her satır sırayla olup olmadığını denetler. Başlangıçta veritabanından getirildikten sonra o satırdaki değişmediği için ilk satırı için yöntemi hiçbir SQL deyimini veritabanına iletir.

 İkinci satırda, ancak `Update` yöntemi otomatik olarak doğru veri komutu çalıştırır ve veritabanına aktarır. SQL deyimi belirli söz dizimi temel veri deposu tarafından desteklenen SQL dialect bağlıdır. Ancak, aşağıdaki genel özellikleri iletilen SQL deyiminin dikkate değer:

-   İletilen SQL deyimi bir güncelleştirme ifadesi olur. Bağdaştırıcı için güncelleştirme deyimini bilir değerini <xref:System.Data.DataRow.RowState%2A> özelliği <xref:System.Data.DataRowState.Modified>.

-   UPDATE deyiminin hedef satır olduğunu belirten bir WHERE yan tümcesi iletilen SQL deyimi içeren burada `CustomerID = 'c400'`. Bu bölümü SELECT deyiminin hedef satırdaki tüm başkalarından olduğundan ayırt `CustomerID` hedef tablonun birincil anahtarı. WHERE yan tümcesi kaydı özgün sürümünden türetilmiş yönelik bilgileri (`DataRowVersion.Original`), satır tanımlamak için gerekli değerleri değiştirilmiş durumda.

-   İletilen SQL deyimini değiştirilmiş sütunların yeni değerleri ayarlamak için SET yan tümcesi içerir.

    > [!NOTE]
    > Varsa TableAdapter's `UpdateCommand` özelliği için bir saklı yordam adı ayarlandı, bağdaştırıcı bir SQL deyimi oluşturmak değil. Bunun yerine, geçirilen uygun parametrelerle saklı yordamı çağırır.

## <a name="passing-parameters"></a>Parametreleri geçirme
 Genellikle veritabanında güncelleştirilmesi giderek kayıtlar için değerleri geçirmeniz parametrelerini kullanın.  Zaman TableAdapter's `Update` yöntemi çalıştıktan bir UPDATE deyimi, parametre değerleri doldurmak gerekiyor. Bu değerleri alır `Parameters` koleksiyonu uygun veri komutu için — bu durumda, `UpdateCommand` TableAdapter nesnesi.

 Bir veri bağdaştırıcısı oluşturmak için Visual Studio Araçları kullandıysanız `UpdateCommand` nesnesini içeren her bir parametre yer tutucu deyimindeki karşılık parametreleri topluluğu.

 <xref:System.Data.SqlClient.SqlParameter.SourceColumn%2A?displayProperty=fullName> Özelliği, her parametrenin veri tablodaki bir sütun işaret eder. Örneğin, `SourceColumn` özelliği için `au_id` ve `Original_au_id` parametreleri, hangi veri tablosu sütununda Yazar Kimliği içeriyor için ayarlanır. Olduğunda bağdaştırıcının `Update` yöntemi çalışır, bu Yazar kimlik sütunu güncelleştirilmekte ve değerleri ifadesine doldurur kaydı okur.

 UPDATE deyiminde, her iki yeni değerleri (olanlar kayda yazılır) yanı sıra eski değerleri (kayıt veritabanında konumlandırılabilir böylece) belirtmeniz gerekir. Bu nedenle her bir değer için iki parametre vardır: biri SET yan tümcesinin ve WHERE yan tümcesi için farklı bir. Her iki parametre güncelleştirilmekte kaydından veri okuma, ancak farklı sürümlerini parametresi 's temelinde sütun değeri elde <xref:System.Data.SqlClient.SqlParameter.SourceVersion> özelliği. Geçerli sürüm parametresi SET yan tümcesi için alır ve WHERE yan tümcesi için parametresi özgün sürümünü alır.

> [!NOTE]
> De değerlerini ayarlayabilirsiniz `Parameters` koleksiyonu kendiniz bir olay işleyicisi veri bağdaştırıcının için genellikle yaptığınız kod <xref:System.Data.DataTable.RowChanging> olay.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da veri kümesi araçları](../data-tools/dataset-tools-in-visual-studio.md)
- [Oluşturma ve TableAdapters öğelerini yapılandırma](create-and-configure-tableadapters.md)
- [TableAdapter kullanarak verileri güncelleştirme](../data-tools/update-data-by-using-a-tableadapter.md)
- [Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md)
- [Verileri doğrulama](validate-data-in-datasets.md)
- [Verileri Kaydetme](../data-tools/saving-data.md)