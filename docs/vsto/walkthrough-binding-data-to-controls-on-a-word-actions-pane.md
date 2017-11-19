---
title: "İzlenecek yol: Word eylemler bölmesindeki denetimlere veri bağlama | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], data binding
- actions panes [Office development in Visual Studio], data binding
- data binding [Office development in Visual Studio], smart documents
- data binding [Office development in Visual Studio], actions panes
- actions panes [Office development in Visual Studio], binding controls
- smart documents [Office development in Visual Studio], data binding
ms.assetid: 5ef72fc7-412b-4454-9890-4479a13ee7f9
caps.latest.revision: "64"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6a70bd325a5a9e20f9a67e59f81c63ce4b1ddcc4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-binding-data-to-controls-on-a-word-actions-pane"></a>İzlenecek Yol: Word Eylemler Bölmesindeki Denetimlere Veri Bağlama
  Bu anlatımda Word eylemler bölmesindeki denetimlere veri bağlama gösterilir. Denetimler, SQL Server veritabanındaki tablolar arasındaki ana/ayrıntı ilişkisi gösterir.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Veriye bağlı olan Windows Forms denetimleri ile Eylemler bölmesi oluşturma.  
  
-   Ana/ayrıntı ilişkisi denetimlerinde verileri görüntülemek için kullanma.  
  
-   Uygulama açıldığında eylemler bölmesini göster.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]veya [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].  
  
-   Northwind SQL Server örnek veritabanı sunucusuyla erişim.  
  
-   SQL Server veritabanına yazma ve okuma izni.  
  
## <a name="creating-the-project"></a>Projeyi Oluşturma  
 İlk adım bir Word belgesi proje oluşturmaktır.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adlı bir Word belgesi proje oluşturun **My Word eylemler bölmesindeki**. Sihirbazı'nda seçin **bir yeni belge oluşturun**.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio tasarımcıda yeni Word belgesini açar ve ekler **My Word eylemler bölmesindeki** için proje **Çözüm Gezgini**.  
  
## <a name="adding-controls-to-the-actions-pane"></a>Eylemler bölmesine denetimleri ekleme  
 Bu kılavuz için veri bağlantılı Windows Forms denetimleri içeren eylemler bölmesi denetimi gerekir. Bir veri kaynağı projeye ekleyin ve ardından denetimlerden sürükleyin **veri kaynakları** Eylemler bölmesi denetimi için pencere.  
  
#### <a name="to-add-an-actions-pane-control"></a>Eylemler bölmesi denetimi eklemek için  
  
1.  Seçin **My Word eylemler bölmesindeki** proje **Çözüm Gezgini**.  
  
2.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  
  
3.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **Eylemler bölmesi denetimi**, adlandırın **ActionsControl**ve ardından **Ekle**.  
  
#### <a name="to-add-a-data-source-to-the-project"></a>Bir veri kaynağı projeye eklemek için  
  
1.  Varsa **veri kaynakları** pencere görünür değil, bunu, menü çubuğu seçme görüntülemek **Görünüm**, **diğer pencereler**, **veri kaynakları**.  
  
    > [!NOTE]  
    >  Varsa **veri kaynaklarını Göster** kullanılamıyor Word belgesini tıklatın ve sonra yeniden denetleyin.  
  
2.  Tıklatın **yeni veri kaynağı Ekle** başlatmak için **veri kaynağı Yapılandırma Sihirbazı**.  
  
3.  Seçin **veritabanı** ve ardından **sonraki**.  
  
4.  Northwind örnek SQL Server veritabanı için bir veri bağlantısı seçin veya yeni bir bağlantı kullanarak eklemek **yeni bağlantı** düğmesi.  
  
5.  
              **İleri**'ye tıklayın.  
  
6.  Bağlantı seçiliyse kaydetme seçeneğini ve ardından temizlemek **sonraki**.  
  
7.  Genişletme **tabloları** düğümünde **veritabanı nesnelerinin** penceresi.  
  
8.  Onay kutusunu işaretleyin **Üreticiler** ve **ürünleri** tabloları.  
  
9. **Son**'a tıklayın.  
  
 Sihirbaz ekler **Üreticiler** tablo ve **ürünleri** tablosu **veri kaynakları** penceresi. Projenize görünür türü belirtilmiş veri kümesi de ekler **Çözüm Gezgini**.  
  
#### <a name="to-add-data-bound-windows-forms-controls-to-an-actions-pane-control"></a>Eylemler bölmesi denetimine veri bağlantılı Windows Forms denetimleri ekleme  
  
1.  İçinde **veri kaynakları** penceresinde genişletin **Üreticiler** tablo.  
  
2.  Aşağı açılan oku tıklatın **şirket adı** düğümü ve select **ComboBox**.  
  
3.  Sürükleme **ŞirketAdı** gelen **veri kaynakları** Eylemler bölmesi denetimi için pencere.  
  
     A <xref:System.Windows.Forms.ComboBox> denetimi Eylemler bölmesi denetiminin oluşturulur. Aynı zamanda bir <xref:System.Windows.Forms.BindingSource> adlı `SuppliersBindingSource`, bir tablo bağdaştırıcısı ve bir <xref:System.Data.DataSet> bileşen projesinde eklenir.  
  
4.  Seçin `SuppliersBindingNavigator` içinde **bileşen** Tepsisi ve DELETE tuşuna basın. Değil kullanacağınız `SuppliersBindingNavigator` bu kılavuzda.  
  
    > [!NOTE]  
    >  Silme `SuppliersBindingNavigator` için oluşturulan tüm kodları kaldırmaz. Bu kodu kaldırabilirsiniz.  
  
5.  Etiket ve değişiklik altında olacak biçimde birleşik giriş kutusu taşıyın **boyutu** özelliğine **171, 21**.  
  
6.  İçinde **veri kaynakları** penceresinde genişletin **ürünleri** Tablo alt **Üreticiler** tablo.  
  
7.  Aşağı açılan oku tıklatın **ProductName** düğümü ve select **ListBox**.  
  
8.  Sürükleme **ProductName** Eylemler bölmesi denetimi için.  
  
     A <xref:System.Windows.Forms.ListBox> denetimi Eylemler bölmesi denetiminin oluşturulur. Aynı zamanda bir <xref:System.Windows.Forms.BindingSource> adlı `ProductBindingSource` ve bir tablo bağdaştırıcısı bileşen'nde projeye eklenir.  
  
9. Etiket ve değişiklik altında olacak biçimde liste kutusu taşıyın **boyutu** özelliğine **171, 95**.  
  
10. Sürükleme bir <xref:System.Windows.Forms.Button> gelen **araç** Eylemler bölmesi denetlemek ve liste kutusu yerleştirin.  
  
11. Sağ <xref:System.Windows.Forms.Button>, tıklatın **özellikleri** kısayol menüsünde ve aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**Ekle**|  
    |**Metin**|**Ekle**|  
  
12. Denetimleri sığması için kullanıcı denetimi yeniden boyutlandırın.  
  
## <a name="setting-up-the-data-source"></a>Veri kaynağını ayarlama  
 Veri kaynağı kurmak için kodu ekleyin <xref:System.Windows.Forms.UserControl.Load> Olay denetimi verilerle doldurmak için Eylemler bölmesinde denetiminin <xref:System.Data.DataTable>ve <xref:System.Windows.Forms.Binding.DataSource%2A> ve <xref:System.Windows.Forms.BindingSource.DataMember%2A> her denetim için özellikler.  
  
#### <a name="to-load-the-control-with-data"></a>Denetimin veri yüklemek için  
  
1.  İçinde <xref:System.Windows.Forms.UserControl.Load> olay işleyicisi `ActionsControl` sınıfında, aşağıdaki kodu ekleyin.  
  
     [!code-vb[Trin_VstcoreActionsPaneWord#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ActionsControl.vb#1)]
     [!code-csharp[Trin_VstcoreActionsPaneWord#1](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#1)]  
  
2.  C# ' ta olay işleyicisine eklemelisiniz <xref:System.Windows.Forms.UserControl.Load> olay. Bu kodu koyabilirsiniz `ActionsControl` çağrısından sonra Oluşturucusu `InitializeComponent`. Olay işleyicileri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#33](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#33)]  
  
#### <a name="to-set-data-binding-properties-of-the-controls"></a>Veri bağlama denetimleri özelliklerini ayarlamak için  
  
1.  Seçin `CompanyNameComboBox` denetim.  
  
2.  İçinde **özellikleri** penceresinde, düğmesini sağındaki **veri kaynağı** özelliği ve seçin **suppliersBindingSource**.  
  
3.  Düğmesini sağındaki **DisplayMember** özelliği ve select **ŞirketAdı**.  
  
4.  Genişletin **veri bağlamaları** özelliği, düğmesini sağındaki **metin** özelliği ve seçin **hiçbiri**.  
  
5.  Seçin `ProductNameListBox` denetim.  
  
6.  İçinde **özellikleri** penceresinde, düğmesini sağındaki **veri kaynağı** özelliği ve seçin **productsBindingSource**.  
  
7.  Düğmesini sağındaki **DisplayMember** özelliği ve select **ProductName**.  
  
8.  Genişletin **veri bağlamaları** özelliği, düğmesini sağındaki **SelectedValue** özelliği ve seçin **hiçbiri**.  
  
## <a name="adding-a-method-to-insert-data-into-a-table"></a>Bir tabloya veri eklemek için bir yöntem ekleme  
 Sonraki ilişkili denetimlerden veri okumak ve bir Word belgeniz tabloda doldurmak için bir görevdir. İlk olarak, tablodaki başlıkları biçimlendirmek için bir yordam oluşturmak ve ardından ekleyin `AddData` oluşturmak ve bir Word tablosu biçimlendirmek için yöntem.  
  
#### <a name="to-format-the-table-headings"></a>Tablo başlıkları biçimlendirmek için  
  
1.  İçinde `ActionsControl` sınıfı, tablonun başlıklarını biçimlendirmek için bir yöntem oluşturma.  
  
     [!code-vb[Trin_VstcoreActionsPaneWord#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ActionsControl.vb#2)]
     [!code-csharp[Trin_VstcoreActionsPaneWord#2](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#2)]  
  
#### <a name="to-create-the-table"></a>Tablo oluşturmak için  
  
1.  İçinde `ActionsControl` sınıfı, bir zaten var ve veri Eylemler bölmesinden tabloya eklerseniz, bir tablo oluşturacaksınız bir yöntem yazma.  
  
     [!code-vb[Trin_VstcoreActionsPaneWord#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ActionsControl.vb#3)]
     [!code-csharp[Trin_VstcoreActionsPaneWord#3](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#3)]  
  
#### <a name="to-insert-text-into-a-word-table"></a>Word tablosuna metin eklemek için  
  
1.  Aşağıdaki kodu ekleyin <xref:System.Windows.Forms.Control.Click> olay işleyicisi **Ekle** düğmesi.  
  
     [!code-vb[Trin_VstcoreActionsPaneWord#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ActionsControl.vb#4)]
     [!code-csharp[Trin_VstcoreActionsPaneWord#4](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#4)]  
  
2.  C# ' ta için bir olay işleyicisi oluşturmalısınız <xref:System.Windows.Forms.Control.Click> düğmesinin olayı.  Bu kodu koyabilirsiniz <xref:System.Windows.Forms.UserControl.Load> olay işleyicisi `ActionsControl` sınıfı.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#5](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ActionsControl.cs#5)]  
  
## <a name="showing-the-actions-pane"></a>Eylemler bölmesini gösterme  
 Denetimler için eklendikten sonra Eylemler bölmesinde görünür hale gelir.  
  
#### <a name="to-show-the-actions-pane"></a>Eylemler bölmesini göstermek için  
  
1.  İçinde **Çözüm Gezgini**, sağ **ThisDocument.vb** veya **ThisDocument.vb**ve ardından **görünümü kodu** kısayol menüsünde.  
  
2.  En üstte denetimi yeni bir örneğini oluşturmak `ThisDocument` aşağıdaki gibi görünen sınıfının.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#6](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#6)]
     [!code-vb[Trin_VstcoreActionsPaneWord#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#6)]  
  
3.  Kodu ekleyin <xref:Microsoft.Office.Tools.Word.Document.Startup> olay işleyicisi `ThisDocument` böylece aşağıdaki gibi görünüyor.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#7](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#7)]
     [!code-vb[Trin_VstcoreActionsPaneWord#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#7)]  
  
## <a name="testing-the-application"></a>Uygulamayı Test Etme  
 Artık belge açıldığında eylemler bölmesinde göründüğünü doğrulamak için belgenizi test edebilirsiniz. Ana/ayrıntı ilişkisi eylemler bölmesindeki denetimlere test ve verileri bir sözcük doldurulur emin olun tablosundan **Ekle** düğmesine tıklandığında.  
  
#### <a name="to-test-your-document"></a>Belgenizi test etmek için  
  
1.  Projenizi çalıştırmak için F5 tuşuna basın.  
  
2.  Eylemler bölmesinde görünür olduğunu doğrulayın.  
  
3.  Açılan kutuda şirketi seçin ve doğrulayın öğeleri **ürünleri** liste kutusunu değiştirin.  
  
4.  Bir ürün seçin, **Ekle** eylemler bölmesindeki ve ürün ayrıntıları Word tablosuna eklendiğini doğrulayın.  
  
5.  Ek ürünler çeşitli şirketlerden ekleyin.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu kılavuz, Word eylemler bölmesindeki denetimlere veri bağlama temellerini gösterir. Sonradan gelebilecek bazı görevler şunlardır:  
  
-   Excel'de denetimlere veri bağlama. Daha fazla bilgi için bkz: [izlenecek yol: Excel eylemler bölmesindeki denetimlere veri bağlama](../vsto/walkthrough-binding-data-to-controls-on-an-excel-actions-pane.md).  
  
-   Projeyi dağıtma. Daha fazla bilgi için bkz: [tarafından ClickOnce kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md)   
 [Nasıl yapılır: Word belgelerini ve Excel çalışma kitaplarına Eylemler bölmesi ekleme](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  