---
title: 'İzlenecek yol: çalışma zamanında Şerit denetimlerini güncelleştirme'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], controls
- updating Ribbon controls
- Ribbon [Office development in Visual Studio], dynamic menu
- dynamic menus [Office development in Visual Studio]
- Ribbon [Office development in Visual Studio], updating
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b2d9f8a585b6a9353c9e64cf03b0876e5324a539
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35258807"
---
# <a name="walkthrough-update-the-controls-on-a-ribbon-at-runtime"></a>İzlenecek yol: çalışma zamanında Şerit denetimlerini güncelleştirme
  Bu anlatımda Şerit nesne modeline Şerit Office uygulamasına yüklendikten sonra bir Şerit denetimlerini güncellemek için nasıl kullanılacağı gösterilir.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
 Örnek bir birleşik giriş kutusu ve Microsoft Office Outlook menüde doldurmak için Northwind örnek veritabanı veri çeker. Bu denetimlerin otomatik olarak seçtiğiniz öğeler doldurmak alanları gibi **için** ve **konu** bir e-posta iletisi.  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Yeni bir Outlook VSTO eklenti projesi oluşturun.  
  
-   Özel Şerit grubu tasarlayın.  
  
-   Özel bir grup için yerleşik bir sekmeyi ekleyin.  
  
-   Çalışma zamanında Şerit üzerindeki denetimleri güncelleştirin.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Outlook  
  
## <a name="create-a-new-outlook-vsto-add-in-project"></a>Yeni bir Outlook VSTO eklenti projesi oluşturma  
 İlk olarak, bir Outlook VSTO eklenti projesi oluşturun.  
  
### <a name="to-create-a-new-outlook-vsto-add-in-project"></a>Yeni bir Outlook VSTO eklenti projesi oluşturmak için  
  
1.  İçinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], Outlook VSTO eklenti projesindeki adlı oluşturun **Çalışma_Zamanında_Şerit_Güncelleme**.  
  
2.  İçinde **yeni proje** iletişim kutusunda **çözüm için dizin oluştur**.  
  
3.  Projeyi varsayılan proje dizinine kaydedin.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio oluşturma Office projelerinde](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
## <a name="design-a-custom-ribbon-group"></a>Özel Şerit grubu tasarlama  
 Bir kullanıcı yeni bir posta iletisi yazdığında bu örnek için Şerit görünür. Şerit için özel bir grup oluşturmak için önce bir Şerit öğesi projenize ekleyin ve Şerit Tasarımcısı grubunda tasarım. Bu özel grup adları çekerek müşterilere izleme e-posta iletileri oluşturabilir ve veritabanından geçmişlerini sipariş yardımcı olur.  
  
### <a name="to-design-a-custom-group"></a>Özel bir grup tasarlamak için  
  
1.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  
  
2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **Şerit (Görsel Tasarımcı)**.  
  
3.  Yeni Şerit adını değiştirmek **CustomerRibbon**ve ardından **Ekle**.  
  
     *CustomerRibbon.cs* veya *CustomerRibbon.vb* dosyası Şerit Tasarımcısı'nda açılır ve varsayılan bir sekme ve grup görüntüler.  
  
4.  Şerit Tasarımcısı seçmek için tıklatın.  
  
5.  İçinde **özellikleri** penceresinde, aşağı açılan oku tıklatın **RibbonType** özelliği ve ardından **Microsoft.Outlook.Mail.Compose**.  
  
     Bu kullanıcı Outlook içinde yeni bir posta iletisi yazdığında Şerit sağlar.  
  
6.  Şerit Tasarımcısı'nda tıklatın **Group1** seçin.  
  
7.  İçinde **özellikleri** penceresindeki ayarlayın **etiket** için **Müşteri Harcamaları**.  
  
8.  Gelen **Office Şerit denetimleri** sekmesinde **araç**, sürükleyin bir **ComboBox** üzerine **Müşteri Harcamaları** grubu.  
  
9. Tıklatın **ComboBox1** seçin.  
  
10. İçinde **özellikleri** penceresindeki ayarlayın **etiket** için **müşteriler**.  
  
11. Gelen **Office Şerit denetimleri** sekmesinde **araç**, sürükleyin bir **menü** üzerine **Müşteri Harcamaları** grubu.  
  
12. İçinde **özellikleri** penceresindeki ayarlayın **etiket** için **ürün satın**.  
  
13. Ayarlama **dinamik** için **doğru**.  
  
     Bu ekleyin ve Şerit Office uygulamasına yüklendikten sonra denetimlerini çalışma zamanında menüsünde kaldırmanızı sağlar.  
  
## <a name="add-the-custom-group-to-a-built-in-tab"></a>Yerleşik bir sekmeyi özel Grup Ekle  
 Yerleşik bir sekmeyi bir Outlook Explorer veya denetçisinin Şerit üzerinde zaten var olan sekme olarak kullanılır. Bu yordamda, yerleşik bir sekmeyi özel grubunu ekleyin ve ardından sekmesinde özel grup konumunu belirtin.  
  
### <a name="to-add-the-custom-group-to-a-built-in-tab"></a>Yerleşik bir sekmeyi özel grup eklemek için  
  
1.  Tıklatın **TabAddins (yerleşik)** sekmesini seçin.  
  
2.  İçinde **özellikleri** penceresinde genişletin **ControlId** özelliğini ayarlayın ve ardından **OfficeId** için **TabNewMailMessage**.  
  
     Bu ekler **Müşteri Harcamaları** grubunu **iletileri** yeni bir posta iletisi içinde görünür Şerit sekmesi.  
  
3.  Tıklatın **Müşteri Harcamaları** grubu seçin.  
  
4.  İçinde **özellikleri** penceresinde genişletin **konumu** özelliği, açılan oku tıklatın **PositionType** özelliği ve ardından  **BeforeOfficeId**.  
  
5.  Ayarlama **OfficeId** özelliğine **GroupClipboard**.  
  
     Bu konumlandırır **Müşteri Harcamaları** önce Grup **Pano** grubunu **iletileri** sekmesi.  
  
## <a name="create-the-data-source"></a>Veri kaynağı oluşturun  
 Kullanım **veri kaynakları** penceresi türü belirtilmiş veri kümesi projenize ekleyin.  
  
### <a name="to-create-the-data-source"></a>Veri kaynağı oluşturmak için  
  
1.  Üzerinde **veri** menüsünde tıklatın **yeni veri kaynağı Ekle**.  
  
     Bu başlatır **veri kaynağı Yapılandırma Sihirbazı**.  
  
2.  Seçin **veritabanı**ve ardından **sonraki**.  
  
3.  Seçin **Dataset**ve ardından **sonraki**.  
  
4.  Northwind örnek Microsoft SQL Server Compact 4.0 veritabanı veri bağlantısı seçin veya yeni bir bağlantı kullanarak eklemek **yeni bağlantı** düğmesi.  
  
5.  Bir bağlantı seçili veya oluşturulduktan sonra tıklayın **sonraki**.  
  
6.  Tıklatın **sonraki** bağlantı dizesini kaydetmek için.  
  
7.  Üzerinde **veritabanı nesnelerinizi** sayfasında **tabloları**.  
  
8.  Aşağıdaki tablolarda her yanındaki onay kutusunu seçin:  
  
    1.  **Müşteriler**  
  
    2.  **Sipariş ayrıntılarını**  
  
    3.  **Siparişleri**  
  
    4.  **Ürünler**  
  
9. **Son**'a tıklayın.  
  
## <a name="update-controls-in-the-custom-group-at-runtime"></a>Çalışma zamanında özel grup denetimlerini güncelleştirme  
 Şerit nesne modeli, aşağıdaki görevleri gerçekleştirmek için kullanın:  
  
-   Müşteri adları Ekle **müşteriler** birleşik giriş kutusu.  
  
-   Menü ve düğme denetimleri ekleme **satın alınan ürünler** siparişler ve ürünleri temsil eden menü satılan.  
  
-   Kime, konu ve gövde doldurmak verileri kullanarak yeni posta iletileri alanlarının **müşteriler** birleşik giriş kutusu ve **satın alınan ürünler** menüsü.  
  
### <a name="to-update-controls-in-the-custom-group-by-using-the-ribbon-object-model"></a>Şerit nesne modelini kullanarak özel grup denetimlerini güncelleştirmek için  
  
1.  Üzerinde **proje** menüsünde tıklatın **Başvuru Ekle**.  
  
2.  İçinde **Başvuru Ekle** iletişim kutusu, tıklatın **.NET** sekmesine **System.Data.Linq** derleme ve ardından **Tamam**.  
  
     Bu derleme dil ile tümleşik sorgu (LINQ) kullanmak için sınıflar içerir. Northwind veritabanı verileriyle özel grup denetimlerini doldurmak için LINQ kullanır.  
  
3.  İçinde **Çözüm Gezgini**, tıklatın **CustomerRibbon.cs** veya **CustomerRibbon.vb** seçin.  
  
4.  Üzerinde **Görünüm** menüsünde tıklatın **kod**.  
  
     Şerit kod dosyası Kod Düzenleyicisi'nde açılır.  
  
5.  Aşağıdaki deyimleri Şerit kod dosyasının üstüne ekleyin. Bu deyimler LINQ ad alanları ve Outlook birincil birlikte çalışma derlemesi (PIA) ad alanı için kolay erişim sağlar.  
  
     [!code-csharp[Trin_Ribbon_Update_At_Runtime#1](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#1)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#1](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#1)]  
  
6.  Aşağıdaki kodu ekleyin `CustomerRibbon` sınıfı. Bu kod, müşteri, siparişler, sipariş ayrıntılarını ve ürün tablolarında Northwind veritabanı bilgileri depolamak için kullanacağı tablo bağdaştırıcıları ve veri tablosu bildirir.  
  
     [!code-csharp[Trin_Ribbon_Update_At_Runtime#2](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#2)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#2](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#2)]  
  
7.  Aşağıdaki kod bloğunu ekleyin `CustomerRibbon` sınıfı. Bu kod Şerit denetimlerini çalışma zamanında oluşturma üç yardımcı yöntemler ekler.  
  
     [!code-csharp[Trin_Ribbon_Update_At_Runtime#3](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#3)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#3](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#3)]  
  
8.  Değiştir `CustomerRibbon_Load` olay işleyicisi yöntemini aşağıdaki kodla. Bu kod, aşağıdaki görevleri gerçekleştirmek için bir LINQ sorgusu kullanır:  
  
    -   Doldurmak **müşteriler** Northwind veritabanında 20 müşterinin adını ve kimlik Numarasını kullanarak birleşik giriş kutusu.  
  
    -   Çağrıları `PopulateSalesOrderInfo` yardımcı yöntemi. Bu yöntem güncelleştirmeleri **AlınanÜrünler** menüsü, şu anda seçili müşteriye ait sipariş numarası.  
  
     [!code-csharp[Trin_Ribbon_Update_At_Runtime#4](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#4)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#4](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#4)]  
  
9. Aşağıdaki kodu ekleyin `CustomerRibbon` sınıfı. Bu kod, aşağıdaki görevleri gerçekleştirmek için LINQ sorgularını kullanır:  
  
    -   Bir menüye ekler **AlınanÜrünler** her sipariş için menüsü seçili müşteriye ilgili.  
  
    -   Her alt ilgili satış sipariş ürünleri için düğmeler ekler.  
  
    -   Olay işleyicileri her düğmeye ekler.  
  
     [!code-csharp[Trin_Ribbon_Update_At_Runtime#6](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#6)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#6](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#6)]  
  
10. İçinde **Çözüm Gezgini**, Şerit kod dosyasına çift tıklayın.  
  
     Şerit Tasarımcısı'nı açar.  
  
11. Şerit Tasarımcısı'nda çift **müşteriler** birleşik giriş kutusu.  
  
     Kod Düzenleyicisi'nde Şerit kod dosyasını açar ve `ComboBox1_TextChanged` olay işleyicisi görüntülenir.  
  
12. Değiştir `ComboBox1_TextChanged` aşağıdaki kod ile olay işleyicisi. Bu kod aşağıdaki görevleri gerçekleştirir:  
  
    -   Çağrıları `PopulateSalesOrderInfo` yardımcı yöntemi. Bu yöntem güncelleştirmeleri **satın alınan ürünler** seçili müşteriye ilişkili satış siparişleri menüsü.  
  
    -   Çağrıları `PopulateMailItem` yardımcı yöntem ve seçili müşteri adı geçerli bir metin geçirir. Bu yöntem için konu ve gövde doldurur yeni posta iletisinin alanları.  
  
     [!code-csharp[Trin_Ribbon_Update_At_Runtime#5](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#5)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#5](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#5)]  
  
13. Aşağıdakileri ekleyin `Click` olay işleyicisine `CustomerRibbon` sınıfı. Bu kod seçili ürünlerin adını yeni posta iletisinin gövdesi alan ekler.  
  
     [!code-csharp[Trin_Ribbon_Update_At_Runtime#8](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#8)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#8](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#8)]  
  
14. Aşağıdaki kodu ekleyin `CustomerRibbon` sınıfı. Bu kod aşağıdaki görevleri gerçekleştirir:  
  
    -   Yeni posta iletisinin Kime satırında, şu anda seçili müşteri e-posta adresini kullanarak doldurur.  
  
    -   Metin yeni posta iletisinin konu ve gövde alanlara ekler.  
  
     [!code-csharp[Trin_Ribbon_Update_At_Runtime#7](../vsto/codesnippet/CSharp/Ribbon_Update_At_Runtime/CustomerRibbon.cs#7)]
     [!code-vb[Trin_Ribbon_Update_At_Runtime#7](../vsto/codesnippet/VisualBasic/Ribbon_Update_At_Runtime/CustomerRibbon.vb#7)]  
  
## <a name="test-the-controls-in-the-custom-group"></a>Özel grup denetimlerini test  
 Outlook içinde yeni bir posta formu açtığınızda, özel bir grup adlı **Müşteri Harcamaları** kasasındaki **iletileri** Şerit sekmesi.  
  
 Bir müşteri izleme e-posta iletisi oluşturmak üzere bir müşteri seçin ve sonra müşteri tarafından alınan ürünleri seçin. Denetimleri **Müşteri Harcamaları** Grup Northwind veritabanı verilerle çalışma zamanında güncelleştirilir.  
  
### <a name="to-test-the-controls-in-the-custom-group"></a>Özel grup denetimleri sınamak için  
  
1.  Tuşuna **F5** projeyi çalıştırın.  
  
     Outlook'u başlatır.  
  
2.  Outlook'ta, üzerinde **dosya** menüsündeki **yeni**ve ardından **posta iletisi**.  
  
     Aşağıdaki eylemler gerçekleşir:  
  
    -   Yeni bir posta iletisi Inspector penceresi görünür.  
  
    -   Üzerinde **ileti** Şerit sekmesi **Müşteri Harcamaları** grup görünür önce **Pano** grubu.  
  
    -   **Müşteriler** grubunda birleşik giriş kutusunu Northwind veritabanı müşteriler adlarıyla güncelleştirilir.  
  
3.  Üzerinde **ileti** Şerit sekmesi, **Müşteri Harcamaları** grubunda, müşteriden seçin **müşteriler** birleşik giriş kutusu.  
  
     Aşağıdaki eylemler gerçekleşir:  
  
    -   **Satın alınan ürünler** menüsü seçili müşteri için her sipariş göstermek üzere güncelleştirilir.  
  
    -   Her sipariş alt o sırada satın ürünleri göstermek üzere güncelleştirilir.  
  
    -   Seçili müşterinin e-posta adresine eklenen **için** posta iletisi ve konu ve gövde posta iletisinin satırlık metin ile doldurulur.  
  
4.  Tıklatın **ürünleri satın alma işlemleri** menüsünde noktası herhangi bir satış siparişi ve satış siparişi üründen'ye tıklayın.  
  
     Ürün adı posta iletisinin gövdesine eklenir.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 Aşağıdaki konulardan Office kullanıcı arabirimini özelleştirme hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Bağlam tabanlı UI hiçbir belge düzeyi özelleştirme ekleyin. Daha fazla bilgi için bkz: [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md).  
  
-   Standart veya özel bir Microsoft Office Outlook form genişletir. Daha fazla bilgi için bkz: [izlenecek yol: Outlook form bölgesi tasarlama](../vsto/walkthrough-designing-an-outlook-form-region.md).  
  
-   Özel görev bölmesini Outlook'a ekleyin. Daha fazla bilgi için bkz: [özel görev bölmeleri](../vsto/custom-task-panes.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Şerit çalışma zamanında erişme](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Dil ile tümleşik sorgu (LINQ)](/dotnet/csharp/linq/index)   
 [Nasıl yapılır: Şerit özelleştirmeye başlama](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [Şerit Tasarımcısı](../vsto/ribbon-designer.md)   
 [İzlenecek yol: Şerit Tasarımcısını kullanarak özel sekme oluşturma](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Şerit nesne modeline genel bakış](../vsto/ribbon-object-model-overview.md)   
 [Outlook için Şerit özelleştirme](../vsto/customizing-a-ribbon-for-outlook.md)   
 [Nasıl yapılır: Şeritteki sekmenin konumunu değiştirme](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)   
 [Nasıl yapılır: yerleşik bir sekmeyi özelleştirme](../vsto/how-to-customize-a-built-in-tab.md)   
 [Nasıl yapılır: Backstage görünümüne denetimler ekleme](../vsto/how-to-add-controls-to-the-backstage-view.md)   
 [Nasıl yapılır: Şerit Şerit Tasarımcısından Şerit XML'ine verebilir.](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)   
 [Nasıl yapılır: kullanıcı arayüzü hatalarını gösterme eklentisi](../vsto/how-to-show-add-in-user-interface-errors.md)  
  
  