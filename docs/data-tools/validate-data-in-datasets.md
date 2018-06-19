---
title: Veri kümelerindeki verileri doğrulama
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DataTable.ColumnChanging
- System.Data.DataTable.ColumnChanging
- System.Data.DataTable.RowChanging
- DataTable.RowChanging
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data validation, datasets
- data validation
- validating data, datasets
- updating datasets, validating data
ms.assetid: 79500596-1e4d-478e-a991-a636fd73a622
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: c8986ce9e2ee1ff171a524b0a402a1e44b70ca06
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31927474"
---
# <a name="validate-data-in-datasets"></a>Veri kümelerindeki verileri doğrulama
Verileri doğrulama kısıtlamaları bir veri kümesi'nin şema içinde veri nesnelerine girilmesini değerleri uygun onaylayan işlemidir. Doğrulama işlemini de bu değerleri, uygulamanız için kurulmuş kuralları takip onaylar. Temel alınan veritabanı güncelleştirme göndermeden önce verileri doğrulamak için iyi bir uygulamadır. Bu, hataları ve bunun yanı sıra olası bir uygulama ve veritabanı arasındaki gidiş dönüş sayısını azaltır.

Doğrulama denetimlerini kümesine oluşturarak, bir veri kümesine yazılan veri geçerli olduğunu doğrulayabilirsiniz. Veri kümesi güncelleştirmesi nasıl gerçekleştirildiği olsun veri denetleyebilirsiniz — doğrudan bir bileşeni içinde bir form veya başka bir yolla denetimler tarafından mı yoksa. Veri kümesi, uygulamanızın (aksine, veritabanı arka ucu) bir parçası olduğundan, uygulamaya özgü doğrulama oluşturmak için mantıksal bir yerdir.

Veri kümesi'nin kısmi sınıf dosyasında doğrulama uygulamanıza eklemek için en iyi yerdir. İçinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] veya [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)], açık **veri kümesi Tasarımcısı** ve doğrulama oluşturmak istediğiniz sütun veya tablo çift tıklatın. Bu eylem otomatik olarak oluşturur bir <xref:System.Data.DataTable.ColumnChanging> veya <xref:System.Data.DataTable.RowChanging> olay işleyicisi.

## <a name="validate-data"></a>Veri doğrulama
 Dataset içindeki doğrulama aşağıdaki yollarla gerçekleştirilebilir:

-   Kendi uygulamaya özgü doğrulama oluşturarak değişiklikleri sırasında bir tek veri sütundaki değerleri kontrol edebilirsiniz.  Daha fazla bilgi için bkz: [nasıl yapılır: doğrulama veri sırasında sütun değişiklikleri](validate-data-in-datasets.md).

-   Tüm veriler değerlerine veri denetleyebilirsiniz kendi uygulamaya özgü doğrulama oluşturarak satır değiştiriyor. Daha fazla bilgi için bkz: [nasıl yapılır: doğrulama veri sırasında satır değişiklikleri](validate-data-in-datasets.md).

-   Benzersiz kısıtlamalar, anahtarları ve benzeri gerçek şema tanımı veri kümesinin bir parçası olarak oluşturarak.

-   Özelliklerini ayarlayarak <xref:System.Data.DataColumn> nesnenin, gibi <xref:System.Data.DataColumn.MaxLength%2A>, <xref:System.Data.DataColumn.AllowDBNull%2A>, ve <xref:System.Data.DataColumn.Unique%2A>.

Bazı olaylar tarafından gerçekleştirilen <xref:System.Data.DataTable> nesne bir değişiklik bir kayıtta oluştuğu zaman:

-   <xref:System.Data.DataTable.ColumnChanging> Ve <xref:System.Data.DataTable.ColumnChanged> sırasında ve tek bir sütun için her bir değişiklikten sonra olayları ortaya çıkar. <xref:System.Data.DataTable.ColumnChanging> Olayı, belirli sütunlardaki değişiklikleri doğrulamak istediğinizde yararlıdır. Önerilen değişikliği hakkında bilgi içeren olay bağımsız değişken olarak geçirilir.
-   <xref:System.Data.DataTable.RowChanging> Ve <xref:System.Data.DataTable.RowChanged> olayları yükseltilmiş sırasında ve sonrasında herhangi bir satır değişikliği. <xref:System.Data.DataTable.RowChanging> Olaydır daha genel. Bir değişiklik yere satırda oluştuğunu, ancak hangi sütunun değişti tanımadığınız gösterir.

Varsayılan olarak, her değişiklik bir sütuna, bu nedenle dört olayları başlatır. İlk <xref:System.Data.DataTable.ColumnChanging> ve <xref:System.Data.DataTable.ColumnChanged> değiştiriliyor belirli sütun için olaylar. Sonraki olan <xref:System.Data.DataTable.RowChanging> ve <xref:System.Data.DataTable.RowChanged> olaylar. Satırda birden fazla değişiklik yaptığınız olayları için her bir değişiklikten gerçekleştirilecektir.

> [!NOTE]
>  Veri sıranın <xref:System.Data.DataRow.BeginEdit%2A> yöntemi kapanmadan <xref:System.Data.DataTable.RowChanging> ve <xref:System.Data.DataTable.RowChanged> her tek sütun değişiklikten sonra olaylar. Bu durumda, olay kadar oluşmaz <xref:System.Data.DataRow.EndEdit%2A> yönteminin çağrılıp çağrılmadığını, ne zaman <xref:System.Data.DataTable.RowChanging> ve <xref:System.Data.DataTable.RowChanged> olaylar yalnızca bir kez başlatılır. Daha fazla bilgi için bkz: [bir veri kümesini doldururken kısıtlamaları kapatma kapatma](../data-tools/turn-off-constraints-while-filling-a-dataset.md).

Seçtiğiniz olay nasıl ayrıntılı doğrulama olmasını istediğiniz bağlıdır. Bir sütun değiştiğinde hemen bir hata catch önemliyse, doğrulama kullanarak yapı <xref:System.Data.DataTable.ColumnChanging> olay. Aksi takdirde kullanın <xref:System.Data.DataTable.RowChanging> çeşitli hatalar aynı anda yakalama sonuçlanabilir olay. Ayrıca, böylece bir sütunun değerini başka bir sütunun içeriğine göre doğrulanır, verileri yapılandırıldıysa, sonra doğrulama sırasında gerçekleştirin <xref:System.Data.DataTable.RowChanging> olay.

Kayıtları güncelleştirildiğinde, <xref:System.Data.DataTable> nesnesi değişiklikleri gerçekleşen değişiklikler yapıldıktan sonra ve yanıt verebilirsiniz olayları başlatır.

Türü belirtilmiş veri kümesi, uygulamanızın kullanıyorsa, kesin türü belirtilmiş olay işleyicileri oluşturabilirsiniz. Bu işleyiciler için oluşturabileceğiniz dört ek yazılan olaylar ekleyecektir: `dataTableNameRowChanging`, `dataTableNameRowChanged`, `dataTableNameRowDeleting`, ve `dataTableNameRowDeleted`. Bu yazılan olay işleyicileri kod yazmak ve okumak daha kolay hale tablosunun sütun adlarını içeren bir bağımsız değişken geçirin.

## <a name="data-update-events"></a>Verileri güncelleştirme olayları

|Olay|Açıklama|
|-----------|-----------------|
|<xref:System.Data.DataTable.ColumnChanging>|Bir sütundaki değeri olarak değiştiriliyor. Olay satır ve sütun için önerilen yeni değeri ile birlikte geçirir.|
|<xref:System.Data.DataTable.ColumnChanged>|Bir sütundaki değeri değiştirildi. Olay satır ve sütun için önerilen değeri ile birlikte geçirir.|
|<xref:System.Data.DataTable.RowChanging>|Yapılan değişiklikler bir <xref:System.Data.DataRow> nesnesi hakkında veri kümesine geri işleminde üzeresiniz. Çağrılmaz durumunda <xref:System.Data.DataRow.BeginEdit%2A> yöntemi, <xref:System.Data.DataTable.RowChanging> olayı her değişiklik bir sütun için hemen sonra <xref:System.Data.DataTable.ColumnChanging> olay tetiklenir. Aradığınız varsa <xref:System.Data.DataRow.BeginEdit%2A> değişiklik yapmadan önce <xref:System.Data.DataTable.RowChanging> olayı yalnızca çağırdığınızda <xref:System.Data.DataRow.EndEdit%2A> yöntemi.<br /><br /> Olay satır sizin için ne tür eylemi (değişiklik, Ekle ve benzeri) gerçekleştirilen belirten bir değer ile birlikte geçirir.|
|<xref:System.Data.DataTable.RowChanged>|Bir satır değiştirildi. Olay satır sizin için ne tür eylemi (değişiklik, Ekle ve benzeri) gerçekleştirilen belirten bir değer ile birlikte geçirir.|
|<xref:System.Data.DataTable.RowDeleting>|Bir satır siliniyor. Olay satır sizin için ne tür eylemi (silme) gerçekleştirilen belirten bir değer ile birlikte geçirir.|
|<xref:System.Data.DataTable.RowDeleted>|Bir satır silindi. Olay satır sizin için ne tür eylemi (silme) gerçekleştirilen belirten bir değer ile birlikte geçirir.|

<xref:System.Data.DataTable.ColumnChanging>, <xref:System.Data.DataTable.RowChanging>, Ve <xref:System.Data.DataTable.RowDeleting> olayları güncelleştirme işlemi sırasında oluşur. Veri doğrulama veya diğer tür işlem gerçekleştirmek için bu olayları kullanabilirsiniz. Güncelleştirme sırasında bu olayları sürecinde olduğundan, bir özel durum Update'ten önleyen atma tarafından iptal edebilirsiniz tamamlanıyor.

<xref:System.Data.DataTable.ColumnChanged>, <xref:System.Data.DataTable.RowChanged> Ve <xref:System.Data.DataTable.RowDeleted> güncelleştirmeyi başarıyla tamamlandığında, oluşturulan bildirim olayları olaylardır. Bu olaylar başka bir işlem başarılı bir güncelleştirme dayalı yapmanıza istediğinizde faydalıdır.

## <a name="validate-data-during-column-changes"></a>Sütun değişiklikleri sırasında veri doğrulama

> [!NOTE]
>  **Veri kümesi Tasarımcısı** hangi doğrulama mantığını bir veri kümesine eklenebilir kısmi bir sınıf oluşturur. Tasarımcı tarafından üretilen veri kümesi silin veya herhangi bir parçalı sınıf kodda değişiklik değil.

Bir veri sütununun değeri yanıt vererek değiştiğinde verileri doğrulayabilir <xref:System.Data.DataTable.ColumnChanging> olay. Oluştuğunda, bu olay bir olay bağımsız değişkenini geçirir (<xref:System.Data.DataColumnChangeEventArgs.ProposedValue%2A>) geçerli sütun için önerilen değeri içerir. İçeriğini temel alarak `e.ProposedValue`, şunları yapabilirsiniz:

-   Önerilen değer nothing yaparak kabul edin.

-   Önerilen değer sütun hata ayarlayarak Reddet (<xref:System.Data.DataRow.SetColumnError%2A>) gelen sütun değiştirme olay işleyicisi içinde.

-   İsteğe bağlı olarak kullanan bir <xref:System.Windows.Forms.ErrorProvider> denetim kullanıcıya bir hata iletisi görüntülenir. Daha fazla bilgi için bkz: [ErrorProvider bileşeni](/dotnet/framework/winforms/controls/errorprovider-component-windows-forms).

Doğrulama de yapılabilir sırasında <xref:System.Data.DataTable.RowChanging> olay.

## <a name="validate-data-during-row-changes"></a>Satır değişiklikleri sırasında veri doğrulama
Doğrulamak istediğiniz her bir sütunun uygulamanızı gereksinimlerini karşılayan verileri içerdiğini doğrulamak üzere kod yazabilirsiniz. Önerilen değer kabul edilebilir değilse, bir hata var. göstermek için sütun ayarlayarak bunu yapabilirsiniz. Aşağıdaki örnekler kümesi sütunu hatası olduğunda `Quantity` sütundur 0 veya daha az. Satır değiştirme olay işleyicileri aşağıdaki örneklerde benzemelidir.

#### <a name="to-validate-data-when-a-row-changes-visual-basic"></a>Verileri bir satır doğrulamak için (Visual Basic) değiştirir.

1.  Bir veri kümesini açma **veri kümesi Tasarımcısı**. Daha fazla bilgi için bkz: [izlenecek yol: veri kümesi tasarımcısında bir veri kümesi oluşturma](walkthrough-creating-a-dataset-with-the-dataset-designer.md).

2.  Doğrulamak istediğiniz tablonun başlık çubuğu çift tıklatın. Bu eylem otomatik olarak oluşturur <xref:System.Data.DataTable.RowChanging> olay işleyicisi <xref:System.Data.DataTable> veri kümesi'nin parçalı sınıf dosyasında.

    > [!TIP]
    >  Satır değiştirme olay işleyicisi oluşturmak için tablo adının solundaki çift tıklayın. Tablo adı çift tıklarsanız düzenleyebilirsiniz.

     [!code-vb[VbRaddataValidating#3](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_1.vb)]

#### <a name="to-validate-data-when-a-row-changes-c"></a>Bir satır (C#) değiştiğinde verileri doğrulamak için

1.  Bir veri kümesini açma **veri kümesi Tasarımcısı**. Daha fazla bilgi için bkz: [izlenecek yol: veri kümesi tasarımcısında bir veri kümesi oluşturma](walkthrough-creating-a-dataset-with-the-dataset-designer.md).

2.  Doğrulamak istediğiniz tablonun başlık çubuğu çift tıklatın. Bu eylem için bir parçalı sınıf dosyası oluşturur <xref:System.Data.DataTable>.

    > [!NOTE]
    >  **Veri kümesi Tasarımcısı** bir olay işleyicisi için otomatik olarak oluşturmaz <xref:System.Data.DataTable.RowChanging> olay. İşlemek için bir yöntem oluşturmak zorunda <xref:System.Data.DataTable.RowChanging> tablonun başlatma yöntemini olayda bağlanacağını için olay ve kodu çalıştırın.

3.  Kısmi sınıfına aşağıdaki kodu kopyalayın:

    ```csharp
    public override void EndInit()
    {
        base.EndInit();
        Order_DetailsRowChanging += TestRowChangeEvent;
    }

    public void TestRowChangeEvent(object sender, Order_DetailsRowChangeEvent e)
    {
        if ((short)e.Row.Quantity <= 0)
        {
            e.Row.SetColumnError("Quantity", "Quantity must be greater than 0");
        }
        else
        {
            e.Row.SetColumnError("Quantity", "");
        }
    }
    ```

## <a name="to-retrieve-changed-rows"></a>Değiştirilen satırları almak için
Bir veri tablodaki her satır sahip bir <xref:System.Data.DataRow.RowState%2A> satır geçerli durumunu değerleri kullanarak izler özelliği <xref:System.Data.DataRowState> numaralandırması. Çağırarak dataset ya da veri tablosundan değiştirilen satırları döndürebilir `GetChanges` yöntemi bir <xref:System.Data.DataSet> veya <xref:System.Data.DataTable>. Değişiklikleri arama önce mevcut olduğunu doğrulayın `GetChanges` çağırarak <xref:System.Data.DataSet.HasChanges%2A> yöntemi bir veri kümesi.

> [!NOTE]
>  Bir veri kümesi veya veri tablosuna değişiklikleri sonra (çağırarak <xref:System.Data.DataSet.AcceptChanges%2A> yöntemi), `GetChanges` yöntemi hiçbir veri döndürür. Uygulamanızı değiştirilen satırları işlem gerekiyorsa çağırmadan önce değişiklikleri işlemelidir `AcceptChanges` yöntemi.

Çağırma <xref:System.Data.DataSet.GetChanges%2A> yöntemi dataset ya da veri tablosunun değiştirilmiş yalnızca kayıtlarını içeren yeni bir veri kümesi ya da veri tablosu döndürür. Belirli kayıtları almak istiyorsanız — örneğin, yalnızca yeni kayıtları veya yalnızca değiştirilen kayıtları — arasında bir değer geçirebilirsiniz <xref:System.Data.DataRowState> numaralandırması için bir parametre olarak `GetChanges` yöntemi.

Kullanım <xref:System.Data.DataRowVersion> bir satır (işlemeyi önce bir satırda olan Örneğin, orijinal değerleri) farklı sürümlerini erişmek için numaralandırması.

#### <a name="to-get-all-changed-records-from-a-dataset"></a>Bir veri kümesinden tüm kayıtlar almak için

-   Çağrı <xref:System.Data.DataSet.GetChanges%2A> yöntemi bir veri kümesi.

     Aşağıdaki örnek adlı yeni bir veri kümesi oluşturur `changedRecords` ve adlı başka bir veri kümesinden tüm kayıtlar ile doldurur `dataSet1`.

     [!code-csharp[VbRaddataEditing#14](../data-tools/codesnippet/CSharp/validate-data-in-datasets_2.cs)]
     [!code-vb[VbRaddataEditing#14](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_2.vb)]

#### <a name="to-get-all-changed-records-from-a-data-table"></a>Bir veri tablodan tüm kayıtlar almak için

-   Çağrı <xref:System.Data.DataTable.GetChanges%2A> DataTable yöntemi.

     Aşağıdaki örnek olarak adlandırılan yeni bir veri tablosu oluşturur `changedRecordsTable` ve adlı başka bir veri tablodan tüm kayıtlar ile doldurur `dataTable1`.

     [!code-csharp[VbRaddataEditing#15](../data-tools/codesnippet/CSharp/validate-data-in-datasets_3.cs)]
     [!code-vb[VbRaddataEditing#15](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_3.vb)]

#### <a name="to-get-all-records-that-have-a-specific-row-state"></a>Belirli satır durumunda olan tüm kayıtları almak için

-   Çağrı `GetChanges` yöntemi bir veri kümesi veya veri tablosu ve geçişi bir <xref:System.Data.DataRowState> bağımsız değişken olarak numaralandırma değeri.

     Aşağıdaki örnek olarak adlandırılan yeni bir veri kümesi oluşturma gösterilmektedir `addedRecords` ve yalnızca için eklenene kayıtlarla doldurmak `dataSet1` veri kümesi.

     [!code-csharp[VbRaddataEditing#16](../data-tools/codesnippet/CSharp/validate-data-in-datasets_4.cs)]
     [!code-vb[VbRaddataEditing#16](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_4.vb)]

     Aşağıdaki örnekte, en son eklenen tüm kayıtları döndürmek gösterilmiştir `Customers` tablosu:

     [!code-csharp[VbRaddataEditing#17](../data-tools/codesnippet/CSharp/validate-data-in-datasets_5.cs)]
     [!code-vb[VbRaddataEditing#17](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_5.vb)]

## <a name="access-the-original-version-of-a-datarow"></a>Erişim DataRow özgün sürümü
Veri satırları değişiklik yapıldığında, veri kümesi hem özgün korur (<xref:System.Data.DataRowVersion.Original>) ve yeni (<xref:System.Data.DataRowVersion.Current>) satır sürümleri. Örneğin, önce çağırma `AcceptChanges` yöntemi, uygulamanızın farklı sürümlerini kaydının erişebilirsiniz (tanımlandığı gibi <xref:System.Data.DataRowVersion> numaralandırması) ve uygun şekilde değişiklikleri işleme.

> [!NOTE]
>  Bir satır farklı sürümlerini mevcut yalnızca düzenlendi sonra ve kendisinden önce `AcceptChanges` yöntemi çağrılır. Sonra `AcceptChanges` yöntemi çağrılır, geçerli ve özgün sürümleri aynıdır.

Geçirme <xref:System.Data.DataRowVersion> değeri sütun dizini (veya sütun adı bir dize olarak) ile birlikte bu sütunun belirli bir satır sürümünden değeri döndürür. Değiştirilen sütun sırasında tanımlanan <xref:System.Data.DataTable.ColumnChanging> ve <xref:System.Data.DataTable.ColumnChanged> olaylar. Bu doğrulama amacıyla farklı satır sürümleri incelemek için iyi bir zamandır. Ancak, kısıtlamalar geçici olarak askıya, olayları yükseltilmiş olmaz ve program aracılığıyla gerekir hangi sütunların değiştiğini belirlemek. Bunu üzerinden yineleme tarafından yapmak <xref:System.Data.DataTable.Columns%2A> toplama ve farklı karşılaştırma <xref:System.Data.DataRowVersion> değerleri.

#### <a name="to-get-the-original-version-of-a-record"></a>Bir kayıt özgün sürümünü almak için

-   Bir sütunun değerini geçirerek erişim <xref:System.Data.DataRowVersion> istediğiniz döndürülecek satır.

     Aşağıdaki örnekte nasıl kullanılacağını gösteren bir <xref:System.Data.DataRowVersion> özgün değerini almak için değer bir `CompanyName` alanındaki bir <xref:System.Data.DataRow>:

     [!code-csharp[VbRaddataEditing#21](../data-tools/codesnippet/CSharp/validate-data-in-datasets_6.cs)]
     [!code-vb[VbRaddataEditing#21](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_6.vb)]

## <a name="access-the-current-version-of-a-datarow"></a>Erişim DataRow geçerli sürümü

#### <a name="to-get-the-current-version-of-a-record"></a>Bir kayıt geçerli sürümü almak için

-   Bir sütunun değerini erişmek ve ardından bir parametre döndürmek istediğiniz bir satır hangi sürümünün gösteren dizine ekleyin.

     Aşağıdaki örnekte nasıl kullanılacağını gösteren bir <xref:System.Data.DataRowVersion> geçerli değerini almak için değer bir `CompanyName` alanındaki bir <xref:System.Data.DataRow>:

     [!code-csharp[VbRaddataEditing#22](../data-tools/codesnippet/CSharp/validate-data-in-datasets_7.cs)]
     [!code-vb[VbRaddataEditing#22](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_7.vb)]

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da veri kümesi araçları](../data-tools/dataset-tools-in-visual-studio.md)
- [Nasıl yapılır: Windows Forms DataGridView Denetiminde Verileri Doğrulama](/dotnet/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control)
- [Nasıl yapılır: Windows Forms ErrorProvider Bileşeni ile Form Doğrulama için Hata Simgeleri Görüntüleme](/dotnet/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider)